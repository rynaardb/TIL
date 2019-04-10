# Working with JSON

## Parsing JSON

### Given the following:

```swift
struct Person: Codable {
    let firstname: String
    let lastname: String
}

var jsonString =
"""
{
    "firstname":"Rynaard",
    "lastname":"Burger"
}
"""
```

### Decoding from JSON string / data to typed object:

```swift
let decoder = JSONDecoder()

if let jsonData = jsonString.data(using: .utf8),
    let decodedPerson = try? decoder.decode(Person.self, from: jsonData) {

    print(decodedPerson.firstname)
    print(decodedPerson.lastname)
}
```

### Encoding typed object to string / data:

```swift
let person = Person(firstname: "Rynaard", lastname: "Burger")

let encoder = JSONEncoder()
let encodedJsonData = try! encoder.encode(person)

if let encodedJsonString = String(data: encodedJsonData, encoding: .utf8) {
    print(encodedJsonString)
}
```

## Codable

`Codable` is a type alias for the `Encodable` and `Decodable` protocols.

Below is a one-to-one representation of all properties matching:

```swift
struct Person: Codable {
    let firstname: String
    let lastname: String
}
```

### Customizing key names:

```swift
struct Person: Codable {
    let firstname: String
    let lastname: String
    let pob: String

    enum CodingKeys : String, CodingKey {
	case firstname
	case lastname
	case pob = "placeOfBirth"
    }   
}
```

## Working with dates

```swift
let encoder = JSONEncoder()
encoder.dateEncodingStrategy = .iso8601
```

## Online Resources

* [Ultimate Guide to JSON Parsing with Swift 4](https://benscheirman.com/2017/06/swift-json/)
