# TableFlip

### (╯°□°）╯︵ ┻━┻
---
### ┬──┬ ノ( ゜-゜ノ)
---

### Animations are cool. UITableView isn't. So why not make animating UITableView cool?

---

##### The entire API for TableFlip consists of an animation, and a call to animate. It's as simple as that.

##### TableFlip takes the annoying nature of reloading UITableViews, maintaining state, and anminating, and minimizes it to two lines of code.

##### If you want to animate every cell consecutively, the code will look like this.

```swift
self.tableView.reloadData()
self.tableView.animateCells(animation: myCoolCellAnimation)
```

##### And if you want to animate the entire table view at once, the code will look like this: 

```swift
self.tableView.reloadData()
self.tableView.animateTableView(animation: myCoolTableAnimation)
```

Animations are completely customizable and configurable. TableFlip provides a few built-in defaults that work nicely out the box, if you don't want to make your own.

## Let's look at some examples


### Animating from the left with a nice staggered effect:

```swift
TableViewAnimation.Cell.left(duration: 0.5)
```

![](gifs/left.gif)


### Pushing from the top can make a nice initial loading effect:

```swift
TableViewAnimation.Table.top(duration: 0.8)
```

![](gifs/top.gif)

### A simple fade is always elegant:

```swift
TableViewAnimation.Cell.fade(duration: 1.0)
```

![](gifs/fade.gif)


### And you can make your own transform, as fun or weird as you want by using CGAffineTransform:

```swift
let degrees = CGFloat(sin(90.0 * M_PI/180.0))
let rotationTransform = CGAffineTransform(rotationAngle: degrees)
let flipTransform = CGAffineTransform(scaleX: -1, y: -1)
let customTransform = rotationTransform.concatenating(flipTransform)

self.loadImages(withAnimation: TableViewAnimation.Cell.custom(duration: 0.6, transform: customTransform, options: .curveEaseInOut))
```

![](gifs/custom.gif)


## Installation
You can use [CocoaPods](http://cocoapods.org/) to install `TableFlip` by adding it to your `Podfile`:

```swift
platform :ios, '8.0'
use_frameworks!

pod 'TableFlip'
```

Or install it manually by downloading `UITableView+Animations.swift` and dropping it in your project.

## About me

Hi, I'm [Joe](http://fabisevi.ch) everywhere on the web, but especially on [Twitter](https://twitter.com/mergesort).

## License

See the [license](LICENSE) for more information about how you can use TableFlip.

## P.S.

If all you liked was the kitty, that's my baby Gif. Feel free to follow her on the [Instagram](https://www.instagram.com/gifthecat).