# Theming

```swift
struct Theme {
  static func apply(to window: UIWindow) {
  window.tintColor = Colors.lightPurple

  let tabBar = UITabBar.appearance()
  tabBar.barTintColor = Colors.lightPurple

  let navBar = UINavigationBar.appearance()
  navBar.barTintColor = Colors.lightPurple
  navBar.titleTextAttributes = [
    NSAttributedString.Key.foregroundColor: Colors.lightPurple
  ]
}

struct Colors {
  static var lightPurple = UIColor(hue:0.72, saturation:0.46, brightness:0.45, alpha:1.00)
}
```
