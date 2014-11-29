#Cheatsheet
##JavaScript
###Algebra and Math
JS is heavily influenced by basic math:
```
//The following is algebra, not JS.

//Variables----------------

a = 5
// brings back 5
a

b = 9
//brings back 9
b

//Functions----------------

//Squaring a number:
f(x) = x * x

//What do these return?
f(3)
f(5)
f(50)

//Circumference of a circle:
f(x) = 3.1415 * 2 * x

//What do these return?
f(4)
f(10)
```
All JavaScript does is:
- replace "f" with "function"
- store the function into a variable so you can re-use it later
- remove the "="
- wrap the formula around "{ }" ex. { //formula here }
- adds a "return" so that the answer gets outputted to the outside world
- end the line with a ";"

```javascript
//squaring
var square = function(x){ return x*x; };
//OR
var square = function(x) {
	return x*x;
};

//circumference of circle
var calcCircumerence = function(x) {
  return (3.1416 * 2 * x);
};
```
It would be good to give our inputs descriptive names.
```javascript
//squaring
var square = function(num){ return num * num; };
//OR
var square = function(num) {
	return num * num;
};

//circumference of circle
var calcCircumerence = function(radius) {
  return (3.1416 * 2 * radius);
};
```
###Exercises
Make a **math** function for calculating the volume of a sphere.
Make a **JS** function for doing the same thing.

Make a **math** function for calculating the area of a rectangle.
Make a **JS** function for doing the same thing.

Make a **math** function for calculating compound interest P = C (1 + r/n)^nt
Make a **JS** function for doing the same thing.

```javascript
// use Math.pow(base, exponent);
// Math.pow(5,2); // equals 25
```

Make a **math** function for calculating ROI (Return on Investment)
Make a **JS** function for doing the same thing.