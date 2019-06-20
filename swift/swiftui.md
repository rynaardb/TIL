# SwiftUI

## Basics

By default, SwiftUI view files declare two structures. The first structure conforms to the `View` protocol and describes the view’s content and layout. The second structure conforming to `PreviewProvider` declares a preview for that view.

```swift
struct ContentView: View {
    var body: some View {
        Text("Hello SwiftUI!")
    }
}

struct ContentView_Preview: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```

## Wrapping UIView subclasses

To use `UIView` subclasses from within SwiftUI, you wrap the other view in a SwiftUI view that conforms to the `UIViewRepresentable` protocol.

The UIViewRepresentable protocol has two requirements you need to add:

`makeUIView(context:)` and `updateUIView(_:context:)`

```swift
struct MapView : UIViewRepresentable {
    func makeUIView(context: Context) -> MKMapView {
        MKMapView(frame: .zero)
    }

    func updateUIView(_ view: MKMapView, context: Context) {
        let coordinate = CLLocationCoordinate2D(
            latitude: 34.011286, longitude: -116.166868)
        let span = MKCoordinateSpan(latitudeDelta: 2.0, longitudeDelta: 2.0)
        let region = MKCoordinateRegion(center: coordinate, span: span)
        view.setRegion(region, animated: true)
    }
}
```

## Stacks

### HStack

```swift
HStack {
    Text("Col 1")
    Text("Col 2")
    Text("Col 3")
}
```

### VStack

```swift
VStack {
    Text("Row 1")
    Text("Row 2")
    Text("Row 3")
}
```

## Lists

### Static

```swift
List {
    Text("Row 1")
    Text("Row 2")
    Text("Row 3")
}
```

### Dynamic

```swift
List(items) { item in
    Text(item.name)
}
```

Lists work with identifiable data. You can make your data identifiable in one of two ways: by calling the `identified(by:)` method with a key path to a property that uniquely identifies each element, or by making your data type conform to the `Identifiable` protocol.

```swift
struct Item: Hashable, Codable, Identifiable {
    var id: Int
    var name: String
}
```

## Navigation between List and Detail

You add navigation capabilities to a list by embedding it in a `NavigationView` and then nesting each row in a `NavigationButton` to set up a transtition to a destination view.

```swift
NavigationView {
    List(items) { item in
        Text(item.name)
    }
    .navigationBarTitle(Text("Items"))
}
```

## Dynamic Previews

By default, previews render at the size of the device in the active scheme. You can change the preview device by calling the `previewDevice(_:)` modifier method.

```swift
struct ItemList_Previews: PreviewProvider {
    static var previews: some View {
        ItemList()
            .previewDevice(PreviewDevice(rawValue: "iPhone XS"))
    }
}
```

`ForEach` operates on collections the same way as the list, which means you can use it anywhere you can use a child view, such as in stacks, lists, groups, and more. When the elements of your data are simple value types — you can use `\.self` as key path to the identifier.

```swift
struct ItemList_Previews: PreviewProvider {
    static var previews: some View {
        ForEach(["iPhone SE", "iPhone XS Max"].identified(by: \.self)) { deviceName in
            ItemList()
                .previewDevice(PreviewDevice(rawValue: deviceName))
        }
    }
}
```

## Working with UIKit views and view controllers

To represent UIKit views and view controllers in SwiftUI, you create types that conform to the `UIViewRepresentable` and `UIViewControllerRepresentable` protocols. Your custom types create and configure the UIKit types that they represent, while SwiftUI manages their life cycle and updates them when needed.

```swift
struct ItemViewController: UIViewControllerRepresentable {
    var controllers: [UIViewController]

    func makeUIViewController(context: Context) -> ItemViewController {
        let itemViewController = ItemViewController(
            transitionStyle: .scroll,
            navigationOrientation: .horizontal)

        return pageViewController
    }

    func updateUIViewController(_ itemViewController: ItemViewController, context: Context) {
        itemViewController.setViewControllers(
            [controllers[0]], direction: .forward, animated: true)
    }
}
```

## Scroll Views

⚠️ Only works with `HStack` as parent view.

```swift
ScrollView {
    HStack {
        Text("Col 1")
        Text("Col 1")
    }
}
```
