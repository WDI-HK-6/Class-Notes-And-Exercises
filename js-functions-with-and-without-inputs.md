#Functions that can do different things when there are no inputs and when there are inputs

Say that you have:

```html
<h1 class="title">MY TITLE</h1>
```
```javascript
$('h1.title').text(); // returns 'MY TITLE'
$('h1.title').text("My New Title"); //replaces 'MY TITLE' in the html with 'My New Title'
```
```.text()``` from jQuery is able to act as a **getter** when the user **doesn't** give it any inputs.

```.text()``` is able to act as a **setter** when the user **does** give it inputs.

This is how:

```javascript
var text = function(input){
	if(!input){
		// do getting function
		// return text
	} else {
		// do setting function
		// change HTML
	};
};

// let's test it using this definition:

var text = function(input){
	if(input === ""){
		console.log("SETTING VALUES FROM HTML");
	} else if (!input) {
		console.log("GETTING VALUES FROM HTML");
	} else {
		console.log("SETTING VALUES ON HTML");
	};
};
```

The ```(!input)``` evaluates to ```true``` if there is no user input, so it runs the getting function.
The ```(!input)``` evaluates to ```false``` if there is no user input, so it runs the setting function.