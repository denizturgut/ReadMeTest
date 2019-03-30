# BL202-Prototype
Banff is a chat engine framework which will be used in future projects that require chat capabilities. It utilizes the MessageKit framework for managment of messaging. This project is built and used with CocoaPods. 

The example iOS App demonstrates hwo to use this framework with Firebase Cloud Firestore. To run the iOS app, simply open the 'Banff.xcworkspace' project file and specify the 'BanffFirebaseExample-iOS' target, as well as your desired device. Hit the run button to build and run the app!

## Installation

### CocoaPods

[CocoaPods](https://cocoapods.org) is a dependency manager for Cocoa projects. For usage and installation instructions, visit their website. To integrate Alamofire into your Xcode project using CocoaPods, specify it in your `Podfile`:

```ruby
pod 'Banff', :git => 'https://github.com/iggytheiguana/BL202-Prototype', :tag => '0.1.0'
```
### Manual
Add <i>/Banff.framework</i> to the 'Embedded Binaries' section of your project settings.

## Using

ChatlViewController.swift is comprimised of most various chat features and functions, most which can be overriden in its counterpart classes.
Two classes subclass ChatlViewController.swift. The first is ChannelViewController, which is meant to handle group conversations. The other class is DirectMessageViewController.swift, which handles one to one chat conversations.

Profile Screen:
For handling of profile image uploads, subclass ProfileViewController.swift and implement protocol <i>ProfileVCDelegate</i> with the necessary networking functions:

```func uploadImage(image: UIImage, data: Data)
```

Please see the Firebase implementation example for using <i>Banff Framework</i> in this repository; BanffFirebaseExample-iOS

## License

Banff Framework is available under the MIT license. See the LICENSE file for more info.
