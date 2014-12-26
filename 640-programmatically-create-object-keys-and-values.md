#Programmatically Create Object Keys and Values in JavaScript

Object values can be variables, but not object keys.

Using variables in place of values works:
```javascript
var myName = 'Bob';
var myAge = 45;

var person1 = {
	name: myName,
	age: myAge
};

// console.log(person1) would give you:
// {
//	 name: 'Bob',
//	 age: 45
// }
```

This does not work as intended when you try to use variables in place of key names:
```javascript

var key1 = 'name';
var key2 = 'age';

var person2 = {
	key1: 'Bob',
	key2: 45
};

// console.log(person2) would give you:
// {
//	 key1: 'Bob',
//	 key2: 45
// }
```

This DOES work:
```javascript

var key1 = 'name';
var key2 = 'age';

var person3 = {};
person3[key1] = 'Bob';
person3[key2] = 45;

// console.log(person3) would give you:
// {
//	 name: 'Bob',
//	 age: 45
// }
```
How about writing a function to programmatically create an object?

```javascript

var returnObject = function(key, value){
	var object = {};
	object[key] = value;
	return object;
};

returnObject('age', 45);

```
Something more complex:

```javascript
// Say that this is a statement that you want to run, but you want 
// 'categoryVoted.category1' and 'userId' to be derived from variables.

update({_id: 'id1'}, {$addToSet: {'categoryVoted.category1': 'userId'}});

// This creates everything, including $addToSet
var returnAddToSetObject = function(category, userId){
  var key = 'categoryVoted.' + category;
  var object = {};
  object.$addToSet = {};
  object.$addToSet[key] = userId;
  return object;
};

// This is how you run it
update({_id: 'id'}, returnAddToSetObject('category3', 'HIhews8fy7ufw'));

// This creates only the object that is the *value* of the $addToSet *key*
var returnCategoryVotedObject = function(category, userId){
  var key = 'categoryVoted.' + category;
  var object = {};
  object[key] = userId;
  return object;
};

// This is how you run it
update({_id: 'id1'}, {$addToSet: returnAddToSetObject('category3', 'HIhews8fy7ufw')});
```