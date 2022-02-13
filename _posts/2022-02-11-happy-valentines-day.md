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

Before we go to `ValentineView.swift`, let's go to... 

## `Valentine.swift`

```swift
import Foundation

struct Valentine: Equatable, Hashable, Identifiable {
    enum ClosingStyle: String, Equatable, Hashable {
        case fromYourValentine = "From Your Valentine"
        case love = "Love"
    }
    var id = UUID()
    var to: String
    var from: String
    var body: String
    var closing: ClosingStyle
    
    static var example = Valentine(
        to: "My Love",
        from: "Saint Valentine",
        body: "...",
        closing: .fromYourValentine
    )
    static var blank = Valentine(
        to: "",
        from: "",
        body: "...",
        closing: .love
    )
}
```

What's a UUID? It's a **U**niversaly **U**nique **ID**entifier like `0139F0E7-4BEE-4C3E-9014-8178A6ADFB5A`. Here's a few runs of printed-out UUIDs:

```
1. DCDEBADB-2F54-43A6-BCDD-12C6B24B2A58
2. 2E775D9C-1606-4377-958C-B42ABAC5E150
3. 948AB659-977E-4F82-A327-C48D487116D5
4. FABA2037-347A-443B-8074-E8D236FF8FDE
5. 5FC20336-1361-4553-B860-60F547F1A170
```

It's unique! Test this snippet out in a playground:

```
import Foundation

var id = UUID()
print(id) // 91A39613-7CED-4B18-9698-29DAA901D1B5
```

See? But we can't go on talking about UUIDs. Sorry!

## `ValentineView.swift`

