#How do JS functions work?

##Basics
Say that we have this:

```javascript

var area = function(num1, num2){
	var result = num1 * num2;
	return result;
};

```
Have you ever wondered why this works?

```javascript
area(2,5); // returns 10

```

Copy and Paste this into Console:

```javascript
(function(num1, num2){
	var result = num1 * num2;
	return result;
}(2,5))
```

It returns 10.

JavaScript is an extremely, extremely literal language when it comes to substitution.

```javascript
var area = function(num1, num2){
	var result = num1 * num2;
	return result;
};
```
is "like" saying
```javascript
var area = "function(num1, num2){var result = num1 * num2;return result;}";
```
So
```javascript
area(2,5);
```
is "like"
```javascript
"function(num1, num2){var result = num1 * num2;return result;}"(2,5);
```
So 
```javascript
area(2,5)
```
Is **literally**, through **substitution**, running

```javascript
(function(num1, num2){
	var result = num1 * num2;
	return result;
}(2,5))
```

##**Challenge**
```javascript
var runUserFunction = function(userFunction){
	var message = "HELLO!";
	userFunction(message);
};

var alertMe = function(input){
	alert(input);
};
```
Why does this work?
```javascript
runUserFunction(function(input){
	alert(input);
});
```
And this?
```javascript
runUserFunction(alertMe);
```