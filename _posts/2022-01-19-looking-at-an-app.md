---
author: Bruno Zhong
tags: App SwiftUI
excerpt_separator: <!--more-->
---

Let's look at an app called Runs, which I made myself. [This is the link to download the app](https://brunozhon.github.io/swift-blog/Runs.swiftpm.zip)!

So, let's get started! First stop: `MyApp.swift`!

<!--more-->

## `MyApp.swift`

```swift
import SwiftUI // 1

@main // 2
struct MyApp: App {
    var body: some Scene {
        WindowGroup { // 3
            ContentView() // 4
        }
    }
}
```

1. On the first line, look at `import SwiftUI`. SwiftUI is a framework.
2. Also, note the use of an attribute called `main`. The attribute says, "This is *now* the entry point for code."
3. The `WindowGroup` is a structure conforming to `Scene` that defines a group of windows.
4. Inside the `WindowGroup` lies the `ContentView`. It is the root for *most* applications. And by the way, the next stop is...
> **ProTip 💡:**
> 
> To see the base view, simply look at `MyApp.swift` (usually) and see the view inside `WindowGroup` (usually.) If the app file isn't `MyApp.swift`, then... **a)** Look at a file ending in `App`. If no luck, **b)** umm... no other idea can help, besides **c)** look at every file. If still no file, then **d)** I'm out of ideas. You should then **e)** **PANIC** because there's **NO** root file for the app! **Oh no!** Just kidding, there's a possibility that **f)** the app is *not* made with `SwiftUI`. It's made of `UIKit` or `AppKit`. Look for `import UIKit` or `import AppKit`. If none, then **g)** it's not an app. Possiblities include that it's a **I)** framework or **II)** package. If none, then **h)** ***PANIC!***

