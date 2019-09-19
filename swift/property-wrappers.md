# Property Wrappers

A property wrapper adds a layer of separation between code that manages how a property is stored and the code that defines a property.

For example, if you have properties that provide thread-safety checks or store their underlying data in a database, you have to write that code on every property. When you use a property wrapper, you write the management code once when you define the wrapper, and then reuse that management code by applying it to multiple properties.

