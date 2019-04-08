# Result Type

```swift
struct Item: Codable {
    let id: Int
    let name: String
}

func getItems(completionHandler: @escaping (Result<[Item]?, Error>) -> ()) {
    guard let url = URL(string: "http://restapi.com/items") else { return }

    let session = URLSession(configuration: .default)

    session.dataTask(with: url) { (data, response, error) in
        if let error = error {
            completionHandler(.failure(error))
        }

        if let data = data {
            do {
                let jsonDecoder = JSONDecoder()
                let items = try jsonDecoder.decode([Item].self, from: data)

                completionHandler(.success(items))
            } catch {
                completionHandler(.failure(error))
            }
        }
    }.resume()
}

```