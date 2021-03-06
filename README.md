Cell+Rx
===========

![Swift 4](https://img.shields.io/badge/Swift-4.0.x-orange.svg)
![RxSwift 4](https://img.shields.io/badge/RxSwift-4.0.x-red.svg)

**Cell+Rx** provides a similar API to [NSObject+Rx](https://github.com/RxSwiftCommunity/NSObject-Rx) but for cells who are reused along the way.

I found myself creating `DisposeBag`s that were reset on the `prepareForReuse()` function which was pretty repetitive.

Instead of adding a new property to every cell, use this library to add it for you, to any subclass of `UITableViewCell` or `UICollectionViewCell`.

```swift
thing
  .bindTo(otherThing)
  .disposed(by: rx_reusableDisposeBag)
```

It'll work just like a property: when the instance is deinit'd, the `DisposeBag` gets disposed. It will also reset whenever the cell is reused by detecting `prepareForReuse()` calls. It's also a read/write property, so you can use your own, too.

Installing
----------

####CocoaPods

This works with RxSwift version 4 and Swift 4.0

```ruby
pod 'Cell+Rx'
```

And that'll be 👌

License
-------

MIT License.
