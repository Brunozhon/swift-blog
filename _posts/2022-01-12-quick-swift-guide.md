---
tags: essentials basic
---

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

Functions can take arguments, which much have a declared type. Arguments have two parts, seperated by a space: the argument label and the argument name.

```swift
func printHappyBirthday(for person: String) {
  print("Happy birthday, \(person)!")
}

func printHappyBirthday(person for: String) {
  fatalError("Wrong happy birthday function called!")
}
```

You call them by their argument label.

```swift
printHappyBirthday(for: "Bruno")
printHappyBirthday(person: "Bruno") // Fatal error!
```

When you call a function, it's like calling this:

```swift
printHappyBirthday(for: "Bruno")     // 1
print("Happy birthday, \(person)!")  // 2
print("Happy birthday, \("Bruno")!") // 3

printHappyBirthday(person: "Bruno")                 // 1
fatalError("Wrong happy birthday function called!") // 2
```

## Types

Types are like blueprints. Think of a house.

```
########## HOUSE ##########
What's inside one?
- Rooms
  - Hallways
  - Bedrooms
  - Playrooms
  - Garage
  - Walls (Bricks, wood, ...)
- Windows
- Doors
- Walls (Bricks, ...)
What can it do?
- Open the doors
- Open the windows
- Close the doors
- Close the windows
```

Here is one in Swift.

```swift
Properties
var rooms: [Room]
var windows: [Window]
var doors: [Door]
var walls: [Wall]
Functions
func openDoor(_ door: Door) async throws
func openWindow(_ window: Window) async throws
func openAllDoors() async
func openAllWindows() async
func closeDoor(_ door: Door) async throws
func closeWindow(_ window: Window) async throws
func closeAllDoors() async
func closeAllWindows() async
```

Abracadarbra! Look at it turn into a struct!

```swift
/// 1

// Properties
var rooms: [Room]
var windows: [Window]
var doors: [Door]
var walls: [Wall]
// Functions
func openDoor(_ door: Door) async throws
func openWindow(_ window: Window) async throws
func openAllDoors() async
func openAllWindows() async
func closeDoor(_ door: Door) async throws
func closeWindow(_ window: Window) async throws
func closeAllDoors() async
func closeAllWindows() async

/// 2

struct House {
  // Properties
  var rooms: [Room]
  var windows: [Window]
  var doors: [Door]
  var walls: [Wall]
  // Functions
  func openDoor(_ door: Door) async throws
  func openWindow(_ window: Window) async throws
  func openAllDoors() async
  func openAllWindows() async
  func closeDoor(_ door: Door) async throws
  func closeWindow(_ window: Window) async throws
  func closeAllDoors() async
  func closeAllWindows() async
}

/// 3

struct House {
  // Properties
  var rooms: [Room]
  var windows: [Window]
  var doors: [Door]
  var walls: [Wall]
  // Functions
  func openDoor(_ door: Door) async throws { ... }
  func openWindow(_ window: Window) async throws { ... }
  func openAllDoors() async { ... }
  func openAllWindows() async { ... }
  func closeDoor(_ door: Door) async throws { ... }
  func closeWindow(_ window: Window) async throws { ... }
  func closeAllDoors() async { ... }
  func closeAllWindows() async { ... }
}

/// 4

struct House {
  // Properties
  var rooms: [Room] = []
  var windows: [Window] = []
  var doors: [Door] = []
  var walls: [Wall] = []
  // Functions
  mutating func openDoor(_ door: Door) async throws { ... }
  mutating func openWindow(_ window: Window) async throws { ... }
  mutating func openAllDoors() async { ... }
  mutating func openAllWindows() async { ... }
  mutating func closeDoor(_ door: Door) async throws { ... }
  mutating func closeWindow(_ window: Window) async throws { ... }
  mutating func closeAllDoors() async { ... }
  mutating func closeAllWindows() async { ... }
}
```

You can call your struct using a initializer.

```swift
House()
House(
  rooms: [...],
  windows: [...],
  doors: [...],
  walls: [...]
)
```

That's it for Swift! I hope you learned the basics of Swift!
