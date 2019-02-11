# React Native Notes

What is React Native?
"Learn once write everywhere". React Native is all about embracing the differences that exist within Android and IOS. You learn how to use a toolset with different platforms to adjust your code and reuse big chunks of code. Build real mobuile apps using React Native and JS.

React Native is NOT a Web App running on mobile device. It is not a web app hosted by webview in native app. 
We have a real nativ application. JS + React Native App compiled to Native Code. (We use both libraries: React + React Native)
We don't have DOM Elements. React Native gives us other components which can be compiled to Native Code. (Alternative DOM)

1. React (Web)
<div></div>
<input />

2. Native Component (Android)
android.view
EditText

3. Native Component (IOS)
UIView
UITextField

4. React Native
<View> - Knows the translations for Android and IOS
<TextInput>

UI -> Components Exposed by React Native 
Logic -> Written by us in JavaScript (JS Thread hosted by React Native App)

You can use expo App on your phone or computer to see the layout you're expecting. 

### Limitations of React Native
- No or very little Cross-Platofrm styling components
Solution: Style components on your own or use 3rd party libraries. 
- Only a basic set of pre-built components
Solution: Build components on your own or use 3rd party libraries. 
- Tools to create Responsive Designs but no responsiveness out of the box
Solution: Create responsive designs on your own(check for device size and OS). 

### React Native is a fast moving target
New versions every month, breaking changes do occur, high-dependency on 3rd party packages and bugs. 

### Basics of React Native Apps
In its cose it uses React. React Native is like a wrapper to create components. Doesn't care if they run on the web or the device. React Native is a real native app. Use the components provided by React Native. 

JSX Elements can/can't use: 

View:                       The most fundamental component for building a UI.

Text:                       A component for displaying text.

Image:                      A component for displaying images.

TextInput:                  A component for inputting text into the app via a keyboard.

ScrollView:                 Provides a scrolling container that can host multiple components and views.

StyleSheet:                 Provides an abstraction layer similar to CSS stylesheets.



