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

1\. Copy/paste some boilerplate code. How about this?

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

2\. Change the `VStack` to a `ScrollView`.

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

3\. Add a placeholder image and change `"Hello, world!"` to... *something you would except to find at the top of an "About Me" page*.

ContentView.swift
```
import SwiftUI

struct ContentView: View {
  var body: some View {
    ScrollView {
      Image(systemName: "globe")
        .imageScale(.large)
        .foregroundColor(.accentColor)
      Text("About Bruno")
      Image("Placeholder")
    }
  }
}
```

4\. Apply a modifier that *allows the image to scale*, a modifier that *sets an imaginary frame*, and a modifier that *scales a `View` to fit a frame or its parent*.

```swift
import SwiftUI

struct ContentView: View {
  var body: some View {
    ScrollView {
      Image(systemName: "globe")
        .imageScale(.large)
        .foregroundColor(.accentColor)
      Text("About Bruno")
      Image("Placeholder")
        .resizable()
        .frame(width: 300, height: 300)
        .scaledToFit() // Or .aspectRatio(nil, contentMode: .fit)
    }
  }
}
```

> **Experiment:** 
> 
> 1. What if you change `.scaledToFit()` into `.scaledToFill()`
> 2. What if you remove the `.scaledToFit()` modifier?
> 3. What if you remove the `.resizable()` modifier?
> 4. What if you remove the `.frame(width: 300, height: 300)` modifier?

Coming Soon!
