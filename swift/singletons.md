# Singletons

## Basic singleton implementation

```swift
class WatchManager {
    static let shared = WatchManager()

    private init(){ }
}
```