# BL202-Prototype
Banff is a chat engine framework which will be used in future projects that require chat capabilities. It utilizes the MessageKit framework for managment of messaging. This project is built and used with CocoaPods. 

The example iOS App demonstrates how to use this framework with Firebase Cloud Firestore. To run the iOS app, simply open the 'Banff.xcworkspace' project file and specify the 'BanffFirebaseExample-iOS' target, as well as your desired device. Hit the run button to build and run the app!

![alt tag](https://raw.github.com/maximbilan/SwiftHUEColorPicker/master/img/img4.png) 

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
Banff framework includes support for six different types of chat screens. These screens are templates that are comprimised mainly of chat features and functions, and are fully customizable user interface-wise. While Swift does not natively support "Abstract" classes, these classes have been designed to be implemented in just this way; to be subclassed and by requirement, implement certain functions (with runtime fatal errors occurring otherwise). Aditionally, there are various extensions that provide convenience functions that are used within the framework classes, as well as a User settings singleton which stores the user's data and is accesible throught the framework and the app using it.

## Using
As mentioned above, there are certain functions that must be implemented when subclassing a chat screen, which would otherwise present a fatal error during runtime. Additionally, you will have to add your own convenience functions that relate to any network calls for data submission/retrieval. Subclass the classes below and implement the abstract functions specified:

<b>SignInViewController</b>:
Provides an entry screen to the chat app intended to authorize and sign a user in.
![alt tag](https://raw.github.com/maximbilan/SwiftHUEColorPicker/master/img/img4.png)

Implement the <i>uploadImage</i> function with the necessary networking logic to upload to your database:
<pre>
func uploadImage(image: UIImage, data: Data){   }
</pre>

<b>RoomsTableViewController.swift</b>: 
This screen is meant to provide list of channels and direct message conversations that the user can navigate to by tapping.
![alt tag](https://raw.github.com/maximbilan/SwiftHUEColorPicker/master/img/img4.png)

Implement the <i>uploadImage</i> function with the necessary networking logic to upload to your database:
<pre>
func uploadImage(image: UIImage, data: Data){   }
</pre>

<b>ChatViewController.swift</b>:
A class that consists of chat conversation functions. The two classes below subclass this class, each functioning as its own type of chat conversation screen.
1) <b>ChannelViewController.swift</b>, which is meant to handle group conversations. 
![alt tag](https://raw.github.com/maximbilan/SwiftHUEColorPicker/master/img/img4.png) 

Implement the <i>uploadImage</i> function with the necessary networking logic to upload to your database:
<pre>
func uploadImage(image: UIImage, data: Data){   }
</pre>

2) <b>DirectMessageViewController.swift</b>, which handles one to one chat conversations.
![alt tag](https://raw.github.com/maximbilan/SwiftHUEColorPicker/master/img/img4.png)

Implement the <i>uploadImage</i> function with the necessary networking logic to upload to your database:
<pre>
func uploadImage(image: UIImage, data: Data){   }
</pre>

<b>ProfileViewController</b>:
Contains the necessary functions of a profile page, which allows users to change their profile picture in a profile setting, while in channel info setting, allow a user to change the image of a channel.
![alt tag](https://raw.github.com/maximbilan/SwiftHUEColorPicker/master/img/img4.png)

Implement the <i>uploadImage</i> function with the necessary networking logic to upload to your database:
<pre>
func uploadImage(image: UIImage, data: Data){   }
</pre>

Implement the <i>uploadImage</i> function with the necessary networking logic to upload to your database:
<pre>
func uploadImage(image: UIImage, data: Data){   }
</pre>

## Firebase Firestore Example

Please see the Firebase implementation example of <i>Banff Framework</i> in the base folder of this repository; BanffFirebaseExample-iOS.

## License

Banff Framework is available under the MIT license. See the LICENSE file for more info.
