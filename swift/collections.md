# Collections

## Higher Order Functions

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

### compactMap (replaced flatMap in Swift 4.1)

Transform each item in the collection and remove any items which are nil.

```swift
let mixedArray = ["1", "2", "3", "Dog"]
let numbersOnly = mixedArray.compactMap { Int($0) }
```

### filter

Filters out items in a collection.

```swift
let filteredArray = personArray.filter { $0.firstname == "Foo" }
```

### reduce

Reduces the collection down to a single result.

```swift
let combinedAge = personArray.reduce(0) { (result, next) -> Int in
    return result + next.age
}
```

### sort

Sort by optional date.

```swift
let arraySortedByDate = messages.sorted {
    let date1 = $0.createdAt ?? Date.distantPast
    let date2 = $1.createdAt ?? Date.distantPast

    return date1 > date2
}
```

## Dictionaries

### Get all the keys

```swift
let keys = dict.map{$0.key}
```

### Get all the values

```swift
let values = dict.map{$0.value}
```