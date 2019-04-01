# BL202-Prototype
Banff is a chat engine framework which will be used in future projects that require chat capabilities. It utilizes the MessageKit framework for managment of messaging. This project is built and used with CocoaPods. 

The example iOS App demonstrates how to use this framework with Firebase Cloud Firestore. To run the iOS app, simply open the 'Banff.xcworkspace' project file and specify the 'BanffFirebaseExample-iOS' target, as well as your desired device. Hit the run button to build and run the app!

## Installation

### CocoaPods
[CocoaPods](https://cocoapods.org) is a dependency manager for Cocoa projects. For usage and installation instructions, visit their website. To integrate Banff into your Xcode project using CocoaPods, specify it in your `Podfile`:

<pre>
pod 'Banff', :git => 'https://github.com/iggytheiguana/BL202-Prototype', :tag => '0.1.0'
</pre>

### Manual
Add <i>Banff.framework</i> to the 'Embedded Binaries' section of your project settings.

### Swift Package Manager (SPM)
Coming soon!

## Description
Banff framework includes support for six different types of chat screens. These screens are comprimised mainly of chat features and functions. While Swift does not natively support "Abstract" classes, these classes have been designed to be implemented in just this way; to be subclassed and by requirement, implement certain functions (with runtime fatal errors occurring otherwise). 

## Using
As mentioned above, there are certain functions that must be implemented when subclassing a chat screen, which would otherwise present a fatal error during runtime.

<b>SignInViewController</b>:
Provides an entry screen to the chat app intended to authorize and sign a user in.

<b>RoomsTableViewController.swift</b>: 
This screen is meant to list channels and direct message conversations that the user can partake in:

<b>ChatViewController.swift</b>:
A class that consists of chat conversation functions. The two classes below subclass this class, each functioning as its own type of chat conversation screen.
1) <b>ChannelViewController.swift</b>, which is meant to handle group conversations. 
2) <b>DirectMessageViewController.swift</b>, which handles one to one chat conversations.

<b>ProfileViewController</b>:
Contains the necessary functions of a profile page, which allows users to change their profile picture in a profile setting, while in channel info setting, allow a user to change the image of a channel.

For handling of profile image uploads, subclass ProfileViewController.swift and implement protocol <i>ProfileVCDelegate</i> with the necessary networking functions:

<pre>
func uploadImage(image: UIImage, data: Data)
</pre>

![alt tag](https://raw.github.com/maximbilan/SwiftHUEColorPicker/master/img/img2.png)
</br>Also, you can change a <i>saturation</i>, a <i>brightness</i> and <i>alpha</i> values.
</br>And control has customization. You can customize the label:</br>
![alt tag](https://raw.github.com/maximbilan/SwiftHUEColorPicker/master/img/img3.png)
</br>Or appearance:</br>
</br>
![alt tag](https://raw.github.com/maximbilan/SwiftHUEColorPicker/master/img/img4.png)

## Firebase Firestore Example

Please see the Firebase implementation example of <i>Banff Framework</i> in the base folder of this repository; BanffFirebaseExample-iOS

## License

Banff Framework is available under the MIT license. See the LICENSE file for more info.
