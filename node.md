# Notes/Understanding Node.js 

Being a good Node.js developer is being a great JavaScript developer.

### Words in Node.js and their descriptions

1. CLI (Command Line Interface):
A utility to type commands to your computer rathen than clicking. Some examples include: Bash on Linux, Terminal on Mac,Command Prompt on Windows, and other replacements... The opposite to the command line is the GUI (Graphical User Interface). Mac typically uses -bash as it has a Linux core. 

2. Arguments:
Arguments are values you give your progrems that affect how it runs. (Essentially passing paramaters to a function).

3. Machine Code (Language) aka Machine Language
Programming Languages spoken by computer processors. Every program you run on your computer has been converted (compiled) into machine code. * It is compiled INTO the machine language that YOUR computer speaks. All code eventually becomes machine code. Machine Code is very low level making it pretty difficult to understand. This is why we typically compile programming languages into machine code. As time has gone by the level of abstraction has increased creating higher level languages. 

Machine Language -> Assembly Language -> C/C++ -> Javascript

4. ECMACRIPT
The standard javascript is based on. ECMA is the organization that basically standardizes the javascript that should be used accross browsers. 

5. Javascript Engine
A program that converts javascript code into something the computer processor can understand. V8 is a javascript engine, and it sits at the core of Node.js

6. Client-Server Model of Computing
The communication between the Client and the Server through a standard format which they both understand. Client request information from the server and the server responds. 

7. Breakpoint
A spot in our code where we tell a debugging tool to pause the execution of our code. Use VS Code for debugging. 

8. Module
A reusable block of code whose existence does not accidently impact other code. 

9. Common JS Modules
An agreed upon standard for how code modules should be structured. 

10. First-Class Function
A first-class function is the ability of everything you can do with certain data types you can do with functions. For example, you can use functions like a string, array, numbers, pass them around through parameters, put them in arrays, objects etc.

11. Function Expression
Function expression is just a block of code that results in a value. ex. let addition = function(a, b) { return a + b };
Function expressions are possible because JS functions are first-class. 

12. Object
Collection of name/value pairs

13. Inheritance
When one object gets access to the properties and methods of another object. 

14. Function Constructors
A normal function that is used to construct objects. The 'this' variable points to a new empty object and that object is returned from the function automatically. Every new object creates an empty prototype object that it points too. You can add methods and functions to the object by using the .prototype and attaching it to the object. To see what properties and methods an object has you can look down its chain using the .__proto__.


15. Primitives in JS
Primitives in JS include strings, numbers, booleans, null, undefined. Everything else is an object. 

16. Scope
Where in code you have access to a particular function or variables. 


17. JSON (JS Object Notation)
A standard for structuring data that is inspired by javascript object literals. JS engines are built to understand it. 

18. Revealing Module Pattern
Exposing only the properties and methods you want via a returned object. A very common and clean way to structure and protect code within modules. 

19. Events
Something that happns in our app that we can respond too. In Nod we actually talk about two different kind of events.

20. Event Listener
The code that responds to an event. Node.js just like the DOM uses an event emmitter to handle events in respects to its type case by case. You can create your own emitter easily which is powerful as it gives a control flow with callbacks and asynchronous code.

21. Magic String
A string that has some special meaning in our code. (This is bad becuase it makes it easy for a typo and bugs in our code). A nice module pattern for helping avoid bugs and string issues through a config.js module.

22. Template Literals
A way to concatenate strings in JS ES6.

23. Syntactic Sugar
A feature that only changes how you type something, but nothing changes under hood.

24. Asynchronous: More than one process running simultaneously. Synchronous: only one process running at a time. 

25. Callback: A function passed to some other function, which we assume will be invoked at some point. 

26. Non-blocking
Doing other things without stopping your programming from running. 

27. Buffer
A temporary holding spot for data being moved from one place to another. (Store it there temporary, intentionally limited in size).

28. Stream
A sequence of data made available over time.(pieces of data that eventually combine into a whole). E.g Think of streaming Netflix, you process data as you watch a show/movie.

29. Binary Data
Data stored in binary (sets of 1s and 0s).

30. Character Set
A representation of characters as numbers. Each char gets a number (Unicode and ASCII are character sets).

31. Character Encoding
How characters are stored in binary

32. Error-first Callback
An error first callback is any callback that that takes an error object as its first parameter (This is a standard).

33. Chunk
A piece of data being sent through a stream.

34. Abstract (Base) Class
A type of constructor you never work directly with, but inherit from. E.x streams We create new custom objects which inherit from the abstract base class. 

35. Protocol
A set of rules two sides agree on when communicating. Both the client and the server are programmed to understand and use that particular set of rules. 

36. IP/TCP
Internet Protocol and Transmission Control Protocol

37. HTTP (HyperText Transfer Protocol)
A set of rules (and a format) for data being transferred on the web. One of various formats that defines data being trasferred via IP/TCP. The core of how we send information through the web.

38. MIME Type
A standard for specifying the type of data being sent. Examples include: app/json, text/html, image/jpeg

39. Endpoint
One URL in a web api. Sometimes that endpoint(url) does multiple things by making choices based on the HTTP request headers. 

40. Serialize
Translating an object into format that can be stored or transferred. (JSON, XML). Deserialize is the opposite, converting the format back into an object. 

41. Routing
Mapping HTTP Request to Content. (Whether actual files exist on the server or not)

42. Package
A collection of code that it is managed and maintained ina  system

43. Package Managed System
Software that automates installing and updating packages

44. Dependency
Code that another set of code depends on to function 

45. Environment Variables
Global Variables specific to the environment our code lives in. 

46. Middleware
Code that sits between two layers of software. In the case of Express, it sits between the request and the response. 

47. REST - Representational State Transfer
An architectural style for building API's. We decide that HTTP verbs and urlss mean something. 
GOOD URL structure, which follows specific http methods the way that one would anticipate. It is mostly for communicating your routes and code to other programmers. 

48. Pipe
Connecting two streams by writing to ones stream what is being read from anbother. In Node you pipe from a Readable stream to a Writable stream. 

49. 

50. 

51. 

52. 

53. 

54. 
55. 
56. 



### Notes by Section

# Section 2: V8 The Javacript Engine

Processors, Machine Code and C++.
A microprocessor is a tiny machine that does work. Microprocessors typically speak one of these languages: IA-32, x86-64, ARM, MIPS. A processor is a physical thing thats a machine that accepts instructions and carries them out. Node is written in C++. The V8 JS Engine is written in C++. V8 is the thing that converts javascript into machine code.

V8 under the hood: (Google's v8 Engine)
Looking inside the v8 documentation provided by google, you can see all the low level microprocessors code as well as all the C++ (.h and .cc files) that compile our code and turn it into machine code. It's just a lot of code that is very efficient and very good. 

The power of the V8 engine. 
You can also embed the V8 engine into your C++ code to allow other users to use Javascript to add code to whatever you're doing or working on. Through embedding the V8 engine you give the power for javascript users to be able to do things only typically available to C++ code such as backend work (working with files, accessing databases), but with Javascript. This is incredibly powerful and how we get Node.js. V8 allows you to literraly create unique functions and syntax for javascript that is not specified in the ECMAScript. Allows for the extension of features to JS, V8 allows for that!!!

Summary: 
V8 is the engine that compiles the JS code into machine code for our microprocessors to read. Node.js is an extension of the V8 engine with additional C++ files that add features to JS such as back-end and server side use. 

# Section 3: The Node Core

Server: At its most basic, is a computer that performs services. The client asks for those services and ay also do some work, but the server does the heavier amount of work. Client request some work -> Server responds with something. 

What does JS need to manage a server? What does Node.js do?
1. Better way to organize our code into reusable pieces.
2. Ways to deal with files.
3. Ways to deal with databases.
4. The ability to communicate over the internet.
5. The ability to accept requests and send responses. (standard format)
6. A way to deal with work that takes a long time (asynchronous requests)

The Node Core (C++ Core) is a core of features/utilities built in C++ made available to JS via the hooks in the V8 engine. Node.js accepts JS and allows 

The JS Core is the core made up of features/utilities already built for you in JS to perform tasks. Most of those JS files are actually wrappers for the C++ code. (They get the code from the C++ files and they modify them using JS code)

# Section 4: Modules, Exports and Require

A module is a resuable block of code that does not affect other code accidently. With module exports you can expose functions, classes etc, data structures. 

```js
require('./greet') // to require other modules in the same directory
// you can't access variables from another module unless you explicitly design it to do so

module.exports = greet; // gives you direct access to the greet function

// Objects and Object Literals
var person = {
  firstName: 'Alejandro',
  lastName: 'Chang',
  greet: function() {
    console.log('Hello, ' + this.firstName + ' ' + this.lastName);
  }
}

person.greet();

console.log(person['firstName']) // Alejandro 
```

IIFE (Immediately Invoked Function Expressions) - A big part of what happens behind the scenes with modules, exports and require. As they have everything to do with modules and accesability and encapsulation/protection of other files that you don't want to be impacted. Node.js takes advantage of IIFE as it protects data/encapsulates data which is something modules do as well.

Modules more in depth: Everytime you create a module it creates a new Module object which is attached with properties and methods. One of the properties is the exports method which is assigned to an empty object initially. Once it has your actual module it's going to load the contents of your file. If you don't provide an extension, it will assume it is a '.js' file, that's how it knows. If you ever have to require a file that is not a 'js' file you have to include the extension. Then it officially sends it to the V8 engine through the compile property. During this process it wraps your code into a string of a function expression, which shortly after is immediately invoked. Module.exports is what is given back from require. 

Summary:
1. require is a function that you pass on a 'path' too.
2. module.exports is what that require function returns 

Overview: Modules are wraped in a function expression with paramaters (function (exports, require, module, _filename, _dirname){ your file });

Require turns JSON string into an object. ex. require('./greetings.json');

Module Patterns: 
1. Replacing the empty objust module.export = { // whatever }
2. Adding a method to the exports object.
3. Creating a new object using the new Object syntax
4. Creating a new object, but passing it along as constructor to your module
4. Revealing Module Pattern

Module caches youre require calls for whatever files you are importing into so you can use the same object across all of your application. By using Module Pattern 4, you can create new objects in your module and they will point to different parts in memory.

Always use module.exports > exports, it's less code and protects you from some bugs. 

Core Modules: Node.js has core modules that help engineers do a variety of things with handy methods and properties. You can find the documentation here: https://nodejs.org/api/index.html

ES6 Syntax:
```js
  // greet.js
  export function greet() {
    console.log('Hello');
  }

  // app.js
  import * as greeter from './greet';
  greeter.greet();
```

# Section 5: Events and the Event Emitter

Two types of Events:
1. System Events:
This comes from the C++ side of the Node.js Core thanks to a library called libuv. Events coming from the computer system. 

2. Custom Events:
They're inside the Javascript Core. Events that we can create for ourself. This is the Event Emitter.

The Node Event Emitter comes with on(), emit() and many more methods and properties. By using a config.js file where we place our 'magic strings' we avoid bugs with code that would be hard to decipher, as our magic strings become variables which our code editors can distinguish. 

Object.create() is a very simple, clean and clear way to set up a sequence of objects, of objects that inherit from one another, a prototype chain. This idea of setting this up is key to understanding the Event Emitter and many mother pieces of Node.js.

Prototypal Inheritance: Can be achieved through the function contructor of an object, ES6 extends class inheritance and Object.create().

**Inherting From the Event Emitter**
The Event Emitter uses internally Object.create() to create an empty object __proto__ that points down to the object you want to inherit from. Many objects built into Node are a type of event emitter. 

Object Literals are useful for call and apply, binding the contest of a particular function.

# Section 6: Asynchronous Code, libuv, The Event Loop, Streams, Files, and more…
Synchronous vs. Asynchronous: Asynchronous is basicall

The Event Loop - The Event Loop is what allows JS to become asynchronous. Through the EL, at its most basic JS uses a call stack, a heap(for memory allocation) and a queue. The call stack executes everything in JS that is synchronous, while all the events are placed on a queue for processing. Once the call stack is empty, the callstacks starts running asynchronous events one by one.
Summary: We are running synchronous JS while inside the C++ core of Node asynchronous processes are being handled.  

Buffer and Streams - In Node.js, stream and buffers refer to the idea of data being streamed a little bit at a time into a buffer which will allows us to process the data/stream in chunks. Ex. Netflix

Characters -> Character Sets(Unicode / ASCII) -> Character Encoding (binary data: 101010 )
JS is pretty bad at character encoding. Luckily due to the help of the V8 JS engine it helps us be able to process character encodings. Character Set - Numbers to letters, Character Encoding - Numbers in base 10 to Numbers in base 2
Byte: 8 bits - 8 zeroes and ones

Files and Fs - asynchronous vs. synchronous 
Always lean towards the asynchronous approach. As your files get bigger and your users increase you want to be able to deliver the best experience possible. This is done through the Event Loop and through using asynchronous operations. It will make it more performant and make it seem faster. 

Streams:
Streams are event emitters. Any streams created have access to on() and emit(). There used to be just streams but now there is 'types' of streams. Readable(can only read data), writable(can send data to stream), duplex(both reads and sends), transform streams(changed data as you move through the stream) etc. Streams are an abstract class. You can build your own stream. Writable and readable from Node's perspective. Request from Nodes perspective is readable. Nodes response to browser is writable. It's almost the opposite. Streams typically take data in buffers, and can be used to copy that data and manipulate it (ex. copy the data).

Piping sending a stream that was readable and pasasing it alon thorugh a writable stream (you can chain the piping of srtreams this way). Pipe the chunk(of data) along streams. 

Node likes to use streams, as long as a stream is correctly implemented, we can read write and pipe data wherever we want. To a database between servers etc. This is powerful and really the node way of thinking about data. It helps Node be performant. We should we always be thinking about where can I use a stream. Minimizing the memory and improving speed. 

Asynchronous + streams = performance. 



# Section 7: HTTP and being a Web Server
IP: Internet Protocol(IP) - a sequence of numbers that uniquely identifies that computer 

HTTP - For web
FTP - For Files
SMTP - For Emails

They're traveling from computer to computer sending information. The way to send those protocols revolves around TCP. 
TCP: Transmission Control Protocol. TCP takes that information and splits it into pieces throught the socket. Each indivdual piece is a packet. Your operating system has these abilities, Node.js provides the ability to access those features of your operating system. 

Port: Once a computer receives a packet, how it knows what program to send it to. 
Streams and Performance: Streams are just a wrapper on the idea of dealing with data a chunk at a time. 

Browser -> domain name -> maps to IP address(request) -> Web Server -> looks specifically for the port for what you're looking for. We assign a specific port to different protocols. What is the port that we're 'listening' to?
Most unsecure websites, the port that information is being sent from is port 80. There are lots of ports that by default are being used by different things. 

HTTP Parser
A C program it parses request and responses and other binary data. Knows what to do with the data that is passed onto it. 

API give and receive data to work with and get assistance in building software applications. Most of the data now in days is JSON. 
Sending and receiving data in HTTP responses is very convenient and the ultimate way to transfer data in JS. It is a very simple way to build API's that you can use in all kinds of applications. Object -> JSON 
Endpoint: One URL in a web API. Sometimes that endpoint (URL) does multiple things by making choices based on the HTTP request headers. Give and receive data in a variety of formats (mostly JSON).

Serialization: obj -> json, deserialization: json -> obj. And this is an API. 
Routing in the server can be easily obtainable through the writeHeaders and the request url's. Routing at its most basic point is mapping http request to its content. Whether there are files that are on the server or not. Manually dealing with these routes is pretty tough, writing a seperate url for everything you want ot do is complicated. Express helps with that.

# Section 8: NPM The Node Package Manager 
The largest ecosystem in open source code. A package is just code(managed and maintained with a package management system). A package management system such as NPM is software that automates and facilitates installing and updating packages. (Deals with what version you have or need and manages dependencies).
Dependency: Code that another set of code depends on to function. (Apps have dependencies, if you use it in your code, it needs it to function). 

When you install packages through NPM, they come from the NPM registry. You can look at the registry and read on packages at their website: www.npmjs.com.

Semantic Versioning: Specifying what version of a set of code this is. Ex. 1.7.2 Major.Minor.Patch.
Patches: Typically bugs and miniscule changes on a version.
Minor: Typically some new features were added. Your code should continue to work fine. 
Major: Typically Big changes. Your code might break. Take a good look of the code and document any changes. 

NPM init, nodemon and package.json. Npm init is just a json deo that quickly sets up your app name, purpose and scripts for you to access your application and configure it to your needs. All the npm packages are structured as node modules. As soon as you download from the npm registry, ex:

```js
  npm install moment --save
```

--> it creates a node_modules folder that holds and organizes your modules downloaded from the npm registry. Package.json is updated automatically adding the dependencies you requested. In this case moment from NPM. A carat ^1.1.1 is very important in dependencies. The carat allows npm to update anything within the major release of a dependency. If you change to a tilde ~1.1.1 it means don't update my packages only minor patches. After this, you can go and give the package.json to someone else, which allows other to download the dependencies and use your application. 

In the bigger scope most node_modules have other node_modules which could have their own node_modules. Essentially you can think about it as nested dependencies, as certain pieces of code need their own dependencies to function. 



# Section 9: Express
HTTP Method: Specifies the type of action the request wishes to make. (GET, POST, DELETE). Also called verbs.

Work that happens between the request and the response. This is what Node/Express is good for. 