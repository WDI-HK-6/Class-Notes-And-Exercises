# JavaScript

JavaScript is a programming language that primarily does client-side functionality. Examples of front-end JS libraries and frameworks are **jQuery** and **AngularJS**, respectively.

JavaScript can also be used for the server-side. **NodeJS** is an example of a JS platform used for server-side functionality. Server-side functionality includes things such as serving files to clients over the web, connecting to real-time data feeds, talking with databases, and establishing data security.

## Javascript Console

Like the terminal, but for JavaScript.

**[JSFiddle](http://jsfiddle.net/)** - allows you to run JavaScript code and also share your code snippets with others.

**Chrome Console** - also a place to test and debug JS code. 

JS statements always end in a semicolon ( ; )

`ex. var firstName = 'Simon';

`console.log();`

Running this statement will output (log) something to your JS console.

`console.log('Hello!');`
`console.log(4+4);`

**Exercise Time!**

## Variables

Think of variables as a storage box for a particular value. If you have a piece of data, create a variable to store that data in.

Whenever you set something using "=" you are **DEFINING** it. 

Whenever you put "//" in JS code you are adding a **comment**.

```
var name = 'Tom Smith';
console.log(name); 
// What will be the output?

var price;
console.log(price); 
// What will be the output?
```

**Exercise Time!**

## Data Types

**Number**: use this if you want to eventually do mathematical operations or comparisons on this value

var price = 25000000; 

**String**: ALWAYS have ' ' wrapped around them. " " works as well but multiple style guides suggest using ' ' instead.

```
var firstName = 'Tom';
var lastName = 'Smith';
var phoneNumber = ???;
var hkId = ???;
var sku = ???;
```

Should these be numbers or strings?

**Boolean**: either true or false (no quotes)

var hasMoney = false;
var hasCheeseburger = true;

Will this work?

var hasHair = "true";
var hasGirlfriend = "false";

Truthy and Falsey

Some things JS considers False and other things JS considers True.

Falsey
undefined, null, +0, -0, NaN, ''

**Exercise Time! - create variables using the proper syntax for numbers, strings, and booleans**

## Storing Multiple Pieces of Data in one Variable

### Arrays

A way to store multiple pieces of data and preserves the order in which they are stored. Can also quickly determine how many items there are in the array.

**Arrays are good for storing multiple values of the same kind.**

Arrays always use **[ ]**

```
var classmates1 = ['Cassie', 'Clement', 'Dale', 'Dennis', 'Dow', 'Vivienne'];

var classmates2 = ['Cassie', 'Clement', 'Dale', 'Dennis', 'Vivienne', 'Dow'];

// the two arrays above are NOT the same. Why?

var takeoutOrder = ['hamburger', 'fries', 'soda'];

var takeoutOrder = [
	'hamburger', 
	'fries', 
	'soda'
];

// the two arrays above ARE the same.

takeoutOrder.length;  		// returns 3
classmates1.length; 			// returns 6
```

**Exercise Time! - create arrays and think about what types of data are good for arrays**

### Objects

Think of objects as **things**. A car is an object. A person is an object. Objects have **properties**, which we call **keys**. The values of those properties / keys are called **values**.

**{key: value}** pairs

A key can be a single word or multiple words separated by spaces, but if they're multiple words with spaces they must be in ' ' .

Objects always use **{ }**

Objects do NOT preserve any order.

Objects are often also called **"hashes"** (not the same as the # symbol).

**Objects are used for storing single/multiple different properties of a thing or a class of thing.**
 
```
var tom = {
	firstName: 'Tom',
	lastName: 'Smith',
	age: 25,
	isMarried: true,
	'nick name': 'Boo'
};

// ...is the same as...

var tom = {
	'nick name': 'Boo',
	isMarried: true,
	lastName: 'Smith',
	firstName: 'Tom',
	age: 25
};

// ...is the same as...

var tom = {firstName: 'Tom', 'nick name': 'Boo', lastName: 'Smith', isMarried: true, age: 25};

// also good for a CLASS of `thing`

var motorcycle = {
	wheels: 2,
	hasEngine: true
};

var bicycle = {
	wheels: 2,
	hasEngine: false
};

```
**Exercise Time! - create objects and think about what types of data are good for objects - must have perfect indentation and code style**

## Accessing Values in arrays and objects

### Arrays

You grab array values via their index. Indexes always start at 0 for the first item in the array.

```
var classmates = ['Cassie', 'Clement', 'Dale', 'Dennis', 'Dow', 'Vivienne'];

classmates[1]; // will be the string 'Clement'
```
### Objects

You grab object values via the key that corresponds to that value.

```
var person = {
	firstName: 'Tom',
	lastName: 'Smith',
	age: 25,
	isMarried: true,
	'nick name': 'Boo'
};
```
There are two ways to reference a key:

**Dot Notation:**

```
person.lastName;     // will be the string 'Smith'
person.age;          // will be the number 25
person.nick name     // does not work
person.'nick name'   // does not work
```

**(Square) Bracket Notation**

```
person.['lastName'];		// will be the string 'Smith'
person.['age'];					// will be the number 25
person.['nick name'];   // will be the string 'Boo'
```

**Exercise Time! - create objects and arrays and access their values**

## Mixing Objects into Arrays and Vice Versa

```
var subaruImpreza = {
	wheels: 4,
	passengers: [
		{
			firstName: 'Tom',
			lastName: 'Smith',
			age: 20
		},{
			firstName: 'Joe',
			lastName: 'Smith',
			age: 20
		},{
			firstName: 'Greg',
			lastName: 'Smith',
			age: 55
		}
	],
	models: [
		{
			name: '2.0i',
			'engine choices': [
				'180hp'
			]
		},{
			name: '2.0i Premium',
			'engine choices': [
				'180hp'
			]
		},{
			name: '2.0i Limited',
			'engine choices': [
				'180hp',
				'250hp'
			]
		},{
			name: 'WRX',
			'engine choices': [
				'180hp',
				'250hp',
				'400hp'
			]
		}
	]
};

var shoppingCart = [
	{
		itemName: 'celery',
		price: 5,
		qty: 3,
		isDiscounted: false
	},{
		itemName: 'lettuce',
		price: 5,
		qty: 2,
		isDiscounted: false
	},{
		itemName: 'bread',
		price: 8,
		qty: 1,
		isDiscounted: false
	},{
		itemName: 'beef',
		price: 30,
		qty: 4,
		isDiscounted: true
	}
];

```
**Exercise Time! - access values in the objects and arrays above.**

**Exercise Time! - look around and practice creating objects and arrays with nested objects and arrays - must have perfect indentation and code style**