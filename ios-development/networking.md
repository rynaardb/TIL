# Networking

## URLSession

### Simple HTTP operations

**GET**

```swift
if let url = URL(string: "https://somewhere.com") {
    var request = URLRequest(url: url)

    let task = URLSession.shared.dataTask(with: request) { (data, response, error) in
        // handle data, response error here
    }
    task.resume()
}
```

**POST**

```swift
if let url = URL(string: "https://somewhere.com") {
    var request = URLRequest(url: url)
    request.httpMethod = "POST"

    let task = URLSession.shared.dataTask(with: request) { (data, response, error) in
        // handle data, response error here
    }
    task.resume()
}
```

**PUT**

```swift
if let url = URL(string: "https://somewhere.com") {
    var request = URLRequest(url: url)
    request.httpMethod = "PUT"

    let task = URLSession.shared.dataTask(with: request) { (data, response, error) in
        // handle data, response error here
    }
    task.resume()
}
```

**DELETE**

```swift
if let url = URL(string: "https://somewhere.com") {
    var request = URLRequest(url: url)
    request.httpMethod = "DELETE"

    let task = URLSession.shared.dataTask(with: request) { (data, response, error) in
        // handle data, response error here
    }
    task.resume()
}
```

**Setting request headers**

```swift
if let url = URL(string: "https://www.apple.com") {
    var request = URLRequest(url: url)
    request.setValue("application/json", forHTTPHeaderField: "Accept")

    let task = URLSession.shared.dataTask(with: request) { (data, response, error) in
        // handle data, response error here
    }
    task.resume()
}
```

### Downloading files

```swift
let url = URL(string: "https://www.apple.com")!

let task = URLSession.shared.downloadTask(with: url) { localURL, urlResponse, error in
    if let localURL = localURL {
        if let string = try? String(contentsOf: localURL) {
            print(string)
        }
    }
}

task.resume()
```

### Multi-part form data

TODO