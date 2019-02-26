# Autolayout

## Notes

* No need to calculate frames
* Initialize views with `.zero` rect
* Set `translatesAutoresizingMaskIntoConstraints = false` on views
* Remember to add the view to the hierarchy using `addSubview`
* Remember to activate constraints by either setting `.isActive = true` or using `NSLayoutConstraint.activate`
* Set constraints in `loadView` and **not** in `viewDidLoad`