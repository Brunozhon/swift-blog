# A Quick Swift Guide

## Variables

A variable is a container that stores data. It can be declared with `var` or `let`.

```swift
var myVariable = "Hello, world!"
let pi = 3.1415926
```

Variables declared with `var` can be mutated, or changed. Variables declared with `let` can't be mutated.

```swift
myVariable = "Now it's different!"
pi = 3.14 // Error
```

Once a variable's type is declared, it can't be changed.

```swift
myVariable = 1.5 // Error
```

## Functions

Functions are declared with the `func` keyword.

```swift
func printHelloWorld() {
  print("Hello, world!")
}
```

You can call it using by adding `()` to the end.

```swift
printHelloWorld()
```

Functions can take arguments, which much have a declared type.

```swift
func printHappyBirthday(for person: String) {
  print("Happy birthday, \(person)!")
}
```
