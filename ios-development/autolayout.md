# Autolayout

## Notes

* No need to calculate frames
* Initialize views with `.zero` rect
* Set `translatesAutoresizingMaskIntoConstraints = false` on views
* Remember to add the view to the hierarchy using `addSubview`
* Remember to activate constraints by either setting `.isActive = true` or using `NSLayoutConstraint.activate`
* Set constraints in `loadView` and **not** in `viewDidLoad`

## Width & Height

```swift
view.widthAnchor.constraint(equalToConstant: 50).isActive = true
view.heightAnchor.constraint(equalToConstant: 50).isActive = true
```

## Aspect Ratio

```swift
testView.widthAnchor.constraint(equalToConstant: 128).isActive = true
testView.widthAnchor.constraint(equalTo: testView.heightAnchor, multiplier: 16/9).isActive = true
```

## Centering Views

```swift
view.centerXAnchor.constraint(equalTo: self.view.centerXAnchor).isActive = true
view.centerYAnchor.constraint(equalTo: self.view.centerYAnchor).isActive = true
```

## Stretching & Filling

```swift
view.topAnchor.constraint(equalTo: self.view.topAnchor, constant: 64),
view.leadingAnchor.constraint(equalTo: self.view.leadingAnchor, constant: 64),
view.trailingAnchor.constraint(equalTo: self.view.trailingAnchor, constant: -64),
view.bottomAnchor.constraint(equalTo: self.view.bottomAnchor, constant: -64),
```

## Safe Area Layout Guides

```swift
view.topAnchor.constraint(equalTo: self.view.safeAreaLayoutGuide.topAnchor),
view.leadingAnchor.constraint(equalTo: self.view.safeAreaLayoutGuide.leadingAnchor),
view.trailingAnchor.constraint(equalTo: self.view.safeAreaLayoutGuide.trailingAnchor),
view.bottomAnchor.constraint(equalTo: self.view.safeAreaLayoutGuide.bottomAnchor),
```

## Animating Layout Constraints