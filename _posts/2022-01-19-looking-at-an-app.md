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

## Using Types

> **Reference:**
> 
> Here's a handy image of `Run.swift` that you might need
> 
> ![Run.swift](https://brunozhon.github.io/swift-blog/684F14B2-7ACB-4304-92B5-EBB6EA887600.jpeg)

Here's `RunView.swift` along with some comments!

```swift
import SwiftUI

struct RunView: View {
    @Environment(\.editMode) var editMode
```
Wow, look at the attribute! It's a special one! A property wrapper, to be exact.

> **Check you Knowlege ✔️**
>
> 1. What do you think the attribute does?
> 2. Why is the First Letter Capitalized? *Hint: Think about the `Spacer` view in here. Why is it capitalized?*
>
> **Answers:**
> 1. The attribute lets us access certain values stored by the environment. (10 pts.)
> 2. The first letter is capitalized because its a property wrapper. (1,000,000,000,000,000,000,000,000,000,000 pts.)
```swift
    @Binding var run: Run
    
    var body: some View {
        VStack {
            HStack {
                Spacer()
                EditButton()
            }
            Image(systemName: "figure.walk")
                .imageScale(.large)
                .foregroundColor(run.iconColor)
            if editMode?.wrappedValue == .inactive {
                Text("\(run.name)")
                    .font(.title)
                Text("Miles ran: \(run.miles) miles")
            } else {
                TextField("Run Name", text: $run.name)
                    .font(.title)
                HStack {
                    Stepper(value: $run.miles, step: 0.1) {
                        Text("Miles ran:")
                    }
                    Text("\(run.miles) miles")
                        .redacted(reason: .privacy)
                }
                ColorPicker("Icon Color", selection: $run.iconColor)
            }
        }
    }
}

struct RunView_Previews: PreviewProvider {
    static var previews: some View {
        RunView(run: .constant(Run(
            name: "My Run", miles: 0.5, iconColor: .green
        )))
    }
}

```
