# Functions

## Setting up Functions

If you think about it, every action in your life can be broken down just a few things:

1. a **procedure or formula** for doing something
2. the **inputs** required for this procedure to work
3. the **output** (result) of the procedure

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

- We put the exact inputs we used inside of the **( )** after the function keyword.

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
var calcRectangleVolume = function(){};
```

- Gather together the inputs needed and stuff them in.

```javascript
var calcRectangleVolume = function(length, width, height){
	
};
```

- Write the body using the same inputs

```javascript
var calcRectangleVolume = function(length, width, height){
	var volume = length * width * height;
};
```

- Make sure to return the output

```javascript
var calcRectangleVolume = function(length, width, height){
	var volume = length * width * height;
	return volume;
};
```

##Two different ways of defining functions

1. Best way, only gets loaded into memory when it is called.

```javascript
var calcCircumference = function(radius) {

	var PI = 3.14159265359;
	var circumference = radius * 2 * PI
	return circumference;

};

calcCircumference(6); // gets loaded into memory at this time
```

2. Not as good, gets loaded into memory from the very beginning.

```javascript
function calcCircumference(radius) {

	var PI = 3.14159265359;
	var circumference = radius * 2 * PI
	return circumference;

};

// gets loaded into memory even when it hasn't been run yet

calcCircumference(6);
```

##Scoping

```JavaScript

var person1 = 'Annie';
var person2;
var globalPerson3;

console.log('person1 is ' + person1);

var myFunction = function() {
	var person2 = 'Brad';
	globalPerson3 = 'GOD';
	console.log('person1 inside myFunction is ' + person1);
}

console.log("-----------Before running myFunction--------------");

console.log('person2 was defined inside myFunction but is called outside of it: ' + person2);
console.log('globalPerson3 was defined inside myFunction but is called outside of it: ' + globalPerson3);

console.log("-----------After running myFunction--------------");
myFunction();

console.log('person2 was defined inside myFunction but is called outside of it: ' + person2);
console.log('globalPerson3 was defined inside myFunction but is called outside of it: ' + globalPerson3);

```


##Best Practices

**Create nullipotent functions.**
**Be non-destructive of your inputs.** 
**Always return a new object or value.**

http://en.wiktionary.org/wiki/nullipotent - Describing an action which has no side effect. They return useful data, but do not change the data that was used as input.

```javascript
//bad-------------------------

var sam = {
	firstName: 'Sam',
	age: 25
};

var destructiveFunction = function(person) {
	person.age = 88;
};

destructiveFunction(sam);

// sam is now { firstName: 'Sam', age: 88 } in the rest of the code.
// What if an untouched version of sam was a dependency in another part of your code?
// Can lead to weird cascading failures everwhere.

//good------------------------

var sam = {
	firstName: 'Sam',
	age: 25
};

var goodFunction = function(person) {
	var newPerson = person;
	newPerson.age = 88;
	return newPerson;
};

goodFunction(sam);

// sam remains the same and does not get changed.
// The original sam variable is preserved for other functions that require sam.

```

**Do not utilize inputs that have not already been defined as one of your arguments.**

```javascript

//bad 

var sam = {
	firstName: 'Sam',
	age: 25
};

var sarah = {
	firstName: 'Sarah',
	age: 29
}

var differenceInAge = function(person) {
	var difference = sarah.age - person.age;
	return difference;
};

alert( differenceInAge(sam) );

//good

var sam = {
	firstName: 'Sam',
	age: 25
};

var sarah = {
	firstName: 'Sarah',
	age: 29
}

var differenceInAge = function(person1, person2) {
	var difference = person1.age - person2.age;
	return difference;
};

alert( differenceInAge(sarah, sam) );

```

**Exercise - create at least 5 of your own functions:**
- one that takes no inputs
- one that takes multiple inputs
- one that takes an array as an input
- one that takes an object as an input
- one that returns a single value
- one that returns another object or array

##jQuery

**jQuery** is a JS library that was written to connect the HTML to your JS and vice versa. It has lots of functions for selecting a part of the DOM then grabbing data from the DOM and manipulating the DOM.

**Pattern:**

```javascript
// Wait for the DOM to be completely ready.
// The $ is short for jQuery.
// Select parts of the DOM and do something to it.
// (Select - Do Something) pattern

$('selector').someJqueryFunction();
$('p').someJqueryFunction();
$('.class-name').someJqueryFunction();
$('#id-of-element').someJqueryFunction();
$('h1 #id-of-element').someJqueryFunction();
$('article .class-name').someJqueryFunction();
```

**Common jQuery functions:**

- Listen for an event from the user that will set off a chain of functions that you write:

http://api.jquery.com/category/events/

- Set and Get data from the HTML

http://api.jquery.com/text/
http://api.jquery.com/data/
http://api.jquery.com/html/
http://api.jquery.com/val/

**Exercise**

Practice going to websites and using jQuery to select things and get and set their values.

##Functional Flow

1. Funnel inputs into functions.
2. Run function.
3. Have function return something new.
4. Save returned value into a variable.
5. Use this new variable as the input into another function.
6. etc, etc, etc

##Planning

You sold an item and need to calculate the total price of the item + shipping + taxes on your website.

Draw out what you need as inputs, as functions, and as outputs.

##Break functions into small, manageable bits for **modularity, seperation of concerns, and easy debugging**

```javascript

	// Setting variables and inputs --------------------------------------------
	// Assume you got these values from user input or a form submission.


	var item = {
		name: 'Anvil',
		weight: {
			unit: 'kg',
			value: 500
		},
		price: {
			unit: 'hkd',
			value: 100000
		}
	};

	var destinationAddress = '33 Des Voeux Road, Central, Hong Kong';

	var originAddress = '1234 Main St., Springfield, CA, 94043, USA';

	var shippingRateTable = {
		//Hash that defines all the shipping rates.
	};

	var taxRateTable = {
		//Hash that defines all the tax rates.
	};

	// Defining Small Functions and their Outputs -------------------------------

	var returnShippingCost = function(origin, destination, weight, shippingRates) {
		var shippingCost;
		// Do some formula that calculates shipping cost and stores it inside shippingCost
		return shippingCost;
	};

	var returnTaxAmount = function(destination, item, taxRates) {
		var taxAmount;
		// Do some formula that calculates tax amount and stores it inside taxAmount;
		return taxAmount;
	};

	var returnTotalPrice = (itemPrice, shippingPrice, taxAmount) {
		var totalPrice = itemPrice + shippingPrice + taxAmount;
		return totalPrice;
	};

	// Running Small Functions and Getting the Final Output -----------------------

	var itemPrice = item.price;
	var shippingCost = returnShippingCost(originAddress, destinationAddress, item.weight, shippingRateTable);
	var taxCost = returnTaxAmount(destinationAddress, item, taxRateTable);

	var totalPrice = returnTotalPrice(itemPrice, shippingCost, taxCost);

	// take totalPrice and send it using jQuery to be displayed to the client

	$('#final-price-box').text(totalPrice);

```

**Exercise:**

Do the shopping cart exercise in Playground.
