# Strings

In Swift, a string is composed of a collection of Character values, stored using the UTF-8 encoding.

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

```swift
let string = "Hello world!"

let indexStartOfText = string.index(string.startIndex, offsetBy: 6)
let indexEndOfText = string.index(string.endIndex, offsetBy: -6)

let result = string[indexStartOfText...]
```

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
