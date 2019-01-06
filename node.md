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

6. 

7. 

8. 

9. 


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