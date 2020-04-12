# iOS Dev-Notes 🗒 🚀
My personal collections of things, tips & tricks I've learned during iOS development so far and do not want to forget.

I'm happy for any feedback, so feel free to write me on [twitter](https://twitter.com/_fxm90).


## Table of contents

[\#49 - Convert units using `Measurement<UnitType>`](#49---convert-units-using-measurementunittype)\
[\#48 - `FloatingPoint` - Protocol](#48---floatingpoint---protocol)\
[\#47 - Wait for multiple async tasks to complete](#47---wait-for-multiple-async-tasks-to-complete)\
[\#46 - Snapshot testing](#46---snapshot-testing)\
[\#45 - Span subview to superview](#45---span-subview-to-superview)\
[\#44 - Animate a view using a custom timing function](#44---animate-a-view-using-a-custom-timing-function)\
[\#43 - How to test a delegate protocol](#43---how-to-test-a-delegate-protocol)\
[\#42 - Xcode multi-cursor editing](#42---xcode-multi-cursor-editing)\
[\#41 - Create a dynamic color for light- and dark mode](#41---create-a-dynamic-color-for-light--and-dark-mode)\
[\#40 - `UITableViewCell` extension that declares a static identifier](#40---uitableviewcell-extension-that-declares-a-static-identifier)\
[\#39 - Prefer "for .. in .. where"-loop over `filter()` and `forach {}`](#39---prefer-for--in--where-loop-over-filter-and-forach-)\
[\#38 - Lightweight observable implementation](#38---lightweight-observable-implementation)\
[\#37 - Run test cases in a playground](#37---run-test-cases-in-playground)\
[\#36 - Show progress of WKWebView in UIProgressBar](#36---show-progress-of-wkwebview-in-uiprogressbar)\
[\#35 - Destructure tuples](#35---destructure-tuples)\
[\#34 - Avoid huge if statements](#34---avoid-huge-if-statements)\
[\#33 - Compare dates in test cases](#33---compare-dates-in-test-cases)\
[\#32 - Be aware of the strong reference to the target of a timer](#32---be-aware-of-the-strong-reference-to-the-target-of-a-timer)\
[\#31 - Initialize `DateFormatter` with formatting options](#31---initialize-dateformatter-with-formatting-options)\
[\#30 - Map latitude and longitude to X and Y on a coordinate system](#30---map-latitude-and-longitude-to-x-and-y-on-a-coordinate-system)\
[\#29 - Encapsulation](#29---encapsulation)\
[\#28 - Remove `UITextView` default padding](#28---remove-uitextview-default-padding)\
[\#27 - Name that color](#27---name-that-color)\
[\#26 - Structure classes using `// MARK: - `](#26---structure-classes-using--mark--)\
[\#25 - Structure test cases](#25---structure-test-cases)\
[\#24 - Avoid forced unwrapping](#24---avoid-forced-unwrapping)\
[\#23 - Always check for possible dividing through zero](#23---always-check-for-possible-dividing-through-zero)\
[\#22 - Animate `alpha` and update `isHidden` accordingly](#22---animate-alpha-and-update-ishidden-accordingly)\
[\#21 - Create custom notification](#21---create-custom-notification)\
[\#20 - Override `UIStatusBarStyle` the elegant way](#20---override-uistatusbarstyle-the-elegant-way)\
[\#19 - Log extension on `String` using swift literal expressions](#19---log-extension-on-string-using-swift-literal-expressions)\
[\#18 - Use gitmoji for commit messages](#18---use-gitmoji)\
[\#17 - Initialize a constant based on a condition](#17---initialize-a-constant-based-on-a-condition)\
[\#16 - Why `viewDidLoad` might be called before `init` has finished](#16---why-viewdidload-might-be-called-before-init-has-finished)\
[\#15 - Capture iOS Simulator video](#15---capture-ios-simulator-video)\
[\#14 - Xcode open file in focused editor](#14---xcode-open-file-in-focused-editor)\
[\#13 - Handle optionals in test cases](#13---handle-optionals-in-test-cases)\
[\#12 - Safe access to an element at index](#12---safe-access-to-an-element-at-index)\
[\#11 - Check whether a value is part of a given range](#11---check-whether-a-value-is-part-of-a-given-range)\
[\#10 - Use `compactMap` to filter `nil` values](#10---use-compactmap-to-filter-nil-values)\
[\#09 - Prefer `Set` instead of array for unordered lists without duplicates](#09---prefer-set-instead-of-array-for-unordered-lists-without-duplicates)\
[\#08 - Remove all sub-views from `UIView`](#08---remove-all-sub-views-from-uiview)\
[\#07 - Animate image change on `UIImageView`](#07---animate-image-change-on-uiimageview)\
[\#06 - Change `CALayer` without animation](#06---change-calayer-without-animation)\
[\#05 - Override `layerClass` to reduce the total amount of layers](#05---override-layerclass-to-reduce-the-total-amount-of-layers)\
[\#04 - Handle notifications in test cases](#04---handle-notifications-in-test-cases)\
[\#03 - Use `didSet` on outlets to setup components](#03---use-didset-on-outlets-to-setup-components)\
[\#02 - Most readable way to check whether an array contains a value (`isAny(of:)`)](#02---most-readable-way-to-check-whether-an-array-contains-a-value-isanyof)\
[\#01 - Override `self` in escaping closure, to get a strong reference to `self`](#01---override-self-in-escaping-closure-to-get-a-strong-reference-to-self)\

## #49 - Convert units using `Measurement<UnitType>`
🔁 Starting from iOS 10 we can use [`Measurement`](https://developer.apple.com/documentation/foundation/measurement) to convert units like e.g. angles, areas, durations, speeds, temperature, volume and [many many more](https://developer.apple.com/documentation/foundation/dimension).

Using e.g. `Measurement<UnitAngle>` we can refactor the computed property shown in note #48 to a method, that allows us to convert between any [`UnitAngle`](https://developer.apple.com/documentation/foundation/unitangle):

```swift
extension BinaryFloatingPoint {
    func converted(from fromUnit: UnitAngle, to toUnit: UnitAngle) -> Self {
        let selfAsDouble = Double(self)
        let convertedValueAsDouble = Measurement(value: selfAsDouble, unit: fromUnit)
            .converted(to: toUnit)
            .value

        return type(of: self).init(convertedValueAsDouble)
    }
}
```

Furthermore this approach leads to a very clean call side:

```swift
let cameraBearing: CLLocationDegrees = 180
cameraBearing.converted(from: .degrees, to: .radians)
```

## #48 - `FloatingPoint` - Protocol
🎲 Ever needed an extension on all floating point datatypes, e.g. `Double`, `Float` or `CGFloat`? You can easily do this by extending the protocol `FloatingPoint`:

```swift 
extension FloatingPoint {
    var degToRad: Self {
        self * .pi / 180
    }
}

let double: Double = 90
let float: Float = 180
let cgFloat: CGFloat = 270

print("Double as radians", double.degToRad)
print("Float as radians", float.degToRad)
print("CGFloat as radians", cgFloat.degToRad)
```

## #47 - Wait for multiple async tasks to complete
⏰ Using a `DispatchGroup` we can wait for multiple async tasks to finish.

```swift
let dispatchGroup = DispatchGroup()
dispatchGroup.enter()
profileService.fetchProfile { profile in
    // ...
    dispatchGroup.leave()
}

dispatchGroup.enter()
profileService.fetchFriends { trips in
    // ...
    dispatchGroup.leave()
}

// We need to define the completion handler of our `DispatchGroup` with an unbalanced call to `enter()` and `leave()`,
// as otherwise it will be called immediately!
dispatchGroup.notify(queue: .main) {
  print("We've downloaded the user profile together with all friends!")
}
```

## 46 - Snapshot testing
📸 Snapshot tests are a very useful tool whenever you want to make sure your UI does not change unexpectedly. Using the library [SnapshotTesting](https://github.com/pointfreeco/swift-snapshot-testing) from [Point-Free](https://github.com/pointfreeco) you can easily start testing snapshots of your `UIView`, `UIViewController`, `UIImage` or even `URLRequest`.

## 45 - Span subview to superview 
⚓️ A small extension to span a subview to the anchors of its superview.

```swift
extension UIView {
    /// Adds layout constraints to top, bottom, leading and trailing anchors equal to superview.
    func fillToSuperview() {
        guard let superview = superview else { return }

        translatesAutoresizingMaskIntoConstraints = false
        NSLayoutConstraint.activate([
            topAnchor.constraint(equalTo: superview.topAnchor),
            bottomAnchor.constraint(equalTo: superview.bottomAnchor),

            leadingAnchor.constraint(equalTo: superview.leadingAnchor),
            trailingAnchor.constraint(equalTo: superview.trailingAnchor),
        ])
    }
}
```

## 44 - Animate a view using a custom timing function
🚀 Starting from iOS 10 we can use a `UIViewPropertyAnimator` to animates changes on views. Using the initializer `init(duration:timingParameters:)` we can pass a `UITimingCurveProvider`, which allows us to provide a custom timing function. You can find lots of these functions on [Easings.net](https://easings.net/). Using e.g. "[easeInBack](https://easings.net/#easeInBack)" your animation code could look like this:

```swift
extension UICubicTimingParameters {
    static let easeInBack = UICubicTimingParameters(controlPoint1: CGPoint(x: 0.6, y: -0.28),
                                                    controlPoint2: CGPoint(x: 0.735, y: 0.045))
}

class CustomTimingAnimationViewController: UIViewController {

    // ...

    func userDidTapButton() {
        let animator = UIViewPropertyAnimator(duration: 1.0,
                                              timingParameters: UICubicTimingParameters.easeInBack)

        animator.addAnimations {
            // Add your animation code here. E.g.:
            // `self.someConstraint?.isActive = false`
            // `self.someOtherConstraint?.isActive = true`
        }

        animator.startAnimation()
    }
}
```


## 43 - How to test a delegate protocol
🧪 Delegation is a common pattern whenever one object needs to communicate to another object (1:1 communication). In this gist I show you how to elegantly test a delegate-protocol from a view-model, by creating a mock and validate the invoked method(s) using an enum:
[Example on how to elegantly test a delegate protocol](https://gist.github.com/fxm90/106fd802f869d3d259d672d0416b66fa)


## 42 - Xcode multi-cursor editing
🏃‍ [Since Xcode 10](https://developer.apple.com/documentation/xcode_release_notes/xcode_10_release_notes/source_editor_release_notes_for_xcode_10) the Source Editor supports multi-cursor editing, allowing you to quickly edit multiple ranges of code at once. You can place additional cursors with the mouse via:
```
shift + control + click
shift + control + ↑
shift + control + ↓
```


## 41 - Create a dynamic color for light- and dark mode
🎨 Using the gist [UIColor+MakeDynamicColor.swift](https://gist.github.com/fxm90/fd217b463222afd6eabcb006fb26d92e) we can create a custom `UIColor`, that generates its color data dynamically based on the current `userInterfaceStyle`. Furthermore this method falls back to the `lightVariant` color for iOS versions prior to iOS 13.


## #40 - `UITableViewCell` extension that declares a static identifier
🧙‍♀️ Using the extension below we can automatically register and dequeue table view cells. It prevents typos and declaring a static string on each cell.

```swift
extension UITableViewCell {
    static var identifier: String {
        return String(describing: self)
    }
}
```

Register a cell:
```swift
tableView.register(CustomTableViewCell.self, forCellReuseIdentifier: CustomTableViewCell.identifier)
```

Dequeue a cell:
```swift
let cell = tableView.dequeueReusableCell(withIdentifier: CustomTableViewCell.identifier)
```


## #39 - Prefer "for .. in .. where"-loop over `filter()` and `forach {}`
🎢 In case you're iterating over a large array using a "for .. in .. where" loop is two times faster than combing `filter()` and `forach {}`, as it saves one iteration. So instead of writing:

```swift
scooterList
    .filter({ !$0.isBatteryEmpty })
    .forEach({ scooter in
        // Do something with each scooter, that still has some battery left.
    })
```

it's more efficient to write

```swift
for scooter in scooterList where !scooter.isBatteryEmpty {
    // Do something with each scooter, that still has some battery left.
}
```


## #38 - Lightweight observable implementation
🕵️‍♂️ ~~If you need a simple and lightweight observable implementation for e.g. UI bindings check out the following gist: [Observable.swift](https://gist.github.com/fxm90/26357043cfe174fabdeedd07d0f25314)~~

For re-usability reasons I've moved the code into a framework and released it as a CocoaPod. Please check out https://github.com/fxm90/LightweightObservable 🙂


## #37 - Run test cases in playground
🧪 - Playgrounds are an easy way to try out simple ideas. It is a good approach to directly think about the corresponding test-cases for the idea or even start the implementation test driven.

By calling `MyTestCase.defaultTestSuite.run()` inside the playground we can run a test-case and later copy it into our project.

```swift
import Foundation
import XCTest

class MyTestCase: XCTestCase {

    override func setUp() {
        super.setUp()
    }

    override func tearDown() {
        super.tearDown()
    }

    func testFooBarShouldNotBeEqual() {
        XCTAssertNotEqual("Foo", "Bar")
    }
}

MyTestCase.defaultTestSuite.run()
```
You can see the result of each test inside the debug area of the playground.


## #36 - Show progress of WKWebView in UIProgressBar
🤖 - In case you need to show the loading progress of a `WKWebView` on a `UIProgressBar`, please have a look at the sample code in the following gist: [WebViewExampleViewController.swift](https://gist.github.com/fxm90/50d6c73d07c4d9755981b9bb4c5ab931)

In the example, the `UIProgressBar` is attached to the bottom anchor of an `UINavigationBar` (see the method `setupProgressView()` for further layout details).


## #35 - Destructure tuples
🧙‍ Image having a tuple with the following properties: `(firstName: String, lastName: String)`. Using Swift we can destructure the tuple into two properties in just one line:

```swift
let (firstName, lastName) = accountService.fullName()

print(firstName)
print(lastName)
```

## #34 - Avoid huge if statements
✨ Instead of writing something like this:

```swift
struct HugeDataObject {
    let category: Int
    let subCategory: Int

    // Imagine lots of other properties, so we can't simply conform to `Equatable` ...
}

if hugeDataObject.category != previousDataObject.category || hugeDataObject.subCategory != previousDataObject.subCategory {
    // ...
}

```

We can split the long statement into several properties beforehand, to increase readability:

```swift
let isDifferentCategory = hugeDataObject.category != previousDataObject.category
let isDifferentSubCategory = hugeDataObject.subCategory != previousDataObject.subCategory

if isDifferentCategory || isDifferentSubCategory {
    // ...
}
```
Or use `guard` to do an early return:

```swift
let isDifferentCategory = hugeDataObject.category != previousDataObject.category
let isDifferentSubCategory = hugeDataObject.subCategory != previousDataObject.subCategory

let didChange = isDifferentCategory || isDifferentSubCategory
guard didChange else { return }
```

**Notice**: By using that pattern we do not skip further checks on failure (e.g. if we use `OR` in the statement and one condition returns `true` / we use `AND` in the statement and one condition returns `false`). So if you're having a load intensive method, it might be better to keep it as a single statement. Or, first check the "lighter" condition and then use an early return to prevent the load intensive method from being executed.

## #33 - Compare dates in test cases
📆 Small example on how to compare dates in tests.

```swift
func testDatesAreEqual() {
    // Given
    let dateA = Date()
    let dateB = Date()

    // When
    // ...

    // Then
    XCTAssertEqual(dateA.timeIntervalSince1970,
                   dateB.timeIntervalSince1970,
                   accuracy: 0.01)
}
```

## #32 - Be aware of the strong reference to the target of a timer
🔁 Creating a timer with the method `scheduledTimer(timeInterval:target:selector:userInfo:repeats:)` always creates a **strong reference to the target** until the timer is invalidated. Therefore, an instance of the following class will never be deallocated:

```swift
class ClockViewModel {
    // MARK: - Private properties

    weak var timer: Timer?

    // MARK: - Initializer

    init(interval: TimeInterval = 1.0) {
        timer = Timer.scheduledTimer(timeInterval: interval,
                                     target: self,
                                     selector: #selector(timerDidFire),
                                     userInfo: nil,
                                     repeats: true)
    }

    deinit {
        print("This will never be called 🙈")

        timer?.invalidate()
        timer = nil
    }

    // MARK: - Private methods

    @objc private func timerDidFire() {
        // Do something every x seconds here.
    }
}
```

But didn't we declare the variable `timer` as `weak`? So even though we have a strong reference from the timer to the view-model (via the target and selector), we should not have a retain cycle? Well that's true. The solution is mentioned in the [ documentation for the class "Timer"](https://apple.co/2yY9B1M)
> Timers work in conjunction with run loops. Run loops maintain strong references to their timers, so you don’t have to maintain your own strong reference to a timer after you have added it to a run loop.

and the [documentation for the method "timerWithTimeInterval"](https://apple.co/2CyIHB7)
> target: The timer maintains a strong reference to this object until it (the timer) is invalidated.

Therefore the run loop contains a strong reference to the view-model, as long as the timer is not invalidated. As we call `invalidate` inside the `deinit` of the view-model method, the timer gets never invalidated.

#### Workaround:
From iOS 10.0 we can use the method `scheduledTimer(withTimeInterval:repeats:block:)` instead and pass a `weak` reference to `self` in the closure, in order to prevent a retain cycle.

```swift
    init(interval: TimeInterval = 1.0) {
        timer = Timer.scheduledTimer(withTimeInterval: interval, repeats: true, block: { [weak self] _ in
            self?.timerDidFire()
        })
    }
```

For iOS version below 10.0, we can use `DispatchSourceTimer` instead. There is a great article from [Daniel Galasko](https://twitter.com/danielgalasko) on how to do that: [A Background Repeating Timer in Swift](https://medium.com/@danielgalasko/a-background-repeating-timer-in-swift-412cecfd2ef9)

**Notice:**
Even for non repeating timers, you should be aware of that strong reference, cause the corresponding object won't get deallocated until the timer has fired.


## #31 - Initialize `DateFormatter` with formatting options
🚀 Basic formatting, which requires only setting `dateStyle` and `timeStyle`, can be achieved with the class function [localizedString(from:dateStyle:timeStyle:)](https://developer.apple.com/documentation/foundation/dateformatter/1415241-localizedstring). 

In case you need further formatting options, the following extension allows you to directly initialize a `DateFormatter` with all available options:

```swift
extension DateFormatter {
    convenience init(configure: (DateFormatter) -> Void) {
        self.init()

        configure(self)
    }
}
```

Use it like this:

```swift
let dateFormatter = DateFormatter {
    $0.locale = .current
    $0.dateStyle = .long
    $0.timeStyle = .short
}
```
```swift
let dateFormatter = DateFormatter {
    $0.dateFormat = "E, d. MMMM"
}
```

Feel free to bring this extension to other formatters, like e.g. [DateComponentsFormatter](https://developer.apple.com/documentation/foundation/datecomponentsformatter) or [DateIntervalFormatter](https://developer.apple.com/documentation/foundation/dateintervalformatter), as well.

**Update:** Starting with Swift 4 we can use key-paths instead of closures:

```swift
protocol Builder {}

extension Builder where Self: AnyObject {
    func set<T>(_ keyPath: ReferenceWritableKeyPath<Self, T>, to value: T) -> Self {
        self[keyPath: keyPath] = value
        return self
    }
}

extension DateFormatter: Builder {}
extension NumberFormatter: Builder {}
```

Use it like this:

```swift
let dateFormatter = DateFormatter()
    .set(\.locale, to: .current)
    .set(\.dateStyle, to: .long)
    .set(\.timeStyle, to: .short)
```
```swift
let numberFormatter = NumberFormatter()
    .set(\.locale, to: .current)
    .set(\.numberStyle, to: .currency)
```

## #30 - Map latitude and longitude to X and Y on a coordinate system
🌍 Not really an iOS specific topic but something to keep in mind 😃
> On a standard north facing map, latitude is represented by horizontal lines, which go up and down (North and South) the Y axis. It's easy to think that since they are horizontal lines, they would be on the x axis, but they are not.
> So similarly, the X axis is Longitude, as the values shift left to right (East and West) along the X axis. Confusing for the same reason since on a north facing map, these lines are vertical.

https://gis.stackexchange.com/a/68856

The following graphics illustrate the quote above:

| Latitude                                     |  Longitude                                      |
| :--------------------------------------------|:------------------------------------------------|
| [![Latitude][latitude--thumbnail]][latitude] | [![Longitude][longitude--thumbnail]][longitude] |

#### Further iOS related information:
 - [Displaying Maps
](https://apple.co/2q61aNU)
 - [CLLocationCoordinate2D](https://apple.co/2O1bIYn)


## #29 - Encapsulation
🚪 Always try to make as many properties and methods private as possible. Other classes don't not need know how a specific algorithm is implemented. Furthermore, this avoids side-effects due to unwanted changes on properties.
Did you know, that even notification receivers can be marked as private?

```swift
class KeyboardViewModel {
    // MARK: - Public properties

    /// Boolean flag, whether the keyboard is currently visible.
    /// We assume that this property has to be accessed from the view controller, therefore we allow public read-access.
    private(set) var isKeyboardVisible = false

    // MARK: - Initializer

    init(notificationCenter: NotificationCenter = .default) {
        notificationCenter.addObserver(self,
                                       selector: #selector(didReceiveUIKeyboardWillShowNotification),
                                       name: UIResponder.keyboardWillShowNotification,
                                       object: nil)

        notificationCenter.addObserver(self,
                                       selector: #selector(didReceiveUIKeyboardDidHideNotification),
                                       name: UIResponder.keyboardDidHideNotification,
                                       object: nil)
    }

    // MARK: - Private methods

    @objc private func didReceiveUIKeyboardWillShowNotification(_: Notification) {
        isKeyboardVisible = true
    }

    @objc private func didReceiveUIKeyboardDidHideNotification(_: Notification) {
        isKeyboardVisible = false
    }
}
```


## #28 - Remove `UITextView` default padding
↔ With the following code the default padding from an `UITextView` can be removed:

```swift
// This brings the left edge of the text to the left edge of the container
textView.textContainer.lineFragmentPadding = 0

// This causes the top of the text to align with the top of the container
textView.textContainerInset = .zero
```
Source: https://stackoverflow.com/a/18987810/3532505

The above code can also be applied inside the interface builder within the "User Defined Runtime Attributes" section. Just add the following lines there:

| Key Path                          | Type   | Value                                           |
| :---------------------------------|:-------| :-----------------------------------------------|
| textContainer.lineFragmentPadding | Number | 0                                               |
| textContainerInset                | Rect   | {{0, 0}, {0, 0}}                                |


## #27 - Name that color
🎨 Not an iOS specific topic, but if your designer comes up with the 9th gray tone and you somehow need to find a proper name inside your code, check out this site: [Name That Color](http://chir.ag/projects/name-that-color/). It automatically generates a name for the given color 🧙‍


## #26 - Structure classes using `// MARK: -`
🔖 Using `// MARK:` we can add some additional information that is shown in the quick jump bar. Adding a dash the end (`// MARK: -`) causes a separation line to show up. Using this technique we can structure classes and make them easier to read.

```swift
class StructuredViewController: UIViewController {

    // MARK: - Types

    typealias CompletionHandler = (Bool) -> Void

    // MARK: - Outlets

    @IBOutlet private var submitButton: UIButton!

    // MARK: - Public properties

    var completionHandler: CompletionHandler?

    // MARK: - Private properties

    private let viewModel: StructuredViewModel

    // MARK: - Initializer

    override init(nibName nibNameOrNil: String?, bundle nibBundleOrNil: Bundle?) {
        viewModel = StructuredViewModel()

        // ...

        super.init(nibName: nibNameOrNil, bundle: nibBundleOrNil)
    }

    deinit {
        // ...
    }

    // MARK: - Public methods

    override func viewDidLoad() {
        // ...
    }

    // MARK: - Private methods

    private func setupSubmitButton() {
        // ...
    }
}
```

## #25 - Structure test cases
⚠️ Splitting test cases into `Given`, `When`, `Then` increases the readability and helps understanding complex tests.

 - In the `Given` phase we setup all preconditions for the test, e.g. configuring mock objects.
 - In the `When` phase we call the function we want to test.
 - In the `Then` phase we verify the actual results against our expected results using `XCTAssert` methods.

 #### Example:
```swift
class MapViewModelTestCase: XCTestCase {
    var locationServiceMock: LocationServiceMock!

    var viewModel: MapViewModel!
    var delegateMock: MapViewModelDelegateMock!

    override func setUp() {
        super.setUp()

        // ...
    }

    override func tearDown() {
        // ...

        super.tearDown()
    }

    func testLocateUser() {
        // Given
        let userLocation = CLLocationCoordinate2D(latitude: 12.34,
                                                  longitude: 56.78)

        locationServiceMock.userLocation = userLocation

        // When
        viewModel.locateUser()

        // Then
        XCTAssertEqual(delegateMock.focusedUserLocation.latitude, userLocation.latitude)
        XCTAssertEqual(delegateMock.focusedUserLocation.longitude, userLocation.longitude)
    }
}
```

## #24 - Avoid forced unwrapping
> The only time you should be using implicitly unwrapped optionals is with @IBOutlets.
> In every other case, it is better to use a non-optional or regular optional property.
> Yes, there are cases in which you can probably "guarantee" that the property will never be nil when used,
> but it is better to be safe and consistent. Similarly, don't use force unwraps.

Source: https://github.com/linkedin/swift-style-guide

Using the patterns shown underneath, we can easily unwrap optionals or use early return to stop further code executing, if an optional is `nil`.

```swift
if let value = value {
    // Do stuff with value here..
}
```

```swift
guard let value = value else {
    // Write a comment, why to exit here.
    return
}

// Do stuff with value here..
```


## #23 - Always check for possible dividing through zero
💥 Always make sure that a certain value is NOT zero before dividing through it.

```swift
class ImageViewController: UIViewController {

    // MARK: - Outlets

    @IBOutlet private var imageView: UIImageView!

    // MARK: - Private methods

    func someMethod() {
        let bounds = imageView.bounds
        guard bounds.height > 0 else {
            // Avoid diving through zero for calculating aspect ratio below.
            return
        }

        let aspectRatio = bounds.width / bounds.height
    }
}
```


## #22 - Animate `alpha` and update `isHidden` accordingly
🦋 Using the following Gist we can animate `alpha` and update the `isHidden` flag accordingly: [fxm90/UIView+AnimateAlpha.swift](https://gist.github.com/fxm90/723b5def31b46035cd92a641e3b184f6)


## #21 - Create custom notification
📚 For creating custom notifications we first should have a look on how to name them properly:

> [Name of associated class] + [Did | Will] + [UniquePartOfName] + Notification

Source: [Coding Guidelines for Cocoa](https://apple.co/2PPywfa)

Now we can create the new notification. We do this by extending the corresponding class:

```swift
extension Notification.Name {
    static let AccountServiceDidLoginUser = Notification.Name("AccountServiceDidLoginUserNotification")
}
```

And finally post it:

```swift
class AccountService {
    func login() {
        NotificationCenter.default.post(name: .AccountServiceDidLoginUser,
                                        object: self)
    }
}
```

For Objective-C support we further need to extend `NSNotification`:

```swift
@objc extension NSNotification {
    static let AccountServiceDidLoginUser = Notification.Name.AccountServiceDidLoginUser
}
```

Then, we can post it like this:

```
[NSNotificationCenter.defaultCenter post:NSNotification.AccountServiceDidLoginUser
                                  object:self];
```

By extending `Notification.Name` we make sure our notification names are unique.

**Notice:** The object parameter should always contain the object, that is triggering the notification. If you need to pass custom data, use the `userInfo` parameter.


## #20 - Override `UIStatusBarStyle` the elegant way
✌️ Using `didSet` we can easily call `setNeedsStatusBarAppearanceUpdate()` to apply a new status-bar style:

```swift
class SomeViewController: UIViewController {

    // MARK: - Public properties

    override var preferredStatusBarStyle: UIStatusBarStyle {
        return customBarStyle
    }

    // MARK: - Private properties

    private var customBarStyle: UIStatusBarStyle = .default {
        didSet {
            setNeedsStatusBarAppearanceUpdate()
        }
    }
}
```

## 19 - Log extension on `String` using swift literal expressions
👌 Swift contains some special literals:

| Literal   | Type   | Value                                           |
| :---------|:-------| :-----------------------------------------------|
| #file     | String | The name of the file in which it appears.       |
| #line     | Int    | The line number on which it appears.            |
| #column   | Int    | The column number in which it begins.           |
| #function | String | The name of the declaration in which it appears.|
Source: [Swift.org - Expressions](https://docs.swift.org/swift-book/ReferenceManual/Expressions.html)

Especially with default parameters those expressions are really useful, as in that case the expression is evaluated at the call site.
We could use a [simple extension on String](https://gist.github.com/fxm90/08a187c5d6b365ce2305c194905e61c2) to create a basic logger:

```swift
"Lorem Ipsum Dolor Sit Amet 👋".log(level: .release)
```

That would create the following output:
> 2018/09/16 19:46:45.189 - ViewController.swift - viewDidLoad():15 - Lorem Ipsum Dolor Sit Amet 👋


## 18 - Use gitmoji
😃 Not an iOS specific topic, but I'd like to use [gitmoji](https://gitmoji.carloscuesta.me/) for my commit messages, e.g. `TICKET-NUMBER - ♻️ :: Description` (Credits go to [Martin Knabbe](https://twitter.com/martin_knabbe) for that pattern). To easily create the corresponding emojis for the type of commit, you can use this [alfred workflow](https://github.com/ai0/alfred-gitmoji-workflow).


## #17 - Initialize a constant based on a condition
👏 A very readable way of initializing a constant after the declaration.

```swift
let startCoordinate: CLLocationCoordinate2D
if let userCoordinate = userLocationService.userCoordinate, CLLocationCoordinate2DIsValid(userCoordinate) {
    startCoordinate = userCoordinate
} else {
    // We don't have a valid user location, so we fallback to Hamburg.
    startCoordinate = CLLocationCoordinate2D(latitude: 53.5582447,
                                             longitude: 9.647645)
}
```

This way we can avoid using a variable and therefore prevent any mutation of `startCoordinate` in further code.


## #16 - Why `viewDidLoad` might be called before `init` has finished
⚡️ Be aware that the method `viewDidLoad` is being called immediately on accessing `self.view` in the initializer. This happens because that the view is not loaded yet, but the property `self.view` shouldn't return `nil`. Therefore the view controller will load the view directly and call the corresponding method `viewDidLoad` afterwards.

#### Example:
```swift
class ViewDidLoadBeforeInitViewController: UIViewController {
    // MARK: - Initializer

    override init(nibName nibNameOrNil: String?, bundle nibBundleOrNil: Bundle?) {
        super.init(nibName: nibNameOrNil, bundle: nibBundleOrNil)

        view.isHidden = true

        print("📝 :: `\(#function)` did finish!")
    }

    required init?(coder aDecoder: NSCoder) {
        super.init(coder: aDecoder)

        view.isHidden = true

        print("📝 :: `\(#function)` did finish!")
    }

    // MARK: - Public methods

    override func viewDidLoad() {
        super.viewDidLoad()

        print("📝 :: `\(#function)` did finish!")
    }
}
```

The code will output log statements in the following order:

```
📝 :: `viewDidLoad()` did finish.
📝 :: `init(nibName:bundle:)` did finish.
```

Source: https://stackoverflow.com/a/5808477

More on view life cycle: [Work with View Controllers](https://apple.co/2q8Jf9y)


## #15 - Capture iOS Simulator video
📹 A small tutorial on how create a video of what's happening in the simulator.

1. Run your App in the simulator
2. Open terminal
3. Run one of the following commands:
  *  To take a screenshot: `xcrun simctl io booted screenshot`
  *  To take a video: `xcrun simctl io booted recordVideo <filename>.<file extension>`
4. Press ctrl + c to stop recording the video.

For example:
```
xcrun simctl io booted recordVideo ~/appVideo.mp4
```

Source: https://stackoverflow.com/a/41141801


## #14 - Xcode open file in focused editor
🏃‍♂️ Shortcuts are a great way to increase productivity. I often use `CMD[⌘] + Shift[⇧] + O` to quickly open a file or `CMD[⌘]  + Shift[⇧] +  J` to focus the current file in the project navigator etc.

> By default, when you ‘Quick Open’ a file via cmd-shift-O, it opens in the ‘Primary Editor’ on the left — even if the right editor pane is currently focused.
> Annoying.
> All I want to do is open two files side-by-side, switch between them easily, and have ‘Quick Open’ target whichever side is currently focused.

[Jesse Squires - Improving the assistant editor](https://www.jessesquires.com/blog/xcode-tip-improving-assistant-editor/)

Jesse Squires provides a solution for that problem: By going to `Settings » Navigation » Navigation` and there checking `Uses Focused Editor`, we can tell Xcode to always open files in the currently focused pane.


## #13 - Handle optionals in test cases
✅ Using `XCTUnwrap` we can safely unwrap optionals in test-cases. If the optional is nil, only the current test-case will fail, but the app won't crash and all other test-cases will continue to be executed.

In the example below, we initialize a view model with a list of bookings. Using the method `findBooking(byIdentifier:)` we search for a given booking. But as we might pass an invalid identifier, the response of the method is an optional booking object. Using `XCTUnwrap` we can easily unwrap the response.
```swift
class BookingViewModelTestCase: XCTestCase {
    func testFindBookingByIdentifierShouldReturnMockedBooking() throws {
        // Given
        let mockedBooking = Booking(identifier: 1)
        let viewModel = BookingViewModel(bookings: [mockedBooking])

        // When
        let fetchedBooking = try XCTUnwrap(
            viewModel.findBooking(byIdentifier: 1)
        )

        // Then
        XCTAssertEqual(fetchedBooking, mockedBooking)
    }
}
```

#### Prior to Xcode 11
[Require](https://github.com/JohnSundell/Require) is a simple, yet really useful framework for handling optionals in test cases (by John Sundell again 😃). He also wrote a great blog post explaining the use-case for this framework: [Avoiding force unwrapping in Swift unit tests](https://www.swiftbysundell.com/posts/avoiding-force-unwrapping-in-swift-unit-tests)


## #12 - Safe access to an element at index
⛑ Using the underneath shown range operator, we can easily create an extension to safely return an array element at the specified index, or `nil` if the index is outside the bounds.

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

let banana = fruits[safe: 2]
let pineapple = fruits[safe: 6]

// Does not crash, but contains nil
let invalid = fruits[safe: 7]
```


## #11 - Check whether a value is part of a given range
💡 Instead of writing `x >= 10 && x <= 100`, we can write `10 ... 100  ~=  x`.
#### Example:
```swift
let statusCode = 200

let isSuccessStatusCode = 200 ... 299 ~= statusCode
let isRedirectStatusCode = 300 ... 399 ~= statusCode
let isClientErrorStatusCode = 400 ... 499 ~= statusCode
let isServerErrorStatusCode = 500 ... 599 ~= statusCode
```

Another (more readable way) for checking whether a value is part of a given range can be achieved using the `contains` method:

```swift
let statusCode = 200

let isSuccessStatusCode = (200 ... 299).contains(statusCode)
let isRedirectStatusCode = (300 ... 399).contains(statusCode)
let isClientErrorStatusCode = (400 ... 499).contains(statusCode)
let isServerErrorStatusCode = (500 ... 599).contains(statusCode)
```

## #10 - Use `compactMap` to filter `nil` values
🎛 By using `compactMap` we can filter out `nil` values of a list. This can be useful, e.g. while parsing a server response:

```swift
struct ItemDataModel {
    let title: String?
}

struct ItemViewModel {
    let title: String
}

extension ItemViewModel {
    /// Convenience initializer, that maps the data-model from the server to our view-model
    /// if all required properties are available.
    init?(dataModel: ItemDataModel) {
        guard let title = dataModel.title else {
            return nil
        }

        self.init(title: title)
    }
}

class ListViewModel {
    /// ...

    func mapToItemViewModel(response: [ItemDataModel]) -> ([ItemViewModel]) {
        // Using `compactMap` we filter out invalid data-models automatically.
        return response.compactMap { ItemViewModel(dataModel: $0) }
    }
}
```


## #09 - Prefer `Set` instead of array for unordered lists without duplicates
👫 **Advantage over `Array`:**

 - Constant Lookup time O(1), as a `Set` stores its members based on hash value.

**Disadvantage compared to `Array`:**

 - No guaranteed order.
 - Can't contain duplicate values.
 - All items we want to store must conform to `Hashable` protocol.

Please have a look at ["The power of sets in Swift" (by John Sundell)](https://medium.com/@johnsundell/the-power-of-sets-in-swift-57be8b223da0) for further examples and use-cases.


## #08 - Remove all sub-views from `UIView`
📭 - A small extension to remove all sub-views.

```swift
extension UIView {
    func removeAllSubviews() {
        subviews.forEach { $0.removeFromSuperview() }
    }
}
```


## #07 - Animate image change on `UIImageView`
✍️ Easily (ex)change an image with using a transition (note that the `.transitionCrossDissolve` is the key to this working).

```swift
extension UIImageView {
    func updateImageWithTransition(_ image: UIImage?, duration: TimeInterval) {
        UIView.transition(with: self, duration: duration, options: .transitionCrossDissolve, animations: { () -> Void in
            self.image = image
        })
    }
}
```


## #06 - Change `CALayer` without animation
👨‍🎨 CALayer has a default implicit animation duration of [0.25 seconds](https://apple.co/2PVTCsB). Using the following extension we can do changes without an animation:

```swift
extension CALayer {
    class func performWithoutAnimation(_ actionsWithoutAnimation: () -> Void) {
        CATransaction.begin()
        CATransaction.setAnimationDuration(0.0)

        actionsWithoutAnimation()

        CATransaction.commit()
    }
}
```


## #05 - Override `layerClass` to reduce the total amount of layers
> By overriding 'layerClass' you can tell UIKit what CALayer class to use for a UIView's backing layer.
> That way you can reduce the amount of layers, and don't have to do any manual layout.
[John Sundell](https://twitter.com/johnsundell/status/1000099872580816897)

This can be archived with the following code:

```swift
override class var layerClass: AnyClass {
    return CAGradientLayer.self
}
```

This is e.g. useful to add a linear gradient behind an image. Furthermore we could change the gradient-color based on the time of the day, without having to add multiple images to our app.
![Example][overwrite-layer-class]

You can see the full code for the example in my gist for the [Vertical Gradient Image View](https://gist.github.com/fxm90/9604b0a067af46f68b80c6968736558d).


## #04 - Handle notifications in test cases
📬 Examples on how to test notifications in test cases:

 - [XCTest - Assert notification (not) triggered](https://gist.github.com/fxm90/23dc7debc5ee8245237c08e5af8679bc)
 - [XCTest - Use custom notification center in test case and assert notification (not) triggered](https://gist.github.com/fxm90/3c6f146ed977100d21f0a1f3e7bb37a2)


## #03 - Use `didSet` on outlets to setup components
👏 By using `didSet` on outlets, we can setup our view components (declared in a storyboard or xib) in a very readable way:

```swift
class FooBarViewController: UIViewController {

    // MARK: - Outlets

    @IBOutlet private var button: UIButton! {
        didSet {
            button.setTitle(viewModel.normalTitle, for: .normal)
            button.setTitle(viewModel.disabledTitle, for: .disabled)
        }
    }

    // MARK: - Private properties

    private var viewModel = FooBarViewModel()
}
```


## #02 - Most readable way to check whether an array contains a value (`isAny(of:)`)
✨ A small extension to check whether a value is part of e.g. an array, in a very readable way (by [John Sundell](https://twitter.com/johnsundell/status/943510426586959873))

```swift
extension Equatable {
    func isAny(of candidates: Self...) -> Bool {
        return candidates.contains(self)
    }
}
```

#### Example:
```swift
enum Product {
    case macBook
    case iPad
    case iPhone
    case watch
}

let device: Product = .iPhone

// Before
let isIOSDevice = [.iPad, .iPhone].contains(device)

// After
let isIOSDevice = device.isAny(of: .iPad, .iPhone)
```


## #01 - Override `self` in escaping closure, to get a strong reference to `self`
🚸 To avoid retain cycles we often have to pass a `weak` reference to `self` into closures. By using the following pattern, we can get a strong reference to `self` for the lifetime of the closure.

```swift
someService.request() { [weak self] response in
    guard let self = self else { return }

    self.doSomething(with: response)
}
```

**Notice:** The above works as of Swift 4.2. Before you have to use:

```
guard let `self` = self else { return }
```

[overwrite-layer-class]: https://felix.hamburg/files/github/dev-notes/overwrite-layer-class.jpg

[latitude]: https://felix.hamburg/files/github/dev-notes/latitude.jpg
[latitude--thumbnail]: https://felix.hamburg/files/github/dev-notes/latitude--thumbnail.jpg

[longitude]: https://felix.hamburg/files/github/dev-notes/longitude.jpg
[longitude--thumbnail]: https://felix.hamburg/files/github/dev-notes/longitude--thumbnail.jpg
