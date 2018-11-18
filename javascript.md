# JavaScript

### Give a high level overview of what an object's prototype represents
A prototype is the class that an object inherits from

### What are the differences between the __proto__ and prototype attributes?
Obj.prototype is a property of a Function object. It is the prototype of objects constructed by that function.

Obj.__proto__ is internal property of an object, pointing to its prototype.

### What happens when we do or don't explicity set an object's prototype?
DONT: The default "prototype" is an object with the only property constructor that points back to the function itself.

DO: if we replace the default prototype as a whole, then there will be no "constructor" in it

### What is an object's default prototype?
Obj.prototype = { constructor: Obj }

### What are the valid values for an object's prototype?
Either an Object or NULL

### What are the benefits of a Javascript closure?
Closure allows a function to access variables from an enclosing scope even after it leaves the scope in which it was declared

### Formally define a Javascript closure
Variables defined outside the scope of a function that are used in the function

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
It can only sun one thing at a time which can cause slowing

###  Is Javascript a single-threaded language? Explain (Hint: This may not be a yes or no question)
JS by itself is single-threaded, but HTML5 and Node have access to multi-threading behavior

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
Compilation phase

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
You cannot create variables/functions without declaring them first, you cannot delete a variable/function once declared and assigned, 

### How does the rest/spread operator work in JS?
Rest (...args) can be passed into a function as a variable that accepts any number of arguments
function showName(firstName, lastName, ...titles)

Spread (...arr) takes an array and lists the elements as individual arguments
let arr1 = [1, -2, 3, 4];
let arr2 = [8, 3, -8, 1];
Math.max(...arr1, ...arr2) 


### What problem does bind solve in Javascript? How does it accomplish this?
Losing "this"; bind returns a “bound variant” of function func that fixes the context this and first arguments if given.

Usually we apply bind to fix this in an object method, so that we can pass it somewhere.


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
A promise is a special JavaScript object that links “producing code” and the “consuming code” together

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
translating a function from callable as f(a, b, c) into callable as f(a)(b)(c)

### What extra features do you get when using lodash.curry?
return a wrapper that allows a function to be called normally when all arguments are supplied or returns a partial otherwise

### Why might you use currying?
currying allows both to keep the function callable normally and to get partials easily