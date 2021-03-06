# BL202-Prototype
Banff is a chat engine framework which will be used in future projects that require chat capabilities. It utilizes the MessageKit framework for managment of messaging. This project is built and used with CocoaPods. Banff supports Swift 4.2

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
Banff framework includes support for six different types of chat screens. These screens are templates that are comprimised mainly of chat features and functions, and are fully customizable user interface-wise. While Swift does not natively support "Abstract" classes, these classes have been designed to be implemented in just this way; to be subclassed and by requirement, implement certain functions (with runtime fatal errors occurring otherwise). Aditionally, there are various extensions that provide convenience functions that are used within the framework classes, as well as a User settings singleton which stores the user's data and is accesible throught the framework and the app using it, which are also customizable through extension.

## Firebase Firestore Example

Please see the example app utlizing <i>Banff Framework</i> in the base folder of this repository; BanffFirebaseExample-iOS. It leverages Google's Firebase Firestore for data persistence.

## Using Banff

As mentioned above, there are certain functions that must be implemented when subclassing a chat screen, which would otherwise present a fatal error during runtime. Additionally, you will have to add your own convenience functions that relate to any network calls for data submission/retrieval. Subclass/extend the classes below and implement the abstract functions specified:

<b>Chat</b>:
While most of this model has already been setup, some databases may require chat data to be sent up in a certain type of document or json format. Extend this class to declare an additional <i>init</i> to parse the data in to a desired format.

<b>Message</b>:
Just like the Chat model, this model has also been mostly setup, and some databases may require Message data to be sent up in a certain format. Extend this class to declare an additional <i>init</i> to do this.

<b>SignInViewController</b>:
Provides an entry screen to the chat app intended to authorize and sign a user in.

![alt tag](https://raw.github.com/maximbilan/SwiftHUEColorPicker/master/img/img4.png)

Implement the <i>authorizeUser</i> function with the database authorization logic to sign the user in. The name passed to the function will be stored in your database and become associated with a user id, and will be added to App Settings store to be used within the app:
<pre>
func authorizeUser(name: String) {   

}
</pre>

<b>RoomsTableViewController.swift</b>: 
This screen is meant to provide list of channels and direct message conversations that the user can navigate to by tapping.

![alt tag](https://raw.github.com/maximbilan/SwiftHUEColorPicker/master/img/img4.png)

Implement the <i>setupListeners</i> function to listen for changes in your channel and direct message conversation database collection data. Setup listeners for each of these collections:
<pre>
func setupListeners() {   

}
</pre>

Optional: Implement the <i>profileButtonPressed</i> function to determine how a user's profile screen should be presented:
<pre>
func profileButtonPressed() {   

}
</pre>

Implement the <i>createChannel</i> function to determine what happens networking-wise when a user creates a new channel:
<pre>
func createChannel() {   

}
</pre>

Optional: Implement the <i>signOutButtonPressed</i> function to determine what happens networking-wise when a user signs out of the app:
<pre>
@IBAction func signOutButtonPressed(_ sender: Any) {   

}
</pre>

<b>ProfileViewController</b>:
Contains the necessary functions of a profile page, which allows a user to change their profile picture in a profile setting, or a channel image in a channel info setting.

![alt tag](https://raw.github.com/maximbilan/SwiftHUEColorPicker/master/img/img4.png)

Implement the <i>uploadImage</i> function with the necessary networking logic to upload an image to your database:
<pre>
func uploadImage(image: UIImage, data: Data) {   

}
</pre>

<b>ChatViewController.swift</b>:
A class that consists of chat conversation functions. The two classes below subclass this class, each functioning as its own type of chat conversation screen.
1) <b>ChannelViewController.swift</b>, which is meant to handle group conversations.

![alt tag](https://raw.github.com/maximbilan/SwiftHUEColorPicker/master/img/img4.png) 

Implement the <i>setupMessagesListener</i> function to listen for changes in your channel conversation database collection data.
<pre>
func setupMessagesListener() {   

}
</pre>

Implement the <i>setupRecipientProfileImageListener</i> function to listen for changes in the channel's image database document data.
<pre>
func setupRecipientProfileImageListener() {   

}
</pre>

Implement the <i>addNewMessageToRecipientChatThread</i> function with the necessary networking logic to upload to your database:
<pre>
func addNewMessageToRecipientChatThread(message: Message) {   

}
</pre>

Optional: Implement the <i>profileButtonPressed</i> function to determine how a user's profile screen should be presented:
<pre>
func profileButtonPressed() {   

}
</pre>

Implement the <i>save</i> function to save a message being sent in the database:
<pre>
func save(_ message: Message) {   

}
</pre>

Implement the <i>loadMessageAsPhoto</i> function to determine how to load a photo as a message:
<pre>
func loadMessageAsPhoto(image: UIImage, url: URL) -> Message? {   

}
</pre>

Implement the <i>sendMessage</i> function to create a message object with the user's data and message text:
<pre>
func sendMessage(text: String) {   

}
</pre>

Implement the <i>sendPhotoAsAssetWithSize</i> function with the necessary networking logic to prepare an image in a safe to upload manner to be uploaded to your database:
<pre>
func sendPhotoAsAssetWithSize(asset: PHAsset, size: CGSize) {   

}
</pre>

Implement the <i>downloadImage</i> function with the necessary networking logic to download a photo message's image data from the database:
<pre>
func downloadImage(at url: URL, completion: @escaping (UIImage?) -> Void)) {   

}
</pre>

Implement the <i>uploadImage</i> function with the necessary networking logic to upload to your photo message's image data to the database:
<pre>
func uploadImage(image: UIImage, to chat: Chat, completion: @escaping (URL?) -> Void) {   

}
</pre>

2) <b>DirectMessageViewController.swift</b>, which handles one to one chat conversations.

![alt tag](https://raw.github.com/maximbilan/SwiftHUEColorPicker/master/img/img4.png)

Implement the <i>setupMessagesListener</i> function to listen for changes in your direct message conversation database collection data.
<pre>
func setupMessagesListener() {   

}
</pre>

Implement the <i>setupRecipientProfileImageListener</i> function to listen for changes in the receipient's image database document data.
<pre>
func setupRecipientProfileImageListener() {   

}
</pre>

Implement the <i>setupRecipientListeners</i> function to listen for changes in the recipient's conversation database collection data, as well as their status database collection data.
<pre>
func setupRecipientListeners() {   

}
</pre>

Implement the <i>addNewMessageToRecipientChatThread</i> function with the necessary networking logic to upload to your database:
<pre>
func addNewMessageToRecipientChatThread(message: Message) {   

}
</pre>

Implement the <i>updateRecipientStatusInMyDb</i> function with the necessary networking logic to upload to your database:
<pre>
func updateRecipientStatusInMyDb(chatUserStatus: inout ChatUserStatus, value: Bool) {   

}
</pre>

Implement the <i>updateMyStatusInRecipientsDb</i> function with the necessary networking logic to upload to your database:
<pre>
func updateMyStatusInRecipientsDb(chatUserStatus: inout ChatUserStatus, value: Bool) {   

}
</pre>

Optional: Implement the <i>profileButtonPressed</i> function to determine how a user's profile screen should be presented:
<pre>
func profileButtonPressed() {   

}
</pre>

Implement the <i>save</i> function to save a message being sent in the database:
<pre>
func save(_ message: Message) {   

}
</pre>

Implement the <i>loadMessageAsPhoto</i> function to determine how to load a photo as a message:
<pre>
func loadMessageAsPhoto(image: UIImage, url: URL) -> Message? {   

}
</pre>

Implement the <i>sendMessage</i> function to create a message object with the user's data and message text:
<pre>
func sendMessage(text: String) {   

}
</pre>

Implement the <i>sendPhotoAsAssetWithSize</i> function with the necessary networking logic to prepare an image in a safe to upload manner to be uploaded to your database:
<pre>
func sendPhotoAsAssetWithSize(asset: PHAsset, size: CGSize) {   

}
</pre>

Implement the <i>downloadImage</i> function with the necessary networking logic to download a photo message's image data from the database:
<pre>
func downloadImage(at url: URL, completion: @escaping (UIImage?) -> Void)) {   

}
</pre>

Implement the <i>uploadImage</i> function with the necessary networking logic to upload to your photo message's image data to the database:
<pre>
func uploadImage(image: UIImage, to chat: Chat, completion: @escaping (URL?) -> Void) {   

}
</pre>

## License

Banff Framework is available under the MIT license. See the LICENSE file for more info.
