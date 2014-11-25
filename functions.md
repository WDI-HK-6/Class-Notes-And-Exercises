# Functions

## Setting up Functions

If you think about it, every action in your life can be broken down just a few things:

1. a procedure or formula for doing something
2. the inputs required for this procedure to work
3. the output (result) of the procedure

**Exercise - think about the formula for calculating something - pick one of the ideas and write it into code**

### Inside-Out Way of Thinking

- Think of the formula.

```
var area = length * width;
```

We've already got the main body of the function.

- Let's wrap this inside javascript function syntax;

```javascript
function() {
	var area = length * width;
};
```

- We put the inputs inside of the **( )** after the function keyword.

```javascript
function(length, width) {	
	var area = length * width;
};
```

- The purpose of making functions is to re-use them. So it needs a name for us to refer to it again in the future.

```javascript
var calcRectangleArea = function(length, width) {
	var area = length * width;
};
```

- The function needs to return an output, so we add a `return` to the end:

```javascript
var calcRectangleArea = function(length, width) {
	var area = length * width;
	return area;
};
```

### Outside-In Way of Thinking

- Think of a name for your function

```javascript
var calcRectangleVolume;
```

- Start defining your function

```javascript
var calcRectangleArea = function(){};
```

- Gather together the inputs needed and stuff them in.

```javascript
var calcRectangleArea = function(length, width, height){
	
};
```

- Write the body

```javascript
var calcRectangleArea = function(length, width, height){
	var volume = length * width * height;
};
```

- Make sure to return the output

```javascript
var calcRectangleArea = function(length, width, height){
	var volume = length * width * height;
	return volume;
};
```

**
Exercise - create at least 5 of your own functions:
- one that takes no inputs
- one that takes multiple inputs
- one that takes an array as an input
- one that takes an object as an input
- one that returns a single value
- one that returns another object or array
**

