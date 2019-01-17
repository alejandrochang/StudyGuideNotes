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

24. 
25. 
26. 


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

