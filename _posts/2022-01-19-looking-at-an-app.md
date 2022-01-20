---
author: Bruno Zhong
tags: App SwiftUI
excerpt_separator: <!--more-->
---

Let's look at an app called Runs, which I made myself. [This is the link to download the app](https://brunozhon.github.io/swift-blog/Runs.swiftpm.zip)!

So, let's get started! First stop: `MyApp.swift`!

**Vocabulary:**
- <span id="framework" name="framework">Framework: "A framework is a hierarchical directory that encapsulated shared resources ..., and reference documentation in a single package." (Apple Developer)</span> [Back (Step 1 at `MyApp.swift`)](#back-1)
- <span id="attribute" name="attribute">Attribute: "An attribute provides additional information about the declaration or type. For example, the `discardableResult` attribute on a function declaration indicates that ... the compiler shouldn't generate a warning if the return value is unused." (Swift Documentation)</span>

<!--more-->

## `MyApp.swift`

```swift
import SwiftUI // 1

@main // 2
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
    }
}
```

1. <span id="back-1" name="back-1">On the</span> first line, look at `import SwiftUI`. SwiftUI is a [*framework*](#framework).
2. <span id="back-2" name="back-2">Also, </span>note the use of an [*attribute*](#attribute) called `main`. The attribute says, "This is the entry point for code, not the defaults."
