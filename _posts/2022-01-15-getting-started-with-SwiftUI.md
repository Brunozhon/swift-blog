---
tags: SwiftUI Basic
author: Bruno Zhong
excerpt_separator: <!--more-->
---

## Projects

- [About Me](#about-me): Create a simple "About Me" project using a `ScrollView`.

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

<!--more-->

3\. Add a placeholder image and change `"Hello, world!"` to... *something you would except to find at the top of an "About Me" page* and make it ***stand out***!

ContentView.swift
```swift
import SwiftUI

struct ContentView: View {
  var body: some View {
    ScrollView {
      Image(systemName: "globe")
        .imageScale(.large)
        .foregroundColor(.accentColor)
      Text("About Bruno")
        .font(.largeTitle)
      Image("Placeholder")
    }
  }
}
```

> **Sidenote:**
> 
> The different font types are:
> - `.largeTitle`
> - `.title`
> - `.title2`
> - `.title3`
> - `.body`
> - `.headline`
> - `.subheadline`
> - `.caption`
> - `.caption2`
>
> You can also create a custom one using `.custom(_:size:)` or `.custom(_:fixedSize:)`.
>
> ```swift
> Text("Hello, world!")
>   .font(
>     .custom("Helvetica", size: 10)
>   )
> ```

> **Experiment:**
>
> What if you change your font into something listed in the sidenote except `.largeTitle`? Which one suits you best? Use the one that suits you best.

4\. Apply a modifier that *allows the image to scale*, a modifier that *sets an imaginary frame*, and a modifier that *scales a `View` to fit a frame or its parent*.

ContentView.swift
```swift
import SwiftUI

struct ContentView: View {
  var body: some View {
    ScrollView {
      Image(systemName: "globe")
        .imageScale(.large)
        .foregroundColor(.accentColor)
      Text("About Bruno")
        .font(.largeTitle)
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

5\. Add a bio about yourself.

```swift
import SwiftUI

struct ContentView: View {
  var body: some View {
    ScrollView {
      Image(systemName: "globe")
        .imageScale(.large)
        .foregroundColor(.accentColor)
      Text("About Bruno")
        .font(.largeTitle)
      Image("Placeholder")
        .resizable()
        .frame(width: 300, height: 300)
        .scaledToFit()
      Text("Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus aliquam rhoncus justo, a luctus purus finibus non. Aenean porttitor sapien non lectus eleifend, vitae accumsan est rutrum. Interdum et malesuada fames ac ante ipsum primis in faucibus. In fringilla augue ipsum, sit amet fringilla quam maximus sit amet. Nunc varius nibh laoreet lacinia fringilla. Proin vel neque pharetra augue tristique commodo vel quis leo. Curabitur at ex ut neque condimentum faucibus sed non ante. Suspendisse gravida vehicula lorem eget suscipit. Ut nec erat lectus. Pellentesque dapibus enim nibh, quis convallis leo ultricies vel. Sed ultricies neque vel turpis posuere, quis dignissim purus ornare.")
    }
  }
}
```

6\. Create a new file called `BioView.swift`. Add your bio here, and remove it from `ContentView.swift`.

BioView.swift
```swift
import SwiftUI

struct BioView: View {
  var body: some View {
    Text("Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus aliquam rhoncus justo, a luctus purus finibus non. Aenean porttitor sapien non lectus eleifend, vitae accumsan est rutrum. Interdum et malesuada fames ac ante ipsum primis in faucibus. In fringilla augue ipsum, sit amet fringilla quam maximus sit amet. Nunc varius nibh laoreet lacinia fringilla. Proin vel neque pharetra augue tristique commodo vel quis leo. Curabitur at ex ut neque condimentum faucibus sed non ante. Suspendisse gravida vehicula lorem eget suscipit. Ut nec erat lectus. Pellentesque dapibus enim nibh, quis convallis leo ultricies vel. Sed ultricies neque vel turpis posuere, quis dignissim purus ornare.")
  }
}

struct BioView_Previews: PreviewProvider {
  static var previews: some View {
    BioView()
  }
}
```

ContentView.swift
```swift
import SwiftUI

struct ContentView: View {
  var body: some View {
    ScrollView {
      Image(systemName: "globe")
        .imageScale(.large)
        .foregroundColor(.accentColor)
      Text("About Bruno")
        .font(.largeTitle)
      Image("Placeholder")
        .resizable()
        .frame(width: 300, height: 300)
        .scaledToFit()
    }
  }
}
```

Coming Soon!
