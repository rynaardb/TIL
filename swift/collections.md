# Collections

## Working with collections

### Given the following

```swift
struct Person {
    let firstname: String
    let lastname: String
    let age: Int
}

let personArray = [
    Person(firstname: "Rynaard", lastname: "Burger", age: 36),
    Person(firstname: "Foo", lastname: "Bar", age: 24)
]
```

### map

Apply transformations to items in the collection.

```swift
let uppercasedFirstnames = personArray.map { $0.firstname.uppercased() }
```

### filter

```swift
let filteredArray = personArray.filter { $0.firstname == "Foo" }
```

### reduce

```swift
let combinedAge = personArray.reduce(0) { (result, next) -> Int in
    return result + next.age
}
```