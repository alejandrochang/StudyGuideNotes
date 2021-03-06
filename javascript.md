# JavaScript

### What is the Event Loop?
Is essentially what allows JavaScript to use callbacks and promises. 
There are four components in the event loop: Heap, Call Stack, EventTable & EventQueue.

Heap: Is used for memory allocation of differnet objects in unordered manner.

Call Stack: When you're about to execute a function it is added to the call stack. Then if that function has an inner function that is stacked on the previous function and so forth. (LIFO)

Ex. An example of this can be seen when you get an error in your console which shows you the path of execution

EventTable & EventQueue: Every time you call a setTimeout function or perform an async operation it is added to the EventTable. Once that event occurs(timeout, click, mousemove) it sends a notice. The EventTable does not execute functions, it's sole purpose is to keep track of events and send them to the EventQueue. The EventQueue receives the order in which the functions should be executed. This is where the Event Loop comes in as it checks the Call Stack, if it is empty, then it looks into the EventQueue, if there is something there it will process it into the Call Stack and execute it. (FIFO)


### What is lexical scoping?
JavaScript has lexical scoping with function scope meaning a new scope is created with every new function created.

### What is reflection in Javascript?
An object can look at itself, listing and changing its properties and methods.

### === ?
```js
  const numbers = [1, 2, 3, 4];
  numbers === [1, 2, 3, 4] // false

  // The comparison is not in the contents of the array, but instead where they're allocated in memory

```
### What are the two JS data types?
There are primitives and there are objects. 
Primitives include: Boolean, Null, undefined, number, string and symbol (ES6). Primitives have no methods and are simply not objects.

Everything else is an object.

### Proper key works for error handling in jS?
"try...catch"

### Function Declaration vs. Function Expression?
Function declarations defines a function with the specified parameters. The function expression is a function that can be declared/assigned to a variable, const etc. Function declararations are hoisted to the top of the program while function expressions aren't. 

### What does the return of [1].push([1]) produce?
The above code prints out 2, as the .push() method returns the length of the array. 

### What's the difference between asynchronous and synchronous API?
A synchronous API waits for a response, and blocks everything else from happening in the application until that response is received. 
An asynchronous API does not wait for a response, but instead asks to be notified when a response is available. As a result it does not block other functionality in the application from progressing. 

### Classical vs Prototypal Inheritance?
Classical inheritance is what more traiditional languages such as Java and C# use to give access to objects properties and methods of other objects. However classical inhertiance leads to coupling/dependencies of other objects as it is very verbose. Prototypal inhertiance is extensible and more flexible. 

### What is inheritance?
Inheritance is when one object gets access to the properties and methods of another object. 

### Give a high level overview of what an object's prototype represents
A prototype is the object that an object inherits from.

### What are the differences between the __proto__ and prototype attributes?
Obj.prototype is a property of a Function object that has a constructor that points back to itself. The __proto__ attribute is accesable by any object in JS which creates the prototype chain.

Obj.__proto__ is internal property of an object, pointing to its prototype.

### What happens when we do or don't explicity set an object's prototype?
DONT: The default "prototype" is an object with the only property constructor that points back to the function itself.

DO: if we replace the default prototype as a whole, then there will be no "constructor" in it

### What is an object's default prototype?
Obj.prototype = { constructor: Obj } if it is a function.
If its a regular object, the obj.prototype will be undefined.

### What is the prototype chain?
Essentially the prototype chain is the chain of objects that are connected through their object __proto_. The prototype chain is how objects inherit in javascript. 

### What are the valid values for an object's prototype?
Either an Object or NULL

### What are the benefits of a Javascript closure?
Closure allows a function to access variables from an enclosing scope even after it leaves the scope in which it was declared. They're useful because they let you associate some data with the lexical environment. This is particularly useful with frontend development as we have a lot of event handling. This event handling can be handled through callbacks that make our page easily interactive. 
```js
  function makeSize(size) {
    return function() {
      document.body.style.fontSize = size + 'px';
    }
  }

  let size12 = makeSize(12);
  let size14 = makeSize(14);
  let size16 = makeSize(16);

  document.getElementById('size-12').onclick = size12;
  document.getElementById('size-14').onclick = size14;
  document.getElementById('size-16').onclick = size16;

  <a href="#" id="size-12">12</a>
  <a href="#" id="size-14">14</a>
  <a href="#" id="size-16">16</a>

```

### Formally define a Javascript closure
Variables defined outside the scope of a function that are used in the function.

### Give an example of a closure
```js
function SpringfieldSchool() {
  let staff = ['Seymour Skinner', 'Edna Krabappel'];
  return {
    getStaff: function() { console.log(staff) },
    addStaff: function(name) { staff.push(name) }
  }
}

let elementary = SpringfieldSchool()
console.log(elementary)        // { getStaff: ƒ, addStaff: ƒ }
console.log(staff)             // ReferenceError: staff is not defined
/* Closure allows access to the staff variable */
elementary.getStaff()          // ["Seymour Skinner", "Edna Krabappel"]
elementary.addStaff('Otto Mann')
elementary.getStaff()          // ["Seymour Skinner", "Edna Krabappel", "Otto Mann"]
```


## What is data encapsulation?
the idea that some data or functions should not be directly exposed, it's hidden in the closure

### What is the difference between the memory heap and call stack in javascript?
The heap is for memory allocation. The call stack is a list of things to do, one task at a time

### What is one problem with programming languages that a fully single-threaded
It can only do one thing at a time which can cause slowing of any application.

###  Is Javascript a single-threaded language? Explain (Hint: This may not be a yes or no question)
JS by itself is single-threaded, but HTML5 and Node have access to multi-threading behavior.

### When is using an IIFE necessary?
An Immediate Invoked Function Expression (IIFE) is a function expression that is called immediately after you define it. It is usually used when you want to create a new variable scope.

### What is the syntax for an IIFE?
The (surrounding parenthesis) prevents from treating it as a function declaration.
The final parenthesis() are executing the function expression.

``` js
var result = [];
for (var i=0; i < 5; i++) {
  result.push( function() { return i } );
}
console.log( result[1]() ); // 5
console.log( result[3]() ); // 5
result = [];
for (var i=0; i < 5; i++) {
  (function () {
    var j = i; // copy current value of i
    result.push( function() { return j } );
  })();
}
console.log( result[1]() ); // 1
console.log( result[3]() ); // 3
```


### In which phase does hoisting occur?
Compilation phase.

### What is the difference between function hoisting and variable hoisting?
Function declarations are completely hoisted. This means that a declared function can be called before it is defined.

Variables are partially hoisted. var declarations are hoisted but not its assignments. let and const are not hoisted.

### What does the new keyword do in Javascript?
1. Creates a new object.
2. Sets the object’s prototype to be the prototype of the constructor function.
3. Executes the constructor function with this as the newly created object.
4. Returns the created object. If the constructor returns an object, this object is returned.

### What type of function is invoked with the new keyword? What does this function return?
Constructor Functions, returns an object

### What is event bubbling?
 Event bubbling relates to the order in which event handlers are called when one element is nested inside a second element, and both elements have registered listener for the same event (a click, for example)

event.target – the deepest element that originated the event.
event.currentTarget (=this) – the current element that handles the event (the one that has the handler on it)
event.eventPhase – the current phase (capturing=1, bubbling=3).

### The 3 phases of event propagation?
Event Capture Phase:
In this phase only the capturer listeners are called, namely, those listeners that were registered using a value of true for the third parameter of addEventListener. Only the capturers found on the path from the window to the event target parent are called.

Event Target Phase: 
In this phase all the listeners registered on the event target will be invoked, regardless of the value of their capture flag.

Event Bubbling Phase:
During the event bubbling phase only the non-capturers will be called. That is, only the listeners registered with a value of false for the third parameter of addEventListener()

### How can you stop event bubbling?
event.stopPropagation()

### What is the difference between event.target and event.currentTarget?
event.target – the deepest element that originated the event.
event.currentTarget (=this) – the current element that handles the event (the one that has the handler on it)

### What does stopImmediatePropagation do?
stops the bubbling and prevent handlers on the current element from running

### What is event delegation?
Event Delegation is using an event handler on the parent of several children to enact the same action on the children, instead of using individual event handlers


### Discuss 4 differences between ES5 and ES6 that you find important
Block Scope: ES5 only had function level scoping, ES6 gives you block level with let and const
Arrow Funtions: gives you lexical "this"
Rest Parameters: lets you array functions on arguments
Classes: helps translate to other OOP languages

### What are the steps of a try..catch block in Javascript?
The code in TRY is run. IF there are no errors, CATCH is ignored. If an error does occur, ignore the rest of TRY and go to CATCH

### What type of errors do try..catch blocks work for?
only Runtime Errors

### When creating a custom error, what attributes should it have?
Message, Name, Stack

### Select the correct statement(s) about the new keyword
B) It returns a new object, even if the function doesn't create one
D) It sets a prototype on the object it returns
E) It sets the context of this within the function to the new object that the function will return

### What's the difference between the DOMContentLoaded and load event triggers?
DOMContentLoaded – the browser fully loaded HTML, and the DOM tree is built, but external resources like pictures <img> and stylesheets may be not yet loaded.
load – the browser loaded all resources (images, styles etc).

### Discuss the differences between let, const, and var. What are their respective scopings?
let and const are block scoped, var is not
let can be changed, const can only change its properties
let and const are not hoisted, var declarations are hoisted but not their assignment


### What happens when you enable strict mode in javascript?
You cannot create variables/functions without declaring them first, you cannot delete a variable/functions once declared and assigned. 'This' holds the value of undefined in global functions and in anonymous functions that are not bound to any object. 

### How does the rest/spread operator work in JS?
Rest (...args) can be passed into a function as a variable that accepts any number of arguments
function showName(firstName, lastName, ...titles)

Spread (...arr) takes an array and lists the elements as individual arguments
let arr1 = [1, -2, 3, 4];
let arr2 = [8, 3, -8, 1];
Math.max(...arr1, ...arr2) 

Rest is passed as the last argument in a function typically, while spread is used in multiple different ways.


### What problem does bind solve in Javascript? How does it accomplish this?
Losing "this"; bind returns a “bound variant” of function that fixes the context this and first arguments if given.
Usually we apply bind to fix this in an object method, so that we can pass it somewhere.

### How can we solve context issues in JavaScript?
``` js
var cat = {
   name: "Gus",
   color: "gray",
   age: 15,
 
   printInfo: function() {
      var that = this; // 1
      console.log("Name:", this.name, "Color:", this.color, "Age:", this.age); //prints correctly
 
      nestedFunction = function() {
         console.log("Name:", that.name, "Color:", that.color, "Age:", that.age); //prints correctly
      }.bind(this); // 2

      nestedFunction.call(this); // 
      nestedFunction.apply(this) // 4

   nestedFunction();
   }
}
cat.printInfo();
```

You can assign this to a variable, typically 'that'.
You can bind the context this.
You can call/apply the context to this. 

Note: Call and apply invoke your function. 


### What is the syntax for passing arguments to the bind function?
function.bind(context)

### What does the length attribute refer to on a Function in Javascript?
returns the number of function parameters
``` js
function f1(a) {}
function f2(a, b) {}
function many(a, b, ...more) {}

alert(f1.length); // 1
alert(f2.length); // 2
alert(many.length); // 2, rest not included
```


### Explain the differences between a Function Expression and Function Declaration
A Function Expression is created when the execution reaches it and is usable from then on — it is not hoisted.
```js
var sum = function(a, b) {
  return a + b;
}
```

A Function Declaration can be called both before and after it was defined — it is hoisted.
``` js
function sum(a, b) {
  return a + b;
}
```


<!-- WEEK 4 -->

### Does JS assign variables by value or by reference?
for primitives, JS stores by value. for objects and functions, JS stores by reference

### What are the 7 different JS types?
as of ES6: null, undefined , boolean, number, string, object and symbol

### Explain the difference between + and -*/ in JS when it comes to coercion.
+ can be used for math and coercion, -*/ can only be used for math operations

### How does prototypal inheritance work?
Objects inherit directly from other objects with Object.create() or Object.assign(), as opposed to Classical Inheritance where object inherit from classes


### What's the JS Global Object?
The overarching place where variables and functions are provided and shared between multiple scripts (window in browser, global in node)

<!-- WEEK 5 -->

### What is a Promise?
A promise represents the eventual result of an asynchronous operation. It is a placeholder into which the successful result value or reason for failure will materialize.

### what arguments does the Promise object take?
resolve, reject

### what arguments does the resolve function take?
value

### What arguments does .then take?
a result function and error function

### explain .then in the context of the callback queue
.then takes in a callback that can be written inside its argument, whereas a callback must be defined beforehand

### What is Promise Chaining?
a way to execute async tasks in succession

### Explain what is returned by .then
another promise that is to be resolved

### How can you suspend the execution of a .then statement?
return a promise without resolving it

### When would you want to use Promise.resolve()?
The method is used when we already have a value, but would like to have it “wrapped” into a promise.

### Explain how Promise.all works.
The method to run many promises in parallel and wait till all of them are ready. It takes an iterable object with promises, technically it can be any iterable, but usually it’s an array, and returns a new promise. The new promise resolves with when all of them are settled and has an array of their results.

### What happens when you pass a non-promise object in the iterable you pass to Promise.all?
It is treated as Promise.resolve(non-promise object)


### What is Promise.race
takes an iterable of promises, but instead of waiting for all of them to finish, it waits for the first result (or error) and goes on with it


### What does the async keyword do?
“async” before a function means a function always returns a promise. If the code has return (non-promise) in it, then JavaScript automatically wraps it into a resolved promise with that value

### What does the await keyword do?
await is used inside an async function. await makes JavaScript wait until the promise settles and returns its result

### what does console.dir() do?
Displays an interactive list of the properties of the specified JavaScript object. The output is presented as a hierarchical listing with disclosure triangles that let you see the contents of child objects.


### What is currying?
Translating a function from callable as f(a, b, c) into callable as f(a)(b)(c).
Function currying also known as partial function application is the use of a function that accepts one or more arguments that returns a new function with some of the arguments already set. 

### What extra features do you get when using lodash.curry?
return a wrapper that allows a function to be called normally when all arguments are supplied or returns a partial otherwise

### Why might you use currying?
currying allows both to keep the function callable normally and to get partials easily

### What are template literals?
${} template literals allow both multiline string and string interpolation.

### What is a variadic function?
Variadic functions are functions that accept any number of arguments instead of a fixed number of arguments. 

### ES5 Generators (iterator-authoring)

### What are REST conventions?
Are a predefined system for defining routes that work with a given type of record. 

Action                        |             Method           |              Route

List all records                            GET                             /streams
Get one particular record                   GET                             /streams/:id
Create record                               POST                            /streams
Update record                               PUT                             /streams/:id
Delete a Record                             DELETE                          /streams/:id

Following RESTful conventions allows for other engineers to make it easier to work with software that you design.

Ex. You can use JSON SERVER: https://www.npmjs.com/package/json-server
1. Create a db.json file
2. Create your oject 'schema'
3. Fetch your data through your actions/axios
4. load data through componentDidMount
5. use cat db.json to see the results of your objects