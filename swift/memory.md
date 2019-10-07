# Memory

Common techniques and facts dealing with memory on iOS.

```swift

var helloWorld = "Hello, World!"
withUnsafePointer(to: &helloWorld) {
    print($0) // prints the memory address
}

print(MemoryLayout.size(ofValue: helloWorld)) // 16 bytes
print(helloWorld)

```

## Some basics

## Copy by reference

## Copy on write

## Copy by value