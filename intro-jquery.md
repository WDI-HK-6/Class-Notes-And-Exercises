### Morning Exercise - putting it all together - arrays, hashes, loops, functions, functional programming flow
```javascript
var customer = {
	firstName: 'Sally',
	lastName: 'Adams',
	points: 500
};

var cart = [
	{
		sku: '2314',
		name: 'Pen',
		price: 199,
		qty: 2
	},{
		sku: '542',
		name: 'Pencil',
		price: 33,
		qty: 2
	},{
		sku: '908',
		name: 'Notepad',
		price: 99,
		qty: 3
	},{
		sku: '983',
		name: 'Pirate Outfit',
		price: 2099,
		qty: 1
	},{
		sku: '453',
		name: 'Immodium',
		price: 599,
		qty: 1
	}
];

// Create a function that returns the total price (price x qty) of a single item in the cart

// Create a function that returns the total price of all items in the cart.

// Create a function that makes a orderSubmission object with customer, cart, and total price of the cart

// Create a function that takes a number in cents and converts it to a string ex. 3999 gets converted to '$39.99'

// Call the function in the step above.

// BONUS: Create a cart object like above, but one that calculates the total price of ITSELF

```


### jQuery makes it easy to:
- find elements in a HTML document
- change HTML content
- listen to what a user does and react accordingly
- animate content on the page
- talk over the network to fetch new content
- jQuery does ALL of this without requiring a full page refresh

### What can you do with jQuery?
- Show sample websites
- Each web browser has different DOM interface, that’s why we use Jquery
- Make AJAX requests to an outside server

### Basic jQuery usage
```
jQuery(<code>)
jQuery(document) <- access the DOM

$ can replace jQuery
$(<code>)
$(document) <- access the DOM
```

### DOM
- Document Object Model
- What is it? Why do we care?
http://www.w3.org/TR/WD-DOM/introduction.html

### find h1
```
jQuery('h1');
jQuery('p');

$('h1');
$('p');
```

###After selecting something, jQuery returns your results in an **array**
```
[<p>​…​</p>​, <p class=​"small">​…​</p>​, <p class=​"small">​…​</p>​]  
```

### You can then do stuff with those results with a wide variety of jQuery **methods**, many of which are both **Getters** and **Setters**.

### finding what’s inside h1 (Getting)
```
$('h1').text(); 
```

### change what’s inside h1 (Setting)
```
$('h1').text('Changed text'); 
```
### We need to wait for the DOM to finish loading before we use jQuery
```
when the DOM is finished loading, it will actually tell you that it’s ready

jQuery(document).ready(function(){
		$(“h1”).text(“changed test”);
});
```

### exercise
1. select the element in `<span>`
2. select the element in p
3. select the text value of h1
4. change the value inside span
5. write Jquery code so it only runs when the DOM is finished loading

### including jQuery into your website
Download the jQuery library from jQuery website (http://jquery.com/)
```
<script language="javascript" type="text/javascript" src="jquery-2.1.1.js"></script>
<script src="js/YourExternalJQueryScripts.js"></script>
```

### change all text in `<li>` to the same content
```
$(“li”).text(“text changed”);
```
### select IDs and classes
```
$(“.class”);
$(“#id”);
```

### where to put javascript links?
- Right before the </body> would be the most ideal!
- Why is that?

```
<!DOCTYPE html>
<html>
  <head>
  </head>
  <body>
    <script src="jquery.min.js"></script>
        <script src="application.js"></script>
  </body>
</html>
```

### descendent selector
```
<ul class=“courses”>
	<li></li>
	<li></li>
	<li></li>
	<li></li>
	<li></li>
</ul>

// all descendents
$(“#courses li”);

// direct descendents
$(“#courses > li”);

// pseudo selector. select first item in the list
$(“#courses li:first”);
$(“#courses li:last”);
$(“#courses li:odd”);
$(“#courses li:even”);
```

### traversing
We don’t want to just use descendent selector. This approach is a little bit faster in the DOM

```
$(“courses”).find(“li”);

$(“courses”) = selector
.find() = traversal

old: $(“li:last”);
new: $(“li”).last();

// Walking the DOM
$(“li”).first();
$(“li”).first().next();
// Method chaining
$(“li”).first().next().prev();

// traverse back up to parent
$(“li”).first().parent();

// traverse down to children; .children() gets the direct children. .find() gets all the children
$(“#courses”).children(“li”);

// html tags and classes
$(“h2.hello”)
```

### Appending to DOM
```
// won’t work
var course = ‘WDI is great’;
var course = (‘<p>WDI is great</p>’;

// will work
var course = $(‘<p>WDI is great</p>’);
```

```
// four options to append an item to certain location in the web  page
apple = $(‘<p>Apple</p>’);

.append(<element>)
.prepend(<element>)
.after(<element>)
.before(<element>)

.appendTo(<element>)
.insertAfter(<element>)
.prependTo(<element>)
.insertBefore(<element>)

apple.appendTo($(‘#fruit’));
```

### Removing from DOM
```
$(‘#food’).remove();
``` 

### Interactions
```
.on(<event>, <event handler>)

$(document).ready(function(){
	$(‘button’).on(‘click’, function(){
		// what happens when any button is clicked
		var apple = $(‘<p>Apple</p>’);
		$(‘.food’).append(apple);
		$(‘button’).remove();
	});
});
```

### Refactor using Traversing
```
$(document).ready(function(){
	$(‘button’).on(‘click’, function(){
		// what happens when any button is clicked
		var apple = $(‘<p>Apple</p>’);
		$(this).after(apple); //after the button
		$(this).remove();
	});
});

// will only find 0 to 1 node when it searches ancestors with proper class
$(this).closest(‘.food’).append(apple);

// .parent() will find all the ancestors
```


### Additional data attributes in HTMl and accessible by jQuery
// additional information
``` 
<li class=“food” data-price=“1.99”>

// reading data
.data(<name>)

// fetching data
.data(<name>, <value>)
```

### Event delegation
```
$(‘.food button’).on(‘click’, function(){});
$(‘.food’).on(‘click’, ‘button’, function(){});
```

### Filtering
```
// filtering with class
$(“.food”).filter(‘.edible’);

// adding removing class
.addClass();
.removeClass();
```

### More events
- keyup
- keydown

### Stop Event Propagation
Poping up the the top of the page
```
<a href=“#”></a>
```

```
function(event){
	// prevent default behaviours of the browser
	event.preventDefault();
	// do something
}
```

### updating css
```
.css(‘background-color’, ‘red’);
.show();
.hide();
```

### Animations
```
.slideup()
.slidedown()
```
