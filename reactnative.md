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

