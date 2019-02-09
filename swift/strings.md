# Strings

Strings are a collection of characters

## Manipulating strings

### Multiline string literals

```swift
let multilineString = """
{
    "firstname":"Rynaard"
    "lastname":"Burger"
}
"""
```

### Substrings

TODO!

### Check if a string contains a word (using contains)

```swift
let string = "Hello world!"
let result = string.contains("world")
```

### Capitalize the first letter of a string

```swift
extension String {
    func capitalizingFirstLetter() -> String {
        return prefix(1).capitalized + dropFirst()
    }

    mutating func capitalizeFirstLetter() {
        self = self.capitalizingFirstLetter()
    }
}

let test = "hello world"
print(test.capitalizingFirstLetter())
```