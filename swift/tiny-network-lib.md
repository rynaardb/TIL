# Tiny Networking Library

```swift
struct Resource<T> where T: Decodable {
    let path: String
    let queryItems: [URLQueryItem]?
    let parse: (Data) -> T? = { data in
        return try? JSONDecoder().decode(T.self, from: data)
    }

    init(path: String, queryItems: [URLQueryItem]? = nil) {
        self.path = path
        self.queryItems = queryItems
    }
}
```

```swift
enum WebserviceError: Error {
    case networkError(Error)
    case serverError
    case requestError(Int, String)
    case invalidResponse
    case decodingError(Error)
}

final class Webservice {
    private let session: URLSession!
    private let baseURL = URL(string: "https://jsonplaceholder.typicode.com")!

    init(session: URLSession = .shared) {
        self.session = session
    }

    func load<T>(resource: Resource<T>, completion: @escaping (Result<T?, WebserviceError>) -> ()) {
        var urlComponents = URLComponents(url: baseURL, resolvingAgainstBaseURL: true)!
        urlComponents.path = resource.path
        urlComponents.queryItems = resource.queryItems
        let request = URLRequest(url: urlComponents.url!)

        session.dataTask(with: request) { (data, response, error) in
            if let error = error  {
                DispatchQueue.main.async {
                    completion(Result.failure(.networkError(error)))
                }
                return
            }

            guard let http = response as? HTTPURLResponse else {
                DispatchQueue.main.async {
                    completion(.failure(.invalidResponse))
                }
                return
            }

            switch http.statusCode {
            case 200:
                DispatchQueue.main.async {
                    completion(.success((data.flatMap(resource.parse))))
                }
            case 400...499:
                if let data = data, let body = String(data: data, encoding: .utf8) {
                    DispatchQueue.main.async {
                        completion(.failure(.requestError(http.statusCode, body)))
                    }
                }
            case 500...599:
                DispatchQueue.main.async {
                    completion(.failure(.serverError))
                }
            default:
                fatalError("Unhandeled HTTP status code: \(http.statusCode)")
            }

        }.resume()
    }
}
```