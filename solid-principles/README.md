# S.O.L.I.D. Principles

## (S)ingle Responsibility

An object should only have one and only one responsibility. Think of how changes to that object will effect the rest of the application. The goal is to have minimal to no effect on other object making it easy to change in the future.

## (O)pen Closed

The Open Closed Principle (or OCP) states that a class should be open for extension, but closed for modification. The goal is to write classes that are more stable, and don't require constant changes themselves to support every scenario the software encounters. Instead, having a stable class to inherit from can provide a nice extension point for our software to customize it for other needs.

## (L)iskov Substitution

The Liskov Subtitution Principle, which stresses the importance of the strong relationship a type has with its super type. A good example of where this principle is **not violated** is UIKit's `UIView`. For example, we have multiple subviews of `UIView` like: `UIButton`, `UIScrollView`, `UITableView` etc. All of these `UIView` subclasses can be substituted for another subclass of `UIView` and still work as expected i.e. adding subviews, responding to touch events etc.

## (I)nterface Segregation

A type should not depend on methods from an interface that it will never use. Often times this means that the type probably carries too many responsibilities, but breaking it apart is difficult for other reasons (perhaps too many things depend on it and changing it would be expensive). You can extract smaller interfaces that support the individual responsibilities, but still have the same class adopt it. Doing so opens up opportunities for further refactoring and testing.

## (D)ependency Inversion

High level components should not depend on low level components, but instead they both should depend on abstractions.
