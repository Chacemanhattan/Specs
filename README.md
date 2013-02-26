# CocoaPods – an Objective-C library manager

| CocoaPods | Xcodeproj | Specs | Dependencies |
| :---: | :---: | :---: | :---: |
[![Build Status](https://travis-ci.org/CocoaPods/CocoaPods.png)](https://travis-ci.org/CocoaPods/CocoaPods)|[![Build Status](https://secure.travis-ci.org/CocoaPods/Xcodeproj.png?branch=master)](http://travis-ci.org/CocoaPods/Xcodeproj)|[![Build Status](https://secure.travis-ci.org/CocoaPods/Specs.png?branch=master)](http://travis-ci.org/CocoaPods/Specs)|[![Dependency Status](https://gemnasium.com/CocoaPods/CocoaPods.png)](https://gemnasium.com/CocoaPods/CocoaPods)


CocoaPods manages library dependencies for your Xcode project.

Homepage: [http://cocoapods.org/](http://cocoapods.org/)
Twitter: [@CocoaPods](http://twitter.com/CocoaPods)
Mailing List: [http://groups.google.com/group/cocoapods](http://groups.google.com/group/cocoapods)

You specify the dependencies for your project in one easy text file. CocoaPods resolves dependencies between libraries, fetches source code for the dependencies, and creates and maintains an Xcode workspace to build your project.

Ultimately, the goal is to improve discoverability of, and engagement in, third party open-source libraries, by creating a more centralized ecosystem.

See the [NSScreencast](https://twitter.com/NSScreencast) episode about [using CocoaPods](http://nsscreencast.com/episodes/5-cocoapods) for a quick overview on how to get started or [create a Pod specification](http://nsscreencast.com/episodes/28-creating-a-cocoapod), or [the wiki](https://github.com/CocoaPods/CocoaPods/wiki) for more in depth information on several topics.

Or, if you’re already using CocoaPods, you can find the changelog [here](https://github.com/CocoaPods/CocoaPods/blob/master/CHANGELOG.md), which contains an overview of the changes in recent versions.


## Installation

Downloading and installing CocoaPods only takes a few minutes.

CocoaPods runs on [Ruby](http://www.ruby-lang.org/en/). To install it run the following commands:

```
$ [sudo] gem install cocoapods
```

If you want to have CocoaPods generate documentation for each library, then install the [appledoc](http://gentlebytes.com/appledoc/) tool:

```
$ brew install appledoc
```

Now that you've got CocoaPods installed you can easily add it to your project.

**NOTES**

1. If you're using a fresh out of the box Mac with Lion using Xcode from the Mac App Store, you will need to install the Command Line Tools for Xcode first: [here](https://developer.apple.com/downloads/index.action)  
Or from `Xcode > Settings > Downloads > Components > Command Line Tools`

2. CocoaPods re-uses some of the RubyGems classes. If you have a version older than 1.4.0, you will have to update RubyGems: `$ gem update --system`.

3. If you use [RVM](https://rvm.io), you might need to create a symbolic link to the LLVM GCC compiler: `$ [sudo] ln -s /usr/bin/llvm-gcc-4.2 /usr/bin/gcc-4.2`


## Adding it to your project

Search for Pods by name or description.

```
$ pod search json

--> JSONKit (1.4, 1.5pre)
    A Very High Performance Objective-C JSON Library.
    - Homepage: https://github.com/johnezang/JSONKit
    - Source:   https://github.com/johnezang/JSONKit.git

--> SBJson (2.2.3, 3.0.4, 3.1)
    This library implements strict JSON parsing and generation in Objective-C.
    - Homepage: http://stig.github.com/json-framework/
    - Source:   https://github.com/stig/json-framework.git
```

After you've found your favorite dependencies you add them to your [Podfile](https://github.com/CocoaPods/CocoaPods/wiki/A-Podfile).

```
$ edit Podfile
```

```ruby
platform :ios
pod 'JSONKit',           '~> 1.4'
pod 'Reachability',      '~> 2.0.4'
```

And then you [install the dependencies](https://github.com/CocoaPods/CocoaPods/wiki/Creating-a-project-that-uses-CocoaPods) in your project.

```
$ pod install
```

Remember to always open the Xcode workspace instead of the project file when you're building.

```
$ open App.xcworkspace
```

Sometimes CocoaPods doesn't have a Pod for one of your dependencies yet. Fortunately [creating a Pod](https://github.com/CocoaPods/CocoaPods/wiki/A-pod-specification) is really easy.

```
$ pod spec create Peanuts
$ edit Peanuts.podspec
$ pod spec lint Peanuts.podspec
```

Once you've got it running [create a ticket](https://github.com/CocoaPods/CocoaPods/issues) and upload the Pod. If you're familiar with Git you can also fork the [CocoaPods specs](https://github.com/CocoaPods/Specs) repository and send a pull request. We really love contributions!

There are several other ways to start using **any** library without a Pod specification, which can be seen in the [SSCatalog example](https://github.com/CocoaPods/CocoaPods/blob/master/examples/SSCatalog/Podfile).


## Collaborate

All CocoaPods development happens on GitHub, there is a repository for [CocoaPods](https://github.com/CocoaPods/CocoaPods) and one for the [CocoaPods specs](https://github.com/CocoaPods/Specs). Contributing patches or Pods is really easy and gratifying. You even get push access when one of your specs or patches is accepted.

Follow [@CocoaPods](http://twitter.com/CocoaPods) to get up to date information about what's going on in the CocoaPods world.


# Donations

* [@fngtps](http://twitter.com/fngtps) is donating time to work on the design of the forthcoming cocoapods.org website and donated the money to hire [Max Steenbergen](http://twitter.com/maxsteenbergen) to design [an icon](http://drbl.in/cpmL) for it.
* [@sauspiel](http://twitter.com/Sauspiel) uses CocoaPods for their games and have hired me to add features and specs they needed. These are Nimbus, QuincyKit, and HockeyKit. For the [Nimbus spec](https://github.com/CocoaPods/Specs/blob/master/Nimbus/0.9.0/Nimbus.podspec), the ‘subspecs’ feature was added.

# Endorsements

* “I am crazy excited about this. With the growing number of Objective-C libraries, this will make things so much better.” –– [Sam Soffes](http://news.ycombinator.com/item?id=3009154)
* “Are you doing open source iOS components? You really should support @CocoaPodsOrg!” –– [Matthias Tretter](http://twitter.com/#!/myell0w/status/134955697740840961)
* “So glad someone has finally done this...” –– [Tom Wilson](http://news.ycombinator.com/item?id=3009349)
* “Anybody who has tasted the coolness of RubyGems (and @gembundler) understands how cool CocoaPods might be.” –– [StuFF mc](http://twitter.com/#!/stuffmc/status/115374231591731200)
* “I will be working on getting several of my Objective-C libraries ready for CocoaPods this week!” –– [Luke Redpath](http://twitter.com/#!/lukeredpath/status/115510581921988608)
* “Really digg how @alloy is building a potential game changer” –– [Klaas Speller](https://twitter.com/#!/spllr/status/115914209438601216)
* “@alloy's making an Objective-C package manager. This is fantastic news kids!” –– [Josh Abernathy](http://twitter.com/#!/joshaber/status/115273577703555073)
* “A package manager for Cocoa/Objective-C, built with @MacRuby. Awesomeness!” –– [Johannes Fahrenkrug](http://twitter.com/#!/jfahrenkrug/status/115303240286998528)
* “This is awesome, I love endorsements!” –– [Appie Durán](http://twitter.com/#!/AppieDuran)
