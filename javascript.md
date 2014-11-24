# JavaScript

JavaScript is a programming language that primarily does client-side functionality. Examples of front-end JS libraries and frameworks are **jQuery** and **AngularJS**, respectively.

JavaScript can also be used for the server-side. **NodeJS** is an example of a JS platform used for server-side functionality. Server-side functionality includes things such as serving files to clients over the web, connecting to real-time data feeds, talking with databases, and establishing data security.

## Javascript Console

Like the terminal, but for JavaScript.

**[JSFiddle](http://jsfiddle.net/)** - allows you to run JavaScript code and also share your code snippets with others.

**Chrome Console** - also a place to test and debug JS code. 

JS statements always end in a semicolon ( ; )

console.log();

Running this statement will output (log) something to your JS console.

console.log("Hello!");
console.log(4+4);

Think of variables as a storage box for a particular value. If you have a piece of data, create a variable to store that data in.

Whenever you set something using "=" you are DEFINING it.

var price;
console.log(price); 

What will be the output?

Integer: use this if you want to eventually do mathematical operations on this value

var price = 25000000; 

String: ALWAYS have " " or ' ' wrapped around them.

var make = "Honda";
var model = "Fit";

var numberOfDoors = ???  

Would this be integer or string?

Boolean:

var hasAirbags = true;
var hasOwner = false;

Will this work?

var hasAirbags = "true";
var hasOwner = "false";

Truthy and Falsey

Some things JS considers False and other things JS considers True.

Falsey
undefined, null, 0, +0, -0, NaN, ""

True
Something that has a set value.

Arrays
A way to store multiple pieces of data. Preserves order.