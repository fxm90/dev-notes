# iOS Dev-Notes 🗒 🚀

My personal collection of tips, tricks, and patterns I've learned during iOS development so far and do not want to forget.

Feedback is always welcome! Feel free to reach out 👋

## Table of Contents

[\#65 – Tracking geometry changes in SwiftUI](#65--tracking-geometry-changes-in-swiftui)\
[\#64 – Responding to enabled state in a custom `ButtonStyle`](#64--responding-to-enabled-state-in-a-custom-buttonstyle)\
[\#63 – Animating text color in SwiftUI](#63--animating-text-color-in-swiftui)\
[\#62 – Creating custom localized date formats](#62--creating-custom-localized-date-formats)\
[\#61 – Animate `isHidden` in a `UIStackView`](#61--animate-ishidden-in-a-uistackview)\
[\#60 – Making types expressible by literals](#60--making-types-expressible-by-literals)\
[\#59 – Customizing toggles with `ToggleStyle` in SwiftUI](#59--customizing-toggles-with-togglestyle-in-swiftui)\
[\#58 – Determining a view's size with Auto Layout](#58--determining-a-views-size-with-auto-layout)\
[\#57 – Decode array while filtering invalid entries](#57--decode-array-while-filtering-invalid-entries)\
[\#56 – Codable cheat sheet](#56--codable-cheat-sheet)\
[\#55 – Respecting safe areas in SwiftUI while extending backgrounds](#55--respecting-safe-areas-in-swiftui-while-extending-backgrounds)\
[\#54 – Rendering basic HTML tags in SwiftUI's Text](#54--rendering-basic-html-tags-in-swiftuis-text)\
[\#53 – Combining Text views in SwiftUI](#53--combining-text-views-in-swiftui)\
[\#52 – Animate a `UITableView` reload](#52--animate-a-uitableview-reload)\
[\#51 – Integrating Redux with SwiftUI](#51--integrating-redux-with-swiftui)\
[\#50 – Exploring Combine: A couple of practical examples](#50--exploring-combine-a-couple-of-practical-examples)\
[\#49 – Effortless unit conversion with `Measurement`](#49--effortless-unit-conversion-with-measurement)\
[\#48 – `FloatingPoint` protocol](#48--floatingpoint-protocol)\
[\#47 – Wait for multiple async tasks to complete](#47--wait-for-multiple-async-tasks-to-complete)\
[\#46 – Snapshot testing](#46--snapshot-testing)\
[\#45 – Pin a view to its superview](#45--pin-a-view-to-its-superview)\
[\#44 – Animating with custom timing curves](#44--animating-with-custom-timing-curves)\
[\#43 – Testing delegate protocols in Swift](#43--testing-delegate-protocols-in-swift)\
[\#42 – Xcode multi-cursor editing](#42--xcode-multi-cursor-editing)\
[\#41 – Create a dynamic color for light- and dark mode](#41--create-a-dynamic-color-for-light--and-dark-mode)\
[\#40 – Derive reuse identifiers from `UITableViewCell` type](#40--derive-reuse-identifiers-from-uitableviewcell-type)\
[\#39 – Prefer "for .. in .. where" over `filter()` followed by `forEach {}`](#39--prefer-for--in--where-over-filter-followed-by-foreach-)\
[\#38 – Lightweight observable implementation](#38--lightweight-observable-implementation)\
[\#37 – Running test cases in a playground](#37--running-test-cases-in-a-playground)\
[\#36 – Displaying `WKWebView` loading progress with `UIProgressView`](#36--displaying-wkwebview-loading-progress-with-uiprogressview)\
[\#35 – Destructure tuples](#35--destructure-tuples)\
[\#34 – Avoid huge if statements](#34--avoid-huge-if-statements)\
[\#33 – Compare dates in tests](#33--compare-dates-in-tests)\
[\#32 – Understand the strong reference behavior of `Timer` targets](#32--understand-the-strong-reference-behavior-of-timer-targets)\
[\#31 – Initialize `DateFormatter` with formatting options](#31--initialize-dateformatter-with-formatting-options)\
[\#30 – Mapping latitude and longitude to X and Y on a coordinate system](#30--mapping-latitude-and-longitude-to-x-and-y-on-a-coordinate-system)\
[\#29 – Encapsulation](#29--encapsulation)\
[\#28 – Remove `UITextView` default padding](#28--remove-uitextview-default-padding)\
[\#27 – Name that color](#27--name-that-color)\
[\#26 – Structure classes using `// MARK: -`](#26--structure-classes-using--mark--)\
[\#25 – Structure test cases](#25--structure-test-cases)\
[\#24 – Avoid forced unwrapping](#24--avoid-forced-unwrapping)\
[\#23 – Guard against division by zero](#23--guard-against-division-by-zero)\
[\#22 – Animate `alpha` and update `isHidden` accordingly](#22--animate-alpha-and-update-ishidden-accordingly)\
[\#21 – Define a custom notification](#21--define-a-custom-notification)\
[\#20 – Overriding `UIStatusBarStyle` the elegant way](#20--overriding-uistatusbarstyle-the-elegant-way)\
[\#19 – Log extension on `String` using Swift literal expressions](#19--log-extension-on-string-using-swift-literal-expressions)\
[\#18 – Use Gitmoji for commit messages](#18--use-gitmoji-for-commit-messages)\
[\#17 – Initialize a constant conditionally](#17--initialize-a-constant-conditionally)\
[\#16 – Why `viewDidLoad` can be called before initialization completes](#16--why-viewdidload-can-be-called-before-initialization-completes)\
[\#15 – Capture iOS Simulator video](#15--capture-ios-simulator-video)\
[\#14 – Xcode shortcuts](#14--xcode-shortcuts)\
[\#13 – Handle optionals in test cases](#13--handle-optionals-in-test-cases)\
[\#12 – Safe access to an element at index](#12--safe-access-to-an-element-at-index)\
[\#11 – Check whether a value is part of a given range](#11--check-whether-a-value-is-part-of-a-given-range)\
[\#10 – Use `compactMap` to filter `nil` values](#10--use-compactmap-to-filter-nil-values)\
[\#09 – Prefer `Set` instead of `Array` for unordered lists without duplicates](#09--prefer-set-instead-of-array-for-unordered-lists-without-duplicates)\
[\#08 – Adding and removing child view controllers](#08--adding-and-removing-child-view-controllers)\
[\#07 – Animate image change on `UIImageView`](#07--animate-image-change-on-uiimageview)\
[\#06 – Change `CALayer` without animation](#06--change-calayer-without-animation)\
[\#05 – Override `layerClass` to reduce the total amount of layers](#05--override-layerclass-to-reduce-the-total-amount-of-layers)\
[\#04 – Handle notifications in test cases](#04--handle-notifications-in-test-cases)\
[\#03 – Use `didSet` on outlets to set up components](#03--use-didset-on-outlets-to-set-up-components)\
[\#02 – A readable way to check whether a value exists in a set of candidates (`isAny(of:)`)](#02--a-readable-way-to-check-whether-a-value-exists-in-a-set-of-candidates-isanyof)\
[\#01 – Memory management: `weak self` in closures vs. tasks](#01--memory-management-weak-self-in-closures-vs-tasks)

## #65 – Tracking geometry changes in SwiftUI

📏 Starting in iOS 16, SwiftUI provides the `onGeometryChange(for:of:action:)` view modifier, which lets you respond to changes in a view’s geometry — such as its size or position.

In the example below, the width of a rounded rectangle automatically matches the width of a `Text` view. As the text’s layout changes, SwiftUI updates the rectangle in sync.

```swift
struct ContentView: View {

  @State
  private var textSize: CGSize = .zero

  var body: some View {
    VStack {
      Text("Hello World!")
        .onGeometryChange(for: CGSize.self, of: \.size) { textSize in
          self.textSize = textSize
        }

      RoundedRectangle(cornerRadius: 4)
        .frame(
          width: textSize.width,
          height: 8,
        )
        .foregroundStyle(.indigo)
    }
  }
}
```

The same approach can be used to track other geometry values, such as a **scroll position**. A complete example demonstrating **scroll offset tracking** is available here:

https://gist.github.com/fxm90/5bc949e4d6f2f56901b47250a25fc64d

## #64 – Responding to enabled state in a custom `ButtonStyle`

🎨 The `ButtonStyle` protocol makes it easy to define consistent, reusable button designs across your app, without repeating code.

However, there is one subtle detail: a `ButtonStyle` doesn’t have direct access to the `isEnabled` environment value.

When you need to adjust your styling based on whether a button is enabled, you can move that logic into a supporting `View`. Because views participate fully in SwiftUI’s environment system, they can read `@Environment(\.isEnabled)` and adapt accordingly.

Here’s one way to structure it:

```swift
struct PrimaryButtonStyle: ButtonStyle {
  func makeBody(configuration: Self.Configuration) -> some View {
    PrimaryButtonStyleView(configuration: configuration)
  }
}

private extension PrimaryButtonStyle {

  struct PrimaryButtonStyleView: View {

    // MARK: - Public Properties

    let configuration: ButtonStyle.Configuration

    // MARK: - Private Properties

    @Environment(\.isEnabled)
    private var isEnabled: Bool

    private var foregroundColor: Color {
      guard isEnabled else {
        return .gray
      }

      return configuration.isPressed
        ? .white.opacity(0.5)
        : .white
    }

    // MARK: - Render

    var body: some View {
      configuration.label
        .foregroundColor(foregroundColor)
    }
  }
}
```

In this approach, the style delegates its rendering to a view that reads from the environment. This allows the button’s appearance to automatically reflect its enabled state.

## #63 – Animating text color in SwiftUI

🎨 SwiftUI makes it easy to animate many visual properties. However, `foregroundColor(_:)` isn’t directly animatable.

When you need to smoothly transition text between colors, there’s a simple workaround.

Instead of animating `foregroundColor`, apply a neutral base color (such as `.white`) and animate the `colorMultiply(_:)` modifier. Because `colorMultiply` participates in SwiftUI’s animation system, the color transition becomes fluid and seamless.

```swift
struct AnimateTextColor: View {

  // MARK: - Private Properties

  @State
  private var textColor: Color = .red

  // MARK: - Render

  var body: some View {
    Text("Lorem Ipsum Dolor Sit Amet.")
      .foregroundColor(.white)
      .colorMultiply(textColor)
      .onTapGesture {
        withAnimation(.easeInOut) {
          textColor = .blue
        }
      }
  }
}
```

## #62 – Creating custom localized date formats

📝 When presenting dates in your app, it's important to consider the user's locale. Month names, day order, and punctuation can vary significantly across regions. Rather than hard-coding a format string, you can generate one dynamically using [`dateFormat(fromTemplate:options:locale:)`](<https://developer.apple.com/documentation/foundation/dateformatter/dateformat(fromtemplate:options:locale:)>).

This approach lets the system determine the correct ordering and formatting for a given locale, based on a template like `MMMd`.

Here’s a convenient `Date` extension that wraps this behavior:

```swift
extension Date {

  /// Returns a localized string representation of the date,
  /// generated from the provided date format template and locale.
  ///
  /// - Parameters:
  ///   - template: A date format template (for example, "MMMd" or "yMMMMd").
  ///   - locale: The locale that determines the final date format.
  ///
  /// - Returns: A locale-aware formatted date string.
  func localizedString(from template: String, for locale: Locale) -> String {
    let dateFormatter = DateFormatter()
    dateFormatter.locale = locale

    if let dateFormat = DateFormatter.dateFormat(
      fromTemplate: template,
      options: 0,
      locale: locale
    ) {
      dateFormatter.dateFormat = dateFormat
    }

    return dateFormatter.string(from: self)
  }
}
```

#### Example

```swift
let template = "MMMd"
let now: Date = .now

let usLocale = Locale(identifier: "en_US")
print("United States:", now.localizedString(from: template, for: usLocale))
// United States: Oct 1

let deLocale = Locale(identifier: "de")
print("Germany:", now.localizedString(from: template, for: deLocale))
// Germany: 1. Okt.
```

## #61 – Animate `isHidden` in a `UIStackView`

🧙‍♀️ When working with `UIStackView`, animating the visibility of an arranged subview is straightforward.

Because a stack view automatically manages the layout of its arranged subviews, changes to the `isHidden` property can be animated seamlessly alongside layout updates.

For example, setting `isHidden` to `true` removes the view from the stack’s layout, allowing the remaining content to smoothly adjust its position.

```swift
UIView.animate(withDuration: 0.3) {
  viewInsideStackView.isHidden = true
  stackView.layoutIfNeeded()
}
```

By calling `layoutIfNeeded()` inside the animation block, the stack view animates to its updated layout, producing a smooth slide-out effect as the hidden view collapses within the stack.

## #60 – Making types expressible by literals

🖌 Swift includes a family of protocols that allow your custom types to be initialized using familiar literal syntax. This makes APIs feel natural, expressive, and consistent with the language itself.

For example, many standard library types conform to literal protocols:

```swift
let int = 0                       // ExpressibleByIntegerLiteral
let string = "Hello World!"       // ExpressibleByStringLiteral
let array = [0, 1, 2, 3, 4, 5]    // ExpressibleByArrayLiteral
let dictionary = ["Key": "Value"] // ExpressibleByDictionaryLiteral
let boolean = true                // ExpressibleByBooleanLiteral
```

A complete list of these protocols can be found in the documentation: [Initialization with Literals](https://developer.apple.com/documentation/swift/initialization-with-literals)

#### Creating custom literal-convertible types

Literal protocols are especially powerful when applied to your own types. By conforming to them, you enable readable initialization without sacrificing type safety.

Consider a simple `StorageKey` type:

```swift
struct StorageKey {
  let path: String
}
```

By conforming to `ExpressibleByStringLiteral` and `ExpressibleByStringInterpolation`, you can initialize `StorageKey` directly from string literals:

```swift
extension StorageKey: ExpressibleByStringLiteral, ExpressibleByStringInterpolation {
  init(stringLiteral path: String) {
    self.init(path: path)
  }
}
```

Now you can create instances using natural string syntax:

```swift
let storageKey: StorageKey = "/cache/"
```

And because it also supports string interpolation:

```swift
let username = "f.mau"
let storageKey: StorageKey = "/users/\(username)/cache"
```

#### Applying the pattern to URL

This approach can also improve ergonomics when working with existing types. For example, you can make `URL` conform to `ExpressibleByStringLiteral`:

````swift
extension URL: ExpressibleByStringLiteral {
  /// Initializes a URL from a string literal.
  ///
  /// Example:
  /// ```
  /// let url: URL = "https://felix.hamburg"
  /// ```
  public init(stringLiteral value: StaticString) {
    guard let url = URL(string: "\(value)") else {
      fatalError("⚠️ – Failed to create a valid URL instance from `\(value)`.")
    }

    self = url
  }
}
````

In this case, the conformance is intentionally limited to `ExpressibleByStringLiteral`, using `StaticString`. This ensures only compile-time string literals are accepted, avoiding runtime failures from dynamic string interpolation.

Based on:

- [Defining static URLs using string literals](https://www.swiftbysundell.com/tips/defining-static-urls-using-string-literals/)
- [Making types expressible by string interpolation](https://www.swiftbysundell.com/tips/making-types-expressible-by-string-interpolation/)
- [Expressible literals in Swift explained by 3 useful examples](https://www.avanderlee.com/swift/expressible-literals/)

## #59 – Customizing toggles with `ToggleStyle` in SwiftUI

🎨 SwiftUI provides a [ToggleStyle](https://developer.apple.com/documentation/swiftui/togglestyle) protocol, giving you full control over the appearance and interaction of a [Toggle](https://developer.apple.com/documentation/swiftui/toggle).

By adopting this protocol, you can design a toggle that aligns perfectly with your app’s visual language — whether that’s a refined switch, a checkbox, or something entirely unique.

#### Understanding `makeBody(configuration:)`

When you create a custom toggle style, you take responsibility for rendering and managing its visual state.

The required method, `makeBody(configuration:)`, provides a configuration value that includes:

- `configuration.isOn`: A Boolean that reflects the current state of the toggle.
- `configuration.label`: The view representing the toggle’s label.

Because you are defining the entire visual representation, you are also responsible for clearly communicating the toggle’s state to the user.

#### Examples of custom toggle styles

The following examples demonstrate custom `ToggleStyle` implementations, complete with screenshots in the comments:

- **A fully configurable toggle style for SwiftUI**\
  https://gist.github.com/fxm90/6afe050ac331d8f719029d7fec87e961
- **A toggle style for SwiftUI, making the Toggle look like a checkbox**\
  https://gist.github.com/fxm90/b56d537d9fb8bf20d573a45367e18c4f

## #58 – Determining a view's size with Auto Layout

↔️ Auto Layout doesn’t just position your views — it can also tell you how large they need to be.

When you want to determine the optimal size of a view based on its constraints, `UIView` provides the [`systemLayoutSizeFitting(_:)`](<https://developer.apple.com/documentation/uikit/uiview/systemlayoutsizefitting(_:)>) method.

For example, if you know the width of a view and want to determine the height required to fit its content, you can specify a fixed horizontal dimension and allow Auto Layout to calculate the vertical one:

```swift
let size = view.systemLayoutSizeFitting(
  CGSize(width: view.bounds.width, height: UIView.layoutFittingCompressedSize.height),
  withHorizontalFittingPriority: .required,
  verticalFittingPriority: .fittingSizeLevel
)
```

In this configuration:

- The horizontal fitting priority is set to `.required`, ensuring the width remains fixed.
- The vertical fitting priority is set to `.fittingSizeLevel`, allowing Auto Layout to determine the height that best fits the content.

## #57 – Decode array while filtering invalid entries

🪄 Ideally, an API has a well-defined interface and the app knows exactly which data to expect. However, there are cases when you can't be 100% sure about a response.

Consider fetching a list of flights for an airport. If one flight includes an incorrectly formatted departure date, you likely don’t want the entire response to fail decoding. Instead, you may prefer to keep the valid flights and discard the problematic entry.

To support this pattern, you can introduce a lightweight wrapper that attempts to decode a value while allowing individual failures to resolve to `nil`. This enables partial success when decoding collections of potentially unreliable data.

```swift
/// A wrapper that attempts to decode a value of type `Base` but gracefully degrades to `nil` if decoding fails.
///
/// `FailableDecodable` is useful when working with unreliable or partially-invalid data (e.g. third-party APIs)
/// where you want decoding to continue even if a single field is malformed.
///
/// - Warning: Because decoding errors are swallowed, this can mask schema or data issues.
///            Use sparingly and only when partial failure is acceptable.
///
/// Source: <https://stackoverflow.com/a/46369152/3532505>
struct FailableDecodable<Base: Decodable>: Decodable {

  /// The successfully decoded value, or `nil` if decoding failed.
  let base: Base?

  /// Attempts to decode `Base` from a single-value container.
  /// If decoding throws, the error is ignored and `base` is set to `nil`.
  init(from decoder: Decoder) throws {
    let container = try decoder.singleValueContainer()
    base = try? container.decode(Base.self)
  }
}
```

#### Example

In this example, we decode the array of `Flight`s as `FailableDecodable<Flight>`. This way, invalid elements don't cause the entire decoding to fail — only the `base` property will be `nil` on failure.

Afterwards, we use `compactMap(\.base)` to filter out entries where `base` is `nil`.

```swift
/// Data Model
struct Flight: Decodable {
  let number: String
  let departure: Date
}

/// HTTP Client Method
func fetchDepartures(for url: URL) async throws -> [Flight] {
  let (data, _) = try await URLSession.shared.data(from: url)

  let decoder = JSONDecoder()
  decoder.dateDecodingStrategy = .iso8601

  let decodedFlights = try decoder.decode([FailableDecodable<Flight>].self, from: data)
  return decodedFlights.compactMap(\.base)
}
```

## #56 – Codable cheat sheet

📝 Working with JSON data is a fundamental part of modern app development. Swift's `Codable` protocol provides a type-safe way to convert between your Swift data types and external representations like JSON.

Paul Hudson has created a helpful [Codable cheat sheet](https://www.hackingwithswift.com/articles/119/codable-cheat-sheet) that walks through the essentials — from simple encoding and decoding to handling more advanced scenarios.

## #55 – Respecting safe areas in SwiftUI while extending backgrounds

📲 In SwiftUI, it’s common to want a view’s content to respect the device’s safe areas while allowing the background to extend to the edges of the screen. This pattern ensures your layout feels natural on all devices, from iPhones with notches to iPads with rounded corners.

Here’s a simple example:

```swift
struct FullScreenBackgroundView: View {
  var body: some View {
    Text("Hello, World!")
      .frame(maxWidth: .infinity, maxHeight: .infinity, alignment: .bottom)
      .background(
        Color.red.ignoresSafeArea()
      )
  }
}

#Preview {
  FullScreenBackgroundView()
}
```

In this example:

- The `Text` view respects the safe area, staying visible and readable.
- The `Color.red` background ignores safe area insets, creating a full-bleed background effect.

This approach is a great way to combine a polished, safe content layout with immersive backgrounds that span the entire screen.

## #54 – Rendering basic HTML tags in SwiftUI's Text

🖌 With **iOS 15**, `Text` now fully embraces `AttributedString`, bringing rich text capabilities and [Markdown support](https://developer.apple.com/documentation/foundation/attributedstring) directly into your views.

This makes it simple to display content that originates from HTML. By mapping basic HTML tags to Markdown, you can render styled text and even interactive hyperlinks in SwiftUI.

For a practical example, see this [SwiftUI+HTML.swift](https://gist.github.com/fxm90/abd949e4258050f2f3cd80118024e5bd) snippet, which demonstrates converting HTML to an `AttributedString` ready for SwiftUI’s `Text`.

## #53 – Combining Text views in SwiftUI

🧙‍♀️ In SwiftUI, you can **concatenate multiple `Text` views** using the `+` operator. This allows you to style each portion of text independently while presenting them as a single cohesive line.

```swift
Text("Hello ")
  .foregroundStyle(.red)
+
Text("World")
  .foregroundStyle(.green)
+
Text("!")
```

Each `Text` segment retains its own modifiers, giving you fine-grained control over appearance and style.

**Note:** The plus operator for Text concatenation has been deprecated in iOS 26, and Apple recommends using text interpolation instead:

```swift
Text(
  """
  \(Text("Hello ")
    .foregroundStyle(.red))\
  \(Text("World")
    .foregroundStyle(.green))\
  \(Text("!"))
  """
)
```

## #52 – Animate a `UITableView` reload

🚀 Refreshing the contents of a `UITableView` can be enhanced with smooth animations using `UIView` transitions.

By invoking [`tableView.reloadData()`](<https://developer.apple.com/documentation/uikit/uitableview/reloaddata()>) inside the animation block of [`UIView.transition(with:duration:options:animations:completion:)`](<https://developer.apple.com/documentation/uikit/uiview/transition(with:duration:options:animations:completion:)>), you can create a seamless, crossfade effect when updating table view cells.

```swift
UIView.transition(
  with: tableView,
  duration: 0.3,
  options: .transitionCrossDissolve,
  animations: { self.tableView.reloadData() }
)
```

You can experiment with any of the [`UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions) to achieve different transition effects.

Source: <https://stackoverflow.com/a/13261683>

## #51 – Integrating Redux with SwiftUI

🔄 SwiftUI’s declarative design makes state management a core part of building robust apps. In this example, we explore how to implement a simple Redux-style architecture **directly in SwiftUI**, without relying on external frameworks.

Check out the full gist here: [Redux.swift](https://gist.github.com/fxm90/c3f74f2c695377b17b1f80cf96a31114)

You can easily copy the code into an Xcode Playground to experiment with state flow and see Redux in action. This is a great way to understand unidirectional data flow in SwiftUI.

## #50 – Exploring Combine: A couple of practical examples

🧪 Combine provides a declarative Swift API for processing values over time, making it easier to work with asynchronous events. To help you get started, here are two practical examples that illustrate common Combine patterns:

- [PassthroughSubject vs. CurrentValueSubject](https://gist.github.com/fxm90/fcb2eb9d92655889d549e7f57168a0fb)\
  This example demonstrates the difference between [`PassthroughSubject`](https://developer.apple.com/documentation/combine/passthroughsubject) and [`CurrentValueSubject`](https://developer.apple.com/documentation/combine/currentvaluesubject), two foundational building blocks in Combine for emitting and observing values over time.
- [Bridging Delegates to Combine](https://gist.github.com/fxm90/8b6c9753f12fcf19991f6c3f0cd635d3)\
  Here, you’ll see how to convert a traditional delegate pattern into Combine publishers, using `CLLocationManagerDelegate` as an example. This pattern makes it easier to integrate existing APIs with the reactive Combine framework.

Feel free to copy the code to a playground and get your hands dirty with Combine 🙂

## #49 – Effortless unit conversion with `Measurement`

🔁 With iOS 10 and later, Swift provides a unified and type-safe way to work with measurements through [`Measurement`](https://developer.apple.com/documentation/foundation/measurement).

Whether you’re dealing with angles, areas, durations, speeds, temperatures, volumes, or other dimensions, `Measurement` makes conversions straightforward and expressive.

For example, using `Measurement<UnitAngle>` we can refactor the computed property shown in note #48 into a method that converts between any [`UnitAngle`](https://developer.apple.com/documentation/foundation/unitangle):

```swift
extension BinaryFloatingPoint {
  /// Converts a value from one `UnitAngle` to another.
  func converted(from fromUnit: UnitAngle, to toUnit: UnitAngle) -> Self {
    let valueAsDouble = Double(self)
    let convertedValue = Measurement(value: valueAsDouble, unit: fromUnit)
      .converted(to: toUnit)
      .value

    return Self(convertedValue)
  }
}
```

This approach leads to a very clean call site:

```swift
let cameraBearing: CLLocationDegrees = 180
let bearingInRadians = cameraBearing.converted(from: .degrees, to: .radians)
```

## #48 – `FloatingPoint` protocol

🎲 Swift’s protocols are incredibly powerful. By extending the `FloatingPoint` protocol, you can seamlessly add functionality to all floating-point types (e.g. `Double`, `Float`, `CGFloat`) without writing repetitive code.

For example, converting degrees to radians is a common task in graphics and animations. With a simple protocol extension, you can make this conversion available on any floating-point value:

```swift
extension FloatingPoint {
  /// Converts an angle in degrees to radians.
  var degreesToRadians: Self {
    self * .pi / 180
  }
}

let angleDouble: Double = 90
let angleFloat: Float = 180
let angleCGFloat: CGFloat = 270

print("Double in radians:", angleDouble.degreesToRadians)
print("Float in radians:", angleFloat.degreesToRadians)
print("CGFloat in radians:", angleCGFloat.degreesToRadians)
```

## #47 – Wait for multiple async tasks to complete

⏰ Apps frequently need to fetch data from multiple sources before updating the interface.

### Using DispatchGroup

`DispatchGroup` allows you to track a collection of asynchronous tasks and receive a callback once they’ve all completed.

```swift
let dispatchGroup = DispatchGroup()

var profile: Profile?
dispatchGroup.enter()
profileService.fetchProfile {
  profile = $0
  dispatchGroup.leave()
}

var friends: Friends?
dispatchGroup.enter()
profileService.fetchFriends {
  friends = $0
  dispatchGroup.leave()
}

dispatchGroup.notify(queue: .main) {
  guard
    let profile = profile,
    let friends = friends
  else {
    return
  }

  print("We've downloaded the user profile together with all friends!")
}
```

### Modern alternatives (iOS 13 and later)

Starting with iOS 13, Swift offers more expressive tools for handling asynchronous coordination.

#### Combining publishers with `CombineLatest`

If your APIs return Combine publishers, you can use `Publishers.CombineLatest` to wait until each publisher emits at least one value.

```swift
let fetchProfileFuture = profileService.fetchProfile()
let fetchFriendsFuture = profileService.fetchFriends()

cancellable = Publishers.CombineLatest(fetchProfileFuture, fetchFriendsFuture)
  .sink { profile, friends in
    print("We've downloaded the user profile together with all friends!")
  }
```

`CombineLatest` produces a tuple containing the latest values from both publishers once each has emitted.

#### Structured concurrency with `async let`

Swift’s structured concurrency model provides an even more concise and readable approach. With `async let`, you can start multiple asynchronous operations concurrently and await their results together.

```swift
Task {
  async let profileTask = profileService.fetchProfile()
  async let friendsTask = profileService.fetchFriends()

  let (profile, friends) = await(profileTask, friendsTask)
  print("We've downloaded the user profile together with all friends!")
}
```

This approach keeps related asynchronous work clearly scoped and eliminates the need for manual bookkeeping. It’s the preferred solution for modern Swift codebases targeting iOS 13 and later.

## #46 – Snapshot testing

📸 Snapshot tests are a powerful way to ensure your interface looks exactly the way you expect — and continues to do so over time.

As your app evolves, even small changes can introduce subtle visual regressions. Snapshot testing helps you catch those changes early by capturing a reference image (or representation) of your UI and comparing it against future test runs.

With the open-source [SnapshotTesting](https://github.com/pointfreeco/swift-snapshot-testing) library from [Point-Free](https://github.com/pointfreeco), you can verify snapshots of `UIView`, `UIViewController`, `UIImage`, and even `URLRequest` instances.

## #45 – Pin a view to its superview

⚓️ A common pattern in Auto Layout is anchoring a view so it fully spans its container. With a small extension on `UIView`, you can make this intent reusable throughout your project.

This helper method pins a view’s edges to its superview with optional spacing, reducing boilerplate while keeping your layout code easy to read.

```swift
extension UIView {
  /// Constrains the view’s edges to match its superview’s edges.
  /// - Parameter spacing: Optional inset applied to all edges. Defaults to 0.
  func fillToSuperview(spacing: CGFloat = 0) {
    guard let superview = superview else { return }

    translatesAutoresizingMaskIntoConstraints = false
    NSLayoutConstraint.activate([
      topAnchor.constraint(equalTo: superview.topAnchor, constant: spacing),
      leadingAnchor.constraint(equalTo: superview.leadingAnchor, constant: spacing),

      superview.bottomAnchor.constraint(equalTo: bottomAnchor, constant: spacing),
      superview.trailingAnchor.constraint(equalTo: trailingAnchor, constant: spacing)
    ])
  }
}
```

## #44 – Animating with custom timing curves

🚀 Starting with iOS 10, `UIViewPropertyAnimator` gives you precise, interruptible control over your animations.

While the built-in timing curves such as `.easeInOut` work beautifully in many cases, there are times when you want to craft a more distinctive motion.

By using the [`init(duration:timingParameters:)`](<https://developer.apple.com/documentation/uikit/uiviewpropertyanimator/init(duration:timingparameters:)>) initializer, you can provide your own object conforming to `UITimingCurveProvider` and define a fully custom timing curve.

One convenient way to do this is with `UICubicTimingParameters`, which lets you specify Bézier control points for fine-tuned motion.

If you’re looking for inspiration, resources like [Easings.net](https://easings.net) provide a variety of well-known timing curves that can help you achieve a specific feel.

For example, here’s how you could implement an “easeInBack” curve — a motion that briefly moves in the opposite direction before accelerating forward:

```swift
extension UICubicTimingParameters {
  static let easeInBack = UICubicTimingParameters(
    controlPoint1: CGPoint(x: 0.6, y: -0.28),
    controlPoint2: CGPoint(x: 0.735, y: 0.045)
  )
}

final class CustomTimingAnimationViewController: UIViewController {

  // ...

  func userDidTapButton() {
    let animator = UIViewPropertyAnimator(
      duration: 1.0,
      timingParameters: UICubicTimingParameters.easeInBack
    )

    animator.addAnimations {
      // Update constraints, transforms, alpha, or other animatable properties.
      // For example:
      // self.someConstraint?.isActive = false
      // self.someOtherConstraint?.isActive = true
      // self.view.layoutIfNeeded()
    }

    animator.startAnimation()
  }
}
```

Because `UIViewPropertyAnimator` is interruptible and fully controllable, you can pause, reverse, or scrub through the animation as needed.

## #43 – Testing delegate protocols in Swift

🧪 Delegation is a common Swift design pattern, enabling **one-to-one communication between objects** in a clean and modular way.

When building apps, it's essential to ensure that delegate callbacks are triggered correctly. One approach is to use a **mock** in your tests. By implementing an enum to track invoked methods, you can verify that e.g. your view models interact with their delegates exactly as expected.

Explore a practical example of this approach in action: [Testing a Delegate Protocol with a Mock](https://gist.github.com/fxm90/106fd802f869d3d259d672d0416b66fa)

## #42 – Xcode multi-cursor editing

🏃‍ Since **Xcode 10**, the Source Editor has included **multi-cursor support**, making it easier than ever to edit multiple locations in your code simultaneously. This feature lets you insert, delete, or modify code across several lines at once, streamlining repetitive edits and improving your workflow.

To add additional cursors, simply use:

```
shift + control + click
shift + control + ↑
shift + control + ↓
```

## #41 – Create a dynamic color for light- and dark mode

🎨 Using the helper in [UIColor+MakeDynamicColor.swift](https://gist.github.com/fxm90/fd217b463222afd6eabcb006fb26d92e), we can define a custom `UIColor` that adapts automatically to the current `userInterfaceStyle`.

The color resolves itself at runtime, seamlessly matching Light or Dark Mode as the interface appearance changes.

On systems earlier than **iOS 13**, the implementation gracefully defaults to the provided **light variant**, ensuring consistent behavior across all supported OS versions.

## #40 – Derive reuse identifiers from `UITableViewCell` type

🧙‍♀️ When working with table views, reuse identifiers are an essential detail. Defining them as string literals, however, introduces unnecessary duplication and the risk of subtle typos.

You can eliminate both by deriving the reuse identifier directly from the cell’s type. The following extension adds a static identifier to `UITableViewCell` that reflects the class name automatically:

```swift
extension UITableViewCell {
  static var identifier: String {
    String(describing: self)
  }
}
```

With this in place, registering and dequeuing cells becomes simpler and more consistent.

Registering a cell:

```swift
tableView.register(CustomTableViewCell.self, forCellReuseIdentifier: CustomTableViewCell.identifier)
```

Dequeuing a cell:

```swift
let cell = tableView.dequeueReusableCell(withIdentifier: CustomTableViewCell.identifier)
```

## #39 – Prefer "for .. in .. where" over `filter()` followed by `forEach {}`

🎢 In performance-sensitive code, a `for-in-where` loop is often more efficient than chaining `filter()` with `forEach`, as it performs the conditional check during iteration rather than requiring an additional pass over the collection.

For example, instead of writing:

```swift
scooterList
  .filter { !$0.isBatteryEmpty }
  .forEach { scooter in
    // Operate on each scooter with remaining battery.
  }
```

you can express the same intent more efficiently using a `for-in-where` loop:

```swift
for scooter in scooterList where !scooter.isBatteryEmpty {
  // Operate on each scooter with remaining battery.
}
```

This approach avoids the creation of an intermediate collection and can be significantly faster when working with large arrays.

## #38 – Lightweight observable implementation

🕵️‍♂️ For a simple and lightweight observable implementation — suitable for UI bindings and similar use cases — refer to the [LightweightObservable](https://github.com/fxm90/LightweightObservable) framework (also available as a CocoaPod).

**Update 2026:** Over time, Apple has introduced several frameworks that support reactive and asynchronous programming. Depending on your deployment target, consider adopting one of the following technologies:

- [Combine](https://developer.apple.com/documentation/combine) (iOS 13.0+)\
  A declarative Swift API for processing values over time.
- [Async Sequence](https://developer.apple.com/documentation/swift/asyncsequence) (iOS 13.0+)\
  A protocol that enables asynchronous iteration using Swift’s concurrency features.
- [Observation](https://developer.apple.com/documentation/Observation) (iOS 17.0+)\
  A modern observation system designed to integrate seamlessly with Swift.\
  In UIKit-based apps, you can respond to observation-driven changes by overriding the [`updateProperties()`](<https://developer.apple.com/documentation/uikit/uiviewcontroller/updateproperties()>) lifecycle method (iOS 26.0+).

## #37 – Running test cases in a playground

🧪 Swift Playgrounds are an easy way to explore ideas. As you prototype, it’s often useful to think through the expected behavior up front — or even take a test-driven approach from the start.

You can run `XCTest`-based test cases directly inside a playground by invoking the test suite explicitly. This makes it easy to validate behavior early, then move the code into your app or framework when it’s ready.

```swift
import XCTest

final class MyTestCase: XCTestCase {

  func testFooBarShouldNotBeEqual() {
    XCTAssertNotEqual("Foo", "Bar")
  }
}

MyTestCase.defaultTestSuite.run()
```

When you run the playground, the results of each test appear in the debug area.

#### Asynchronous tests

If your tests rely on asynchronous work, enable indefinite execution to allow the playground to continue running:

```swift
PlaygroundPage.current.needsIndefiniteExecution = true
```

This ensures that asynchronous expectations have time to complete before the playground exits.

**Note:** The Swift Testing framework is currently not supported in playgrounds.

## #36 – Displaying `WKWebView` loading progress with `UIProgressView`

🤖 To reflect the loading progress of a `WKWebView`, you can observe its `estimatedProgress` property and present the value using a `UIProgressView`.

The complete implementation is available in the following example: [WebViewExampleViewController.swift](https://gist.github.com/fxm90/50d6c73d07c4d9755981b9bb4c5ab931)

In this example, the progress view is positioned along the bottom edge of the navigation bar.

## #35 – Destructure tuples

🧙‍ When a tuple’s elements are named — such as `(firstName: String, lastName: String)` — you can decompose it into individual constants in a single, expressive statement.

```swift
let (firstName, lastName) = accountService.fullName()

print(firstName)
print(lastName)
```

## #34 – Avoid huge if statements

✨ Long conditional expressions can quickly become difficult to read and reason about — especially as a type grows more complex.

Consider the following example:

```swift
struct HugeDataObject {
  let category: Int
  let subCategory: Int

  // Imagine many additional properties,
  // making `Equatable` impractical in this case.
}

if hugeDataObject.category != previousDataObject.category ||
   hugeDataObject.subCategory != previousDataObject.subCategory {
  // ...
}

```

While functionally correct, the intent of this condition isn’t immediately obvious at the call site. Breaking the logic into named Boolean values makes the code more expressive and easier to scan:

```swift
let isDifferentCategory = hugeDataObject.category != previousDataObject.category
let isDifferentSubCategory = hugeDataObject.subCategory != previousDataObject.subCategory

if isDifferentCategory || isDifferentSubCategory {
  // ...
}
```

By naming each comparison, you communicate _why_ the condition exists — not just _how_ it’s computed.

For early-exit scenarios, `guard` can further clarify intent by moving the “happy path” out of the conditional:

```swift
let isDifferentCategory = hugeDataObject.category != previousDataObject.category
let isDifferentSubCategory = hugeDataObject.subCategory != previousDataObject.subCategory

let didChange = isDifferentCategory || isDifferentSubCategory
guard didChange else { return }

// Proceed knowing the data has changed
```

#### A note on evaluation

This pattern evaluates all conditions upfront. Unlike a single expression using `||` or `&&`, it does not short-circuit once the result is known.

If you have a **computationally expensive check**, it may be better to keep it as a **single statement** or check the **lightweight condition first with an early return** to avoid the expensive evaluation.

## #33 – Compare dates in tests

📆 `Date` stores time as a `Double` (seconds since a reference point). Because of floating-point precision, two logically equivalent dates can differ by a tiny fraction of a second, causing direct equality checks with `==` to fail unexpectedly.

Instead, compare their underlying time intervals with a small tolerance. The right tolerance depends on the context, but for most cases, 1 millisecond is a reasonable choice.

A shared helper keeps the tolerance consistent across your test suite:

```swift
private extension TimeInterval {
  static let oneMillisecond = 0.001
}
```

#### Using XCTest

```swift
func testDatesAreEqual() {
  // Given
  let dateA = Date()
  let dateB = Date()

  // When
  // ...

  // Then
  XCTAssertEqual(
    dateA.timeIntervalSince1970,
    dateB.timeIntervalSince1970,
    accuracy: .oneMillisecond,
  )
}
```

#### Using Swift Testing

```swift
@Test
func verifyDatesAreEqual() {
  // Given
  let dateA = Date()
  let dateB = Date()

  // When
  // ...

  // Then
  let diff = abs(dateA.timeIntervalSince1970 - dateB.timeIntervalSince1970)
  #expect(diff < .oneMillisecond)
}
```

## #32 – Understand the strong reference behavior of `Timer` targets

🔁 When you create a timer using `scheduledTimer(timeInterval:target:selector:userInfo:repeats:)`, the timer creates a **strong reference to the target** until the timer is invalidated. As a result, instances like the one below are never deallocated:

```swift
final class ClockViewModel {

  // MARK: - Private Properties

  weak var timer: Timer?

  // MARK: - Instance Lifecycle

  init(interval: TimeInterval = 1) {
    timer = Timer.scheduledTimer(
      timeInterval: interval,
      target: self,
      selector: #selector(timerDidFire),
      userInfo: nil,
      repeats: true
    )
  }

  deinit {
    print("⚠️ - This will never be called!")

    timer?.invalidate()
    timer = nil
  }

  // MARK: - Private Methods

  @objc
  private func timerDidFire() {
    // Perform work at the specified interval.
  }
}
```

At first glance, this may look surprising. The timer property is declared as weak, and although the timer retains its target, there is no retain cycle. The issue lies elsewhere.

According to the documentation for [`Timer`](https://developer.apple.com/documentation/foundation/timer):

> Timers work in conjunction with run loops. Run loops maintain strong references to their timers, so you don’t have to maintain your own strong reference to a timer after you have added it to a run loop.

And the documentation for [`init(timeInterval:target:selector:userInfo:repeats:)`](<https://developer.apple.com/documentation/foundation/timer/init(timeinterval:target:selector:userinfo:repeats:)>) further clarifies:

> **target:**\
> The timer maintains a strong reference to this object until it (the timer) is invalidated.

In other words, the run loop strongly retains the timer, and the timer strongly retains its target. As long as the timer remains valid, the view model remains alive.

Because `invalidate()` is called in `deinit`, and `deinit` is never reached, the timer is never invalidated.\
The object is effectively kept alive by the run loop.

#### Recommended approach

Starting in iOS 10, prefer the block-based API `scheduledTimer(withTimeInterval:repeats:block:)`. By capturing `self` weakly, you avoid this retention issue entirely:

```swift
init(interval: TimeInterval = 1.0) {
  timer = Timer.scheduledTimer(
    withTimeInterval: interval,
    repeats: true
  ) { [weak self] _ in
    self?.timerDidFire()
  }
}
```

For earlier system versions, consider using `DispatchSourceTimer` instead. A detailed discussion of this approach can be found in Daniel Galasko’s article: [A Background Repeating Timer in Swift](https://medium.com/@danielgalasko/a-background-repeating-timer-in-swift-412cecfd2ef9)

**Note:**
This behavior also applies to non-repeating timers. Even if a timer fires only once, its target will not be deallocated until the timer has fired or been invalidated.

## #31 – Initialize `DateFormatter` with formatting options

🚀 Basic formatting, which requires only setting `dateStyle` and `timeStyle`, can be achieved using the function [localizedString(from:dateStyle:timeStyle:)](https://developer.apple.com/documentation/foundation/dateformatter/1415241-localizedstring).

When you need additional customization, you can streamline configuration by initializing `DateFormatter` with a configuration closure. The following convenience initializer enables an expressive setup:

```swift
extension DateFormatter {
  convenience init(configure: (DateFormatter) -> Void) {
    self.init()

    configure(self)
  }
}
```

E.g. creating a formatter configured with localized date and time styles:

```swift
let dateFormatter = DateFormatter {
  $0.locale = .current
  $0.dateStyle = .long
  $0.timeStyle = .short
}
```

Or specify a custom date format:

```swift
let dateFormatter = DateFormatter {
  $0.dateFormat = "E, d. MMMM"
}
```

This pattern generalizes well to other formatter types, including [`DateComponentsFormatter`](https://developer.apple.com/documentation/foundation/datecomponentsformatter) and [`DateIntervalFormatter`](https://developer.apple.com/documentation/foundation/dateintervalformatter), providing a consistent and readable configuration style across Foundation.

Starting with **Swift 4**, we can use key paths instead of closures:

```swift
protocol Builder {}

extension Builder {
  func set<T>(_ keyPath: WritableKeyPath<Self, T>, to value: T) -> Self {
    var mutableCopy = self
    mutableCopy[keyPath: keyPath] = value

    return mutableCopy
  }
}

extension Formatter: Builder {}
```

This approach enables a chainable configuration style:

```swift
let dateFormatter = DateFormatter()
  .set(\.locale, to: .current)
  .set(\.dateStyle, to: .long)
  .set(\.timeStyle, to: .short)
```

Or configure a number formatter similarly:

```swift
let numberFormatter = NumberFormatter()
  .set(\.locale, to: .current)
  .set(\.numberStyle, to: .currency)
```

Based on: [Vadim Bulavin – KeyPath Based Builder](https://twitter.com/V8tr/status/1242846971188183047)

## #30 – Mapping latitude and longitude to X and Y on a coordinate system

🌍 When working with `CLLocationCoordinate2D`, it’s important to be clear about how geographic coordinates map onto a 2D coordinate system.

On a standard, north-up map:

- **Latitude maps to the Y-axis.**\
  Lines of latitude run east–west, but their values change as you move north or south. As a result, latitude corresponds to vertical movement along the Y-axis.

- **Longitude maps to the X-axis.**\
  Lines of longitude run north–south, but their values change as you move east or west. This aligns longitude with horizontal movement along the X-axis.

This can feel counterintuitive at first (especially since latitude lines are horizontal and longitude lines are vertical), but the key is to focus on which direction the values increase or decrease, not the orientation of the lines themselves.

The following graphics illustrate this relationship visually:

| Latitude                                     | Longitude                                       |
| :------------------------------------------- | :---------------------------------------------- |
| [![Latitude][latitude--thumbnail]][latitude] | [![Longitude][longitude--thumbnail]][longitude] |

#### Further iOS-related information

- [Displaying Maps](https://developer.apple.com/library/archive/documentation/UserExperience/Conceptual/LocationAwarenessPG/MapKit/MapKit.html)
- [CLLocationCoordinate2D](https://developer.apple.com/documentation/corelocation/cllocationcoordinate2d)

## #29 – Encapsulation

🚪 In a codebase that’s constantly evolving, maintaining strong encapsulation is essential. Clearly defined APIs help limit surface area, keeping implementation details private and reducing unintended coupling.

Even notification observers and outlets can be declared `private` when they’re not part of a type’s public contract.

```swift
final class KeyboardViewModel {

  // MARK: - Public Properties

  /// Boolean flag, whether the keyboard is currently visible.
  /// We assume that this property has to be accessed from the view controller,
  /// therefore we allow public read-access.
  private(set) var isKeyboardVisible = false

  // MARK: - Instance Lifecycle

  init(notificationCenter: NotificationCenter = .default) {
    notificationCenter.addObserver(
      self,
      selector: #selector(didReceiveUIKeyboardWillShowNotification),
      name: UIResponder.keyboardWillShowNotification,
      object: nil
    )

    notificationCenter.addObserver(
      self,
      selector: #selector(didReceiveUIKeyboardDidHideNotification),
      name: UIResponder.keyboardDidHideNotification,
      object: nil
    )
  }

  // MARK: - Private Methods

  @objc
  private func didReceiveUIKeyboardWillShowNotification(_: Notification) {
    isKeyboardVisible = true
  }

  @objc
  private func didReceiveUIKeyboardDidHideNotification(_: Notification) {
    isKeyboardVisible = false
  }
}
```

## #28 – Remove `UITextView` default padding

↔ The following code removes the default padding from a `UITextView`:

```swift
// This brings the left edge of the text to the left edge of the container
textView.textContainer.lineFragmentPadding = 0

// This causes the top of the text to align with the top of the container
textView.textContainerInset = .zero
```

Source: https://stackoverflow.com/a/18987810/3532505

You can achieve the same result directly in Interface Builder using **User Defined Runtime Attributes**. Add the following entries to your `UITextView`:

| Key Path                          | Type   | Value            |
| :-------------------------------- | :----- | :--------------- |
| textContainer.lineFragmentPadding | Number | 0                |
| textContainerInset                | Rect   | {{0, 0}, {0, 0}} |

## #27 – Name that color

🎨 While not iOS-specific, [Name That Color](http://chir.ag/projects/name-that-color/) is a helpful resource when you need a meaningful name for your Swift color constants. It automatically generates a descriptive name for any given hex color value.

## #26 – Structure classes using `// MARK: -`

🔖 Use `// MARK:` to organize your Swift files with named sections that appear in Xcode’s Jump Bar.

Adding a dash (`// MARK: -`) inserts a visual separator, making large files easier to scan and navigate.

```swift
final class StructuredViewController: UIViewController {

  // MARK: - Types

  typealias CompletionHandler = (Bool) -> Void

  // MARK: - Public Properties

  var completionHandler: CompletionHandler?

  // MARK: - Private Properties

  private let viewModel: StructuredViewModel

  // MARK: - Instance Lifecycle

  override init(nibName nibNameOrNil: String?, bundle nibBundleOrNil: Bundle?) {
    viewModel = StructuredViewModel()

    // ...

    super.init(nibName: nibNameOrNil, bundle: nibBundleOrNil)
  }

  deinit {
    // ...
  }

  // MARK: - View Lifecycle

  override func viewDidLoad() {
    // ...
  }

  // MARK: - Private Methods

  private func setupSubmitButton() {
    // ...
  }
}
```

## #25 – Structure test cases

⚠️ Organizing tests into `Given`, `When`, `Then` improves readability and helps with understanding complex tests.

- `Given` establishes the context by setting up preconditions, such as configuring mock objects or test data.
- `When` performs the action under test.
- `Then` verifies the outcome by asserting that the results match expectations.

#### Example when using XCTest

```swift
final class MapViewModelTestCase: XCTestCase {
  var locationServiceMock: LocationServiceMock!

  var viewModel: MapViewModel!
  var delegateMock: MapViewModelDelegateMock!

  override func setUp() {
    super.setUp()

    // ...
  }

  func testLocateUser() {
    // Given
    let userLocation = CLLocationCoordinate2D(
      latitude: 12.34,
      longitude: 56.78
    )
    locationServiceMock.userLocation = userLocation

    // When
    viewModel.locateUser()

    // Then
    XCTAssertEqual(delegateMock.focusedUserLocation.latitude, userLocation.latitude)
    XCTAssertEqual(delegateMock.focusedUserLocation.longitude, userLocation.longitude)
  }
}
```

#### Example when using Swift Testing

```swift
struct MapViewModelTestCase {
  let locationServiceMock: LocationServiceMock

  let viewModel: MapViewModel
  let delegateMock: MapViewModelDelegateMock

  init() {
    // ...
  }

  @Test
  func locateUser() {
    // Given
    let userLocation = CLLocationCoordinate2D(
      latitude: 12.34,
      longitude: 56.78
    )
    locationServiceMock.userLocation = userLocation

    // When
    viewModel.locateUser()

    // Then
    #expect(delegateMock.focusedUserLocation.latitude == userLocation.latitude)
    #expect(delegateMock.focusedUserLocation.longitude == userLocation.longitude)
  }
}
```

## #24 – Avoid forced unwrapping

> The only time you should be using implicitly unwrapped optionals is with @IBOutlets.
> In every other case, it is better to use a non-optional or regular optional property.
> Yes, there are cases in which you can probably "guarantee" that the property will never be `nil` when used,
> but it is better to be safe and consistent. Similarly, don't use force unwraps.

Source: https://github.com/linkedin/swift-style-guide

Using the patterns shown below, we can safely unwrap optionals or use an early return to stop further code execution when an optional is `nil`.

```swift
if let value = value {
  // Use the unwrapped value.
}
```

```swift
guard let value = value else {
  // Explain why execution cannot continue.
  return
}

// Use the unwrapped value.
```

By embracing optionals and handling them explicitly, you make failure states visible and your code more predictable.

## #23 – Guard against division by zero

💥 Before performing a division, ensure the divisor is nonzero. This avoids undefined behavior, and can prevent crashes or incorrect program output.

```swift
final class ImageViewController: UIViewController {

  // MARK: - Outlets

  @IBOutlet private var imageView: UIImageView!

  // MARK: - Private Methods

  func someMethod() {
    let bounds = imageView.bounds
    guard bounds.height > 0 else {
      // Avoid dividing by zero for calculating aspect ratio below.
      return
    }

    let aspectRatio = bounds.width / bounds.height
  }
}
```

## #22 – Animate `alpha` and update `isHidden` accordingly

🦋 This lightweight extension lets you animate a view’s `alpha` value while automatically managing its `isHidden` state: [fxm90/UIView+AnimateAlpha.swift](https://gist.github.com/fxm90/723b5def31b46035cd92a641e3b184f6)

## #21 – Define a custom notification

📚 When introducing custom notifications, adhere to established Cocoa naming conventions.

Notification names should be composed as follows:

> [Name of associated class] + [Did | Will] + [UniquePartOfName] + Notification

This pattern improves clarity, avoids collisions, and aligns with Apple’s APIs.

Source: [Coding Guidelines for Cocoa](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/CodingGuidelines/Articles/NamingIvarsAndTypes.html)

#### Defining the notification name

Define custom notifications by extending `Notification.Name`:

```swift
extension Notification.Name {
  static let AccountServiceDidLoginUser =
    Notification.Name("AccountServiceDidLoginUserNotification")
}
```

Using a static constant ensures the notification name is defined in one place and remains type-safe throughout your codebase.

#### Posting the notification

Post the notification from the owning type:

```swift
final class AccountService {

  func login() {
    NotificationCenter.default.post(
      name: .AccountServiceDidLoginUser,
      object: self
    )
  }
}
```

#### Objective-C interoperability

To make the notification available to Objective-C, extend `NSNotificationName`:

```swift
@objc
extension NSNotificationName {
  static let AccountServiceDidLoginUser =
    Notification.Name.AccountServiceDidLoginUser
}
```

The notification can then be posted from Objective-C:

```
[[NSNotificationCenter defaultCenter] postNotificationName:NSNotification.AccountServiceDidLoginUser
                                                    object:self];
```

**Note:** The `object` parameter should always refer to the sender of the notification. Use the `userInfo` dictionary to attach additional contextual data when needed.

## #20 – Overriding `UIStatusBarStyle` the elegant way

✌️ A clean way to manage the status bar appearance is to introduce a dedicated property and update the system whenever it changes.

By combining a custom property with a `didSet` observer, you can call `setNeedsStatusBarAppearanceUpdate()` to prompt UIKit to re-evaluate the status bar style and apply the new appearance.

This approach keeps state changes explicit, localized, and easy to reason about.

```swift
final class SomeViewController: UIViewController {

  // MARK: - Public Properties

  override var preferredStatusBarStyle: UIStatusBarStyle {
    customBarStyle
  }

  // MARK: - Private Properties

  private var customBarStyle: UIStatusBarStyle = .default {
    didSet {
      setNeedsStatusBarAppearanceUpdate()
    }
  }
}
```

## #19 – Log extension on `String` using Swift literal expressions

👌 Swift provides several built-in literal expressions that capture contextual information at the call site:

| Literal   | Type   | Value                                            |
| :-------- | :----- | :----------------------------------------------- |
| #file     | String | The name of the file in which it appears.        |
| #line     | Int    | The line number on which it appears.             |
| #column   | Int    | The column number in which it begins.            |
| #function | String | The name of the declaration in which it appears. |

Source: [Swift.org – Expressions](https://docs.swift.org/swift-book/ReferenceManual/Expressions.html)

These expressions are especially useful as default parameter values, since they are evaluated at the call site.

By combining this behavior with a [simple extension on `String`](https://gist.github.com/fxm90/08a187c5d6b365ce2305c194905e61c2), you can build a lightweight logging API that automatically captures file, function, and line information:

```swift
"Lorem Ipsum Dolor Sit Amet 👋".log(level: .info)
```

This produces output similar to the following:

> ℹ️ 2026-02-09 21:35:00.000 [String+Log.swift:59] viewDidLoad() - Lorem Ipsum Dolor Sit Amet 👋

If you need more flexibility, consider using Apple's unified logging system (`OSLog`) for production apps.

## #18 – Use Gitmoji for commit messages

😃 While not specific to iOS development, [gitmoji](https://gitmoji.dev/) provides a standardized set of emojis for commit messages — for example, `TICKET-NUMBER - ♻️ :: Description` (credit to [Martin Knabbe](https://twitter.com/martin_knabbe) for that pattern).

To streamline emoji insertion for each commit type, you can use this [Alfred workflow](https://github.com/ai0/alfred-gitmoji-workflow), which allows you to insert the appropriate emoji directly from the keyboard.

## #17 – Initialize a constant conditionally

👏 Swift makes it easy to initialize a `let` constant using conditional logic, while keeping your code clear and safe from unintended mutation.

```swift
let startCoordinate: CLLocationCoordinate2D
if let userCoordinate = userLocationService.userCoordinate, CLLocationCoordinate2DIsValid(userCoordinate) {
  startCoordinate = userCoordinate
} else {
  // We don't have a valid user location, so we fall back to Hamburg.
  startCoordinate = CLLocationCoordinate2D(
    latitude: 53.5582447,
    longitude: 9.647645
  )
}
```

This approach avoids using a `var` and prevents any accidental mutation of `startCoordinate` later on.

Starting from **Swift 5.9**, `if` and `switch` expressions allow an even more concise approach:

```swift
let startCoordinate = if let userCoordinate = userLocationService.userCoordinate, CLLocationCoordinate2DIsValid(userCoordinate) {
  userCoordinate
} else {
  // We don't have a valid user location, so we fall back to Hamburg.
  CLLocationCoordinate2D(
    latitude: 53.5582447,
    longitude: 9.647645
  )
}
```

## #16 – Why `viewDidLoad` can be called before initialization completes

⚡️ Be aware that `viewDidLoad()` may be invoked if you access `self.view` from within a view controller’s initializer.

At that point, the view hierarchy has not yet been loaded. However, the view property is guaranteed to return a non-`nil` value. To satisfy that guarantee, UIKit loads the view immediately, which in turn triggers `viewDidLoad()` — even though initialization has not yet completed.

As a result, code in `viewDidLoad()` may run earlier than expected if `self.view` is accessed during initialization.

#### Example:

```swift
final class SomeViewController: UIViewController {

  // MARK: - Instance Lifecycle

  override init(nibName nibNameOrNil: String?, bundle nibBundleOrNil: Bundle?) {
    super.init(nibName: nibNameOrNil, bundle: nibBundleOrNil)

    view.isHidden = true

    print("`\(#function)` did finish!")
  }

  required init?(coder aDecoder: NSCoder) {
    super.init(coder: aDecoder)

    view.isHidden = true

    print("`\(#function)` did finish!")
  }

  // MARK: - View Lifecycle

  override func viewDidLoad() {
    super.viewDidLoad()

    print("`\(#function)` did finish!")
  }
}
```

The code will output log statements in the following order:

```
`viewDidLoad()` did finish!
`init(nibName:bundle:)` did finish!
```

Source: https://stackoverflow.com/a/5808477

## #15 – Capture iOS Simulator video

📹 Starting with Xcode 12.5, the iOS Simulator includes built-in support for capturing screenshots and recording video.

- Press **⌘ + R** to start or stop a screen recording.
- Press **⌘ + S** to capture a screenshot.

These features are available directly in the Simulator app and remove the need to use the `xcrun simctl` command-line utility for basic capture workflows.

For more advanced use cases, such as configuring the simulator environment, the `simctl` command-line tool remains available.

For example, you can **override the status bar time** to produce consistent screenshots or recordings:

```
xcrun simctl status_bar booted override --time '9:41'
```

## #14 – Xcode shortcuts

🏃‍♂️ If you spend a lot of time in Xcode, a few well-chosen keyboard shortcuts can save you a lot of time. Here are some essential shortcuts that make everyday development more fluid.

#### Navigation & Search

- **⌘ + ⇧ + O**\
  Open Quickly lets you instantly search across your project for files, classes, methods, symbols, and more.

- **⌘ + ⇧ + J**\
  Highlights the currently open file in the Project Navigator. This is especially useful when working in large or modular projects.

- **⌘ + L**
  Jump directly to a specific line number. Ideal when reviewing logs, stack traces, or collaborating in code reviews.

- **⌘ + ⇧ + F**
  Search across your entire project for text matches, with powerful filtering options.

#### Editing & Refactoring

- **⌘ + ⌃ + E**\
  Select all occurrences within the current scope. A useful shortcut for local refactoring.

- **⌘ + ⌥ + /**\
  Insert a structured documentation comment template, making it easy to document APIs with consistency.

- **⌃ + M**\
  Format arguments to multiple lines.

- **⌃ + ⇧ + Click**\
  Create multiple cursors for simultaneous editing across different lines. (See also [\#42 – Xcode multi-cursor editing](#42--xcode-multi-cursor-editing))

#### Build, Run & Test

- **⌘ + R**\
  Build and run your app.

- **⌘ + B**\
  Build without running — useful for quick validation.

- **⌘ + U**\
  Run your test suite.

- **⌃ + ⌥ + ⌘ + G**\
  Repeat your most recent test or run action, whether it was a single test or an entire test class.

#### SwiftUI & Previews

- **⌘ + ⌥ + Enter**\
  This toggles the SwiftUI preview.

## #13 – Handle optionals in test cases

✅ Using `XCTUnwrap`, we can safely unwrap optionals in test cases. If the optional is `nil`, only the current test case fails, but the app does not crash and all other test cases continue to run.

In the example below, we initialize a view model with a list of bookings. The method `findBooking(byUUID:)` returns an optional, because an invalid identifier might be passed. Using `XCTUnwrap`, we can safely unwrap the result.

#### Example when using XCTest

```swift
final class BookingViewModelTestCase: XCTestCase {

  func test_findBookingByUUID_shouldReturnCorrectBooking() throws {
    // Given
    let mockedBooking = Booking(uuid: "some-uuid")
    let viewModel = BookingViewModel(bookings: [mockedBooking])

    // When
    let receivedBooking = try XCTUnwrap(
      viewModel.findBooking(byUUID: "some-uuid")
    )

    // Then
    XCTAssertEqual(receivedBooking, mockedBooking)
  }
}
```

#### Example when using Swift Testing

In Swift Testing, we can achieve similar behavior using the `#require` macro.

```swift
struct BookingViewModelTestCase {

  @Test
  func findBookingByUUID_shouldReturnCorrectBooking() throws {
    // Given
    let mockedBooking = Booking(uuid: "some-uuid")
    let viewModel = BookingViewModel(bookings: [mockedBooking])

    // When
    let receivedBooking = try #require(
      viewModel.findBooking(byUUID: "some-uuid")
    )

    // Then
    #expect(receivedBooking == mockedBooking)
  }
}
```

## #12 – Safe access to an element at index

⛑ Using the range operator, we can create an `Array` extension that safely returns an element at the specified index, or `nil` if the index is out of bounds.

```swift
extension Array {
  subscript(safe index: Index) -> Element? {
    let isValidIndex = (0 ..< count).contains(index)
    guard isValidIndex else {
      return nil
    }

    return self[index]
  }
}

let fruits = ["Apple", "Banana", "Cherries", "Kiwifruit", "Orange", "Pineapple"]

let banana = fruits[safe: 1]
let pineapple = fruits[safe: 5]

// Does not crash, but contains nil.
let invalid = fruits[safe: 7]
```

## #11 – Check whether a value is part of a given range

💡 Instead of writing verbose range checks like `x >= 10 && x <= 100`, Swift allows you to use the pattern match operator (`~=`) or the `contains(_:)` method for clearer, more readable code.

#### Using the pattern match operator

```swift
let statusCode = 200

let isSuccessStatusCode = 200 ... 299 ~= statusCode
let isRedirectStatusCode = 300 ... 399 ~= statusCode
let isClientErrorStatusCode = 400 ... 499 ~= statusCode
let isServerErrorStatusCode = 500 ... 599 ~= statusCode
```

#### Using `contains(_:)` (often more readable)

```swift
let statusCode = 200

let isSuccessStatusCode = (200 ... 299).contains(statusCode)
let isRedirectStatusCode = (300 ... 399).contains(statusCode)
let isClientErrorStatusCode = (400 ... 499).contains(statusCode)
let isServerErrorStatusCode = (500 ... 599).contains(statusCode)
```

## #10 – Use `compactMap` to filter `nil` values

🎛 When working with collections in Swift, it’s common to encounter optional values.

Rather than manually unwrapping or filtering them, use `compactMap` to transform a collection while automatically discarding any `nil` values.

```swift
struct Product {
  let name: String
  let price: Double?
}

let products = [
  Product(name: "MacBook Air", price: 999.99),
  Product(name: "Mouse", price: nil),
  Product(name: "Keyboard", price: 79.99),
  Product(name: "Monitor", price: nil),
  Product(name: "USB Cable", price: 12.99),
]

// Extract only products with valid prices.
let availablePrices = products.compactMap(\.price)

// Output: [999.99, 79.99, 12.99]
print(availablePrices)

// Output: Total value: $1092.97
let totalValue = availablePrices.reduce(0, +)
print("Total value: $\(totalValue)")
```

## #09 – Prefer `Set` instead of `Array` for unordered lists without duplicates

👫 **Advantage over `Array`:**

- Constant lookup time O(1), since a `Set` stores its members based on hash value.

**Disadvantage compared to `Array`:**

- No guaranteed order.
- Cannot contain duplicate values.
- All stored elements must conform to the `Hashable` protocol.

For further examples and use cases, refer to ["The power of sets in Swift" (by John Sundell)](https://medium.com/@johnsundell/the-power-of-sets-in-swift-57be8b223da0).

## #08 – Adding and removing child view controllers

👶 This `UIViewController` extension provides a reusable API for adding and removing child view controllers, including lifecycle calls and full-size layout constraints.

```swift
extension UIViewController {

  /// Inserts a child view controller and installs its view in the hierarchy.
  func insert(_ child: UIViewController) {
    guard child.parent == nil else { return }

    addChild(child)

    child.view.translatesAutoresizingMaskIntoConstraints = false
    view.addSubview(child.view)

    NSLayoutConstraint.activate([
      child.view.leadingAnchor.constraint(equalTo: view.leadingAnchor),
      child.view.trailingAnchor.constraint(equalTo: view.trailingAnchor),
      child.view.topAnchor.constraint(equalTo: view.topAnchor),
      child.view.bottomAnchor.constraint(equalTo: view.bottomAnchor),
    ])

    child.didMove(toParent: self)
  }

  /// Removes a child view controller and its view from the hierarchy.
  func remove(_ child: UIViewController) {
    guard child.parent === self else { return }

    child.willMove(toParent: nil)
    child.view.removeFromSuperview()
    child.removeFromParent()
  }
}
```

The constraint setup pins the child’s view to all four edges of its parent and can be **further extracted into a `UIView` extension** if this pattern is used more broadly.

See [\#45 – Pin a view to its superview](#45--pin-a-view-to-its-superview) for more details on what this looks like.

## #07 – Animate image change on `UIImageView`

✍️ When updating the image of a `UIImageView`, a subtle cross-dissolve transition creates a smooth, polished effect. By using `.transitionCrossDissolve`, you can seamlessly animate between images with just a few lines of code:

```swift
extension UIImageView {
  func updateImageWithTransition(_ image: UIImage?, duration: TimeInterval) {
    UIView.transition(
      with: self,
      duration: duration,
      options: .transitionCrossDissolve
    ) {
      self.image = image
    }
  }
}
```

## #06 – Change `CALayer` without animation

👨‍🎨 `CALayer` has a default implicit animation duration of [0.25 seconds](<https://developer.apple.com/documentation/quartzcore/calayer/add(_:forkey:)>). The following extension allows you to update layer properties instantly, without triggering these implicit animations:

```swift
extension CALayer {
  final class func performWithoutAnimation(_ actionsWithoutAnimation: () -> Void) {
    CATransaction.begin()
    CATransaction.setAnimationDuration(0.0)

    actionsWithoutAnimation()

    CATransaction.commit()
  }
}
```

## #05 – Override `layerClass` to reduce the total amount of layers

```swift
override class var layerClass: AnyClass {
  return CAGradientLayer.self
}
```

> By overriding 'layerClass' you can tell UIKit what CALayer class to use for a UIView's backing layer.
> That way you can reduce the amount of layers, and don't have to do any manual layout.
> [John Sundell](https://twitter.com/johnsundell/status/1000099872580816897)

This is e.g. useful for adding a linear gradient behind an image. This way, we could change the gradient color based on the time of day, without bundling multiple images in the app.

![Example][overwrite-layer-class]

You can see the full code for the example in my gist for the [Vertical Gradient Image View](https://gist.github.com/fxm90/9604b0a067af46f68b80c6968736558d).

## #04 – Handle notifications in test cases

📬 When working with `NotificationCenter`, you often want to make sure the right notifications are posted. Here’s a quick way to test them.

- [XCTest – Assert notification (not) triggered](https://gist.github.com/fxm90/23dc7debc5ee8245237c08e5af8679bc)
- [XCTest – Use custom notification center in test case and assert notification (not) triggered](https://gist.github.com/fxm90/3c6f146ed977100d21f0a1f3e7bb37a2)

## #03 – Use `didSet` on outlets to set up components

👏 Using `didSet` on `@IBOutlet`s is a neat trick to configure your view components (declared in a storyboard or XIB) in a concise and readable manner:

```swift
final class ExampleViewController: UIViewController {

  // MARK: - Outlets

  @IBOutlet private var button: UIButton! {
    didSet {
      button.setTitle(viewModel.normalTitle, for: .normal)
      button.setTitle(viewModel.disabledTitle, for: .disabled)
    }
  }
}
```

## #02 – A readable way to check whether a value exists in a set of candidates (`isAny(of:)`)

✨ A lightweight `Equatable` extension that improves readability when checking whether a value matches one of several candidates. This pattern was popularized by [John Sundell](https://twitter.com/johnsundell/status/943510426586959873).

```swift
extension Equatable {
  func isAny(of candidates: Self...) -> Bool {
    candidates.contains(self)
  }
}
```

#### Example:

```swift
enum Device {
  case iPhone7
  case iPhone8
  case iPhoneX
  case iPhone11
}

let device: Device = .iPhoneX

// Before
let hasSafeAreas = [.iPhoneX, .iPhone11].contains(device)

// After
let hasSafeAreas = device.isAny(of: .iPhoneX, .iPhone11)
```

## #01 – Memory management: `weak self` in closures vs. tasks

🚸 To prevent retain cycles, closures commonly capture `self` weakly. However, the implementation differs between traditional closures and modern Swift Concurrency.

#### Escaping closures

For escaping completion handlers, capture `self` weakly to avoid retain cycles. Then, promote it to a strong reference for the duration of the closure’s execution.

Since Swift 5.7, this can be expressed using the shorthand optional binding syntax.

```swift
documentService.fetch { [weak self] document in
    // Creates a strong reference for the duration of this closure.
    guard let self else { return }

    updateUI(document)
}
```

#### Swift concurrency (`Task`)

Inside a `Task`, capturing `self` is implicit. You don’t need to explicitly write `self.` to reference instance members — but `self` is still strongly retained for the lifetime of the task.

That distinction becomes important for long-running or suspended tasks.

##### Avoid early unwrapping in long-running tasks

```swift
Task { [weak self] in
  // `self` is retained strongly until the task completes.
  guard let self else { return }

  let document = await documentService.fetch()
  updateUI(document)
}
```

Although `self` is captured weakly, unwrapping it at the beginning creates a strong reference that remains alive until the entire task finishes.

If the task is long-running, `self` (e.g. a view controller) will be kept in memory even after it should have been deallocated.

##### Prefer late or conditional access

To allow `self` to be released while the task is suspended, defer unwrapping until the moment you need it. Or use a conditional access.

```swift
Task { [weak self, documentService] in
  let document = await documentService.fetch()

  // `self` may deallocate while the fetch is in progress.
  self?.updateUI(document)
}
```

##### Long-lived tasks and async sequences

When working with long-running loops or `AsyncSequence` values, re-evaluate the existence of `self` on each iteration. This ensures `self` can be released between iterations.

```swift
Task { [weak self] in
  for await value in stream {
    guard let self else {
      // Exit the loop when `self` has been deallocated.
      break
    }

    process(value)
  }
}
```

[overwrite-layer-class]: Assets/overwrite-layer-class.jpg
[latitude]: Assets/latitude.jpg
[latitude--thumbnail]: Assets/latitude--thumbnail.jpg
[longitude]: Assets/longitude.jpg
[longitude--thumbnail]: Assets/longitude--thumbnail.jpg
