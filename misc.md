# MISC

### Name 5 benefits of HTML5
Accessibility, VA Support, Cleaner Code, Local Storage, Mobile Support

### What is localStorage? How might you use it?
It’s a little bit of a cross between regular old cookies and a client-side database. It’s better than cookies because it allows for storage across multiple windows, it has better security and performance and data will persist even after the browser is closed.

### Why are media queries useful?
Media query is a CSS technique introduced in CSS3.It uses the @media rule to include a block of CSS properties only if a certain condition is true.
Media queries extend the usefulness of media types by allowing more precise labeling of style sheets. This enables the content's presentation to be customized to a specific range of output devices without having to change the content itself.

### What is mobile-first design? Be as specific as possible.
designing for mobile before designing for desktop or any other device

### In which order do the React Lifecycle methods (including the optional ones) run?
componentWillMount
componentDidMount
componentWillReceiveProps
shouldComponentUpdate
componentWillUpdate
componentDidUpdate
componentWillUnmount


### In which lyfecycle methods should you make asynchronous fetches for data?
componentDidMount

### In which lyfecycle methods can you call setState?
componentDidMount
componentWillReceiveProps
componentDidUpdate


### Give one explanation for why we have to make AJAX requests in componentDidMount
You can’t guarantee the AJAX request won’t resolve before the component mounts. If it did, that would mean that you’d be trying to setState on an unmounted component, which not only won’t work, but React will yell at you for. Doing AJAX in componentDidMount will guarantee that there’s a component to update.

### What is a state tree in the context of Redux?
A JS object that contains all the information, data, and UI state of an application

### Why don't we want to modify (i.e. mutate) our redux state?
The second principle of Redux is that the state tree is read only. You cannot modify or write to it. Instead, anytime you want to change the state, you need to dispatch an action. Using reducers helps minimize mistakes.

### What is a pure function? Impure function?
The pure functions are the functions whose returned value depends solely on the values of their arguments. Pure functions do not have any observable side effects, such as network or database calls. The pure functions just calculate the new value. You can be confident that if you call the pure function with the same set of arguments, you're going to get the same returned value. They are predictable. Also, pure functions do not modify the values passed to them. For example, squareAll function that accepts an array does not overwrite the items inside this array. Instead, it returns a new array by using items map.

On the opposite, impure functions may call the database or the network, they may have side effects, they may operate on the DOM, and they may override the values that you pass to them. This is going to be an important distinction because some of the functions that you're going to write in Redux have to be pure, and you need to be mindful of that.

### Describe in detail what a redux reducer is. What makes it a pure function?
A Reducer is a pure function that describes state mutations by taking the previous state of the app, the action being dispatched, and returns the next state of the app. 
A Reducer does not modify the state given to it. It has to be pure, so it has to return a new object.

### What is the role of the store in Redux?
It holds current application state, dispatch actions, and uses reducers to update the state

### What does the subscribe method do in Redux?
It lets you register a callback that the Redux store will call any time an action has been dispatched, so that you can update the UI of your application. It will reflect the current application state.

###  What are presentational components?
Components that don't specify any behaviors, and that are only concerned with how things look or how they render

### Select the correct statement(s) about Redux
B) Reducers can call other reducers**
E) functions that are subscribed to the store will fire when the store is changed
G) Object.assign overwrites properties in order of how its arguments are received, even when the first object has those properties
H) combineReducers is shorthand syntax that defines the slices of state and which reducers to pass these slices to
K) The purpose of a container component is to subscribe to the store and to calculate the props that will be passed to the presentational component


### Explain Context in React
Context provides a way to pass data through the component tree without having to pass props down manually at every level.

### What does the <Provider> component do?
All Consumers that are descendants of a Provider will re-render whenever the Provider’s value prop changes. 

### In which order does SQL execute its queries? Make sure to mention SELECT, JOIN, WHERE, and aggregate functions such as GROUP BY
SELECT => FROM => JOIN => GROUP BY => HAVING => SELECT => DISTINCT => ORDER BY => LIMIT/OFFSET

### Where in a SQL query may we use a sub query (After which SQL keyword) 
after FROM

 What is Moore's Law?


### Describe the effects of using Group By and Having
 A group by is a query that takes a table and summarizes it into another table. You summarize the original table by grouping the original table into subsets (based upon the attributes that you specify in the group by). Each of these groups will yield one tuple.

The Having is simply equivalent to a WHERE clause after the group by has executed and before the select part of the query is computed.

<!-- WEEK 4 -->
### What is a symbol when talking about transmitting data?
States of voltage to represent information (binary )

### How is information transmitted over wireless signal?
Radio waves by varying voltage at a high frequency are sent from an antenna and a receiver picks up the radio waves and converts it back to a signal

### How do two computers ensure that the signal that is sent between them is interpreted correctly?
There is a data signal being synced with a clock to ensure proper reading

### What happens when the clocks become unsynchronized?
A clock slip, information goes missing or more information is added

### How do computers synchronize their clocks?
GPS Antenna with atomic clocks

### What is manchester coding?
It's a way to send information through voltage changes rather than syncing absolute voltages with time 

### What is framing?
a sequence of 1' and 0's that alert the receiver when a series of 1/0's should be considered data 

### What is a frame delimiter?
after an alternating series of 1 and 0, the frame delimiter is a 10101011 sequence that signals the next byte is the start of data 

### What is bit stuffing?
adding extra 1's or 0's to signify that a particular sequence is not a flag for something else

### What is Address Resolution Protocol?
Address Resolution Protocol (ARP) is a protocol for mapping an Internet Protocol address (IP address) to a physical machine address that is recognized in the local network

### What is the purpose of TCP?
provides a byte stream service that is connection oriented (connection has to made first) and reliable (sends request again if no ACK is received). if data is too large to send, TCP will break it up into small parts and send it

### What is a frame check sequence?
A number at the end of the frame that is created from the previous sequence to detect corruption in the frame. A sender will create the sequence from the sequence and the receiver will create the sequence again and match them up to make sure no data was corrupted 

### What is a MAC address?
an identifier for routers to know what devices to send data to

### How do packets get transferred around the internet?
Internet Protocol (IP) Addresses. Data is sent from one network with an IP address to and from another network.  A router will look at a PPP address that is wrapped around an IP address and will be routed accordingly

<!-- WEEK 5 -->

### Top 10 ways to speed up a website
1. Minimize HTTP requests
2. Minify and combine files (js, html, css
3. Use asynchronous loading for CSS and JavaScript files
4. Defer JavaScript loading
5. Minimize time to first byte
6. Reduce server response time
7. Choose the right hosting option for your needs
8. Run a compression audit
9. Enable compression
10. Enable browser caching

### How can you speed up a website?
1. Avoid manually authoring CSS/JS in the middle of your HTML (automating this process with tools is preferred)
2. Place CSS towards the top, place JS towards the bottom
3. Using async calls for third party requests
4. Combine multiple css files
5. Use <link> instead of @import

### What is the DOM?
The backbone of an HTML document are tags. According to Document Object Model (DOM), every HTML-tag is an object. Nested tags are called “children” of the enclosing one. The text inside a tag it is an object as well. All these objects are accessible using JavaScript.

### What happens when you omit the head tag or the body tag in your HTML?
It will automatically be added

### What happens if you inlclude more tags after the tag?
They become nodes in the DOM

### What kind of object is returned by .childNodes?
a special array-like iterable object

### Talk about the different ways you can access DOM elements in jS
Parent, Siblings, Children

### What are two important properties of DOM collections?
Read only: We can’t replace a child by something else assigning childNodes[i] = ...
LivE: If we keep a reference to elem.childNodes, and add/remove nodes into DOM, then they appear in the collection automatically.

### What's the difference between calling .childnodes and calling .children?
.children shows only elements (div, ul, script)

### What happens if you set innerHTML to a script?
If innerHTML inserts a script tag into the document – it doesn’t execute.
It becomes a part of HTML, just as a script that has already run.

### What does the .hidden property do?
.hidden specifies whether the element is visible or not.

### What does data before action mean?
Decomposing problems into data types first then executing actions on those data structures

### What are the components of a class?
Field and Methods

### What is encapsulation?
the idea that fields of an object instance can only be read or written by methods of that instance's class

### what is the difference between public and private methods?
public member of a class are visible anywhere which means it is ok to access them from outside their own class. private members are meant to only be accessed by methods of the same class

### What is the rationale for writing services?
When you have to support multiple clients using different protocols. It’s  beneficial to use services from your controllers in order to encapsulate domain, application, and infrastructure logic and preserve the cohesiveness of your domain mode

### What is the idea of creating services?
To keep Rails controllers clean and DRY


### Explain the syntax flex: 1, flex: 2, etc.
 Flex: 1 is a baseline width. A container "A" using Flex: 2 and a container "B" using Flex: 3 will have container A taking up 40% of the width and B taking up 60%

### What is the default value of align-items in the flex world?
 Stretch

### What is flex-basis?
The flexbox way of using WIDTH

### Explain flex-wrap
When screen widths drop below a certain amount, containers will wrap to the next line if needed

### what is margin: auto used for?
It centers a child horizontally and vertically when the parent container is set to display: flex


### Explain the difference between inline and inline block
INLINE: The default value for elements. Think of elements like <span>, <em>, or <b> and how wrapping text in those elements within a string of text doesn't break the flow of the text. An inline element will not accept height and width. It will just ignore it.

INLINE BLOCK: An element set to inline-block is very similar to inline in that it will set inline with the natural flow of text (on the "baseline"). The difference is that you are able to set a width and height which will be respected.


### Explain display: block
Block level elements do not sit inline but break past them. By default (without setting a width) they take up as much horizontal space as they can.

### What does position relative and absolute do?
an element’s original position remains in the flow of the document, just like the static value. But now left/right/top/bottom/z-index will work. The positional properties “nudge” the element from the original position in that direction.


### Explain floats and clears
Float allows divs to be placed somewhere and have text wrap around that image. An element that has the clear property set on it will not move up adjacent to the float like the float desires, but will move itself down past the float.

### Explain the clearfix
Rather than setting the overflow on the parent, you apply an additional class like "clearfix" to it. Then apply this CSS:
``` css
.clearfix:after { 
   content: "."; 
   visibility: hidden; 
   display: block; 
   height: 0; 
   clear: both;
}
```
This will apply a small bit of content, hidden from view, after the parent element which clears the float.