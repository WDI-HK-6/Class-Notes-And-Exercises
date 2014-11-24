# JavaScript

JavaScript is a programming language that primarily does client-side functionality. Examples of front-end JS libraries and frameworks are **jQuery** and **AngularJS**, respectively.

JavaScript can also be used for the server-side. **NodeJS** is an example of a JS platform used for server-side functionality.

## Javascript Console



Chrome Console - allows you to type JavaScript code and see some kind of output the code gives you. It is a place to test and debug JS code. Like the terminal, but for JavaScript.

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