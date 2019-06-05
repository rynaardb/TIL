# SwiftUI

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