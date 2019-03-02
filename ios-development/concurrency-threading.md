# Concurrency & Threading

## Grand Central Dispatch (GCD)

### Asynchronous

For long running tasks to be executed in the background to avoid blocking the main UI thread. The order of completion is never guaranteed.

Execute code on the **main thread** from another background thread:

```swift
DispatchQueue.main.async {
    // ui code here i.e tableView.reloadData()
}
```
Below will avoid strong reference cycles to `self`

```swift
DispatchQueue.main.async { [unowned self] in
    // ui code here i.e self.tableView.reloadData()
}
```

Execute code after a delay:

```swift
DispatchQueue.main.asyncAfter(deadline: .now() + 0.5) {
    // code will execute after 500ms
}
```

Execute code on a **background thread**:

```swift
DispatchQueue.global(qos: .background).async {
    // long running operation here
}
```

### Synchronous

Used when the order of the completion is important.

## OperationQueue

Useful when you need to precisely control how many simultaneous operations can run and what QOS you need, while also letting you schedule work using closures. You can even ask the operation queue to wait until all its operations are finished, which makes scheduling easier.

```swift
let queue = OperationQueue()

for image in images {
    queue.addOperation {
        self.process(image)
    }
}

queue.waitUntilAllOperationsAreFinished()
```

Setting the number of concurrent operations:

```swift
queue.maxConcurrentOperationCount = 4
```

Stop all operations yet to be started:

```swift
queue.cancelAllOperations()
```

## Online Resources

* [Swift Multi-Threading using GCD For Beginners](https://hackernoon.com/swift-multi-threading-using-gcd-for-beginners-2581b7aa21cb)
* [Dispatch On The Server - Soroush Khanlou](http://khanlou.com/2017/09/dispatch-on-the-server/)