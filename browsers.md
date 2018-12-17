# BROWSERS

### What are some ways to deal with compatibility issues with CSS3 and older browsers?
There are a couple of JavaScript solutions that can help us serve responsive websites to older browsers lacking CSS3 support: 
Respond.js: all it needs: <script type="text/javascript" src="js/respond.min.js"></script>

Modernizr: Tells you wherether the current browser has this feature natively or not.After the first phase of detecting features, Modernizr creates a JavaScript object with the results and adds classes to the HTML element for you to target with your CSS. It’s a gorgeous solution, because it makes it easy for you to write conditional JavaScript and CSS to handle each situation, whether a browser supports a feature or not.

adaptive.960.js:

Proble ex: Media Queries do not work on older browsers. 

### Media queries?
In CSS2 the @media rule was introduced allowing for different styling rules withing media types. In CSS3 media queries where added which allowed to check things such as width/height of the viewport, width/height of the device, orientation and resolution. Media queries look for the capability of the device instead of the type of device. 
