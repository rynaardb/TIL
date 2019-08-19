# Common Gotchas

Common gotchas when developing iOS applications.

## GCD

* Make sure the UI gets updated on the main thread

## Retain cycles

* The most common cause of retain cycles is due to a reference to `self` when using closures. Use `[weak self]` with `self?.prop` instead.

## Autolayout

* Views should first tbe added to their parent view before setting constraints
* Remember to set `isActive = true` on individual constraints or use `NSLayoutConstraint.activate`

## UIStackView

* Set `view.clipsToBounds = true` to avoid views overlapping with each other