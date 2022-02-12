---
tags: V-Day App
author: Bruno
excerpt_seperator: <!--more-->
---

Happy Valentine's Day!

<!--more-->

We're going to create an app that can make Valentines for us. Luckily, I'm not *all* done with my app.

But first, let's go through a review.

## `ContentView.swift`

```swift
import SwiftUI

struct ContentView: View {
    var body: some View {
        NavigationView {
            ValentineList()
                .navigationTitle("Valentines")
        }
    }
}
```

You usually wouldn't include a ***`lot`*** in this file. (See how I added a lot of styling?)

What's a `ValentineList`?

## `ValentineList.swift`

```swift
import SwiftUI

struct ValentineList: View {
    @State private var valentines = [
        Valentine.example
    ]
    
    var body: some View {
        List {
            ForEach($valentines) { $valentine in // NOTE TO READER: This new syntax is valid, and was explained in a video about WWDC21.
                NavigationLink("Valentine to \(valentine.to)", destination: ValentineView(valentine: $valentine))
            }
        }
    }
}

struct ValentineList_Previews: PreviewProvider {
    static var previews: some View {
        ValentineList()
    }
}
```


