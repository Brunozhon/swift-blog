---
tags: SwiftUI Basic
author: Bruno Zhong
excerpt_separator: <!--more-->
---

## Projects

- [About Me](#about-me): Create a simple "About Me" project using a `ScrollView`.

<!--more-->

### About Me

We'll be creating a simple "About Me" project.

1. Copy/paste some boilerplate code. How about this?

ContentView.swift
```swift
import SwiftUI

struct ContentView: View {
  var body: some View {
    VStack {
      Image(systemName: "globe")
        .imageScale(.large)
        .foregroundColor(.accentColor)
      Text("Hello, world!")
    }
  }
}
```

MyApp.swift
```swift
import SwiftUI

@main
struct MyApp: App {
  var body: some Scene {
    WindowGroup {
      ContentView()
    }
  }
}
```

2. Change the `VStack` to a `ScrollView`.

ContentView.swift
```swift
import SwiftUI

struct ContentView: View {
  var body: some View {
    ScrollView {
      Image(systemName: "globe")
        .imageScale(.large)
        .foregroundColor(.accentColor)
      Text("Hello, world!")
    }
  }
}
```

Coming Soon!
