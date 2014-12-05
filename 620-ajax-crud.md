#AJAX for CRUD

![enter image description here](http://i.stack.imgur.com/RyM1b.png)

##Create - POST

Creating new information in the database.

- a form that a user fills out that submits to the server and the database

OR

- the server creates data in its database from some other data source, such as an AJAX request

```javascript
$.ajax({
	type: 'POST',
    url: 'http://ga-wdi-api.meteor.com/api/posts/',
	data: {
		user: 'yourName',
		title: 'My Annotation Title',
		text: 'Something describing my annotation',
		x: Date.parse("2011-02-10"),
		dateCreated: new Date()
	},
	dataType: 'json',
	success: function(response){
		console.log(response);
	}
});
```

##Read - GET

Retrieving and displaying existing information from the database.

- a response from the server with the information requested

- a page that displays information from the database

```javascript

//Gets all posts.

$.ajax({
	type: 'GET',
    url: 'http://ga-wdi-api.meteor.com/api/posts/',
	dataType: 'json',
	success: function(response){
		console.log(response);
	}
});

// Gets one post.

$.ajax({
	type: 'GET',
    url: 'http://ga-wdi-api.meteor.com/api/posts/epfL7Qg6NeH5MBK56',
	dataType: 'json',
	success: function(response){
		console.log(response);
	}
});

// Searches for your posts.

$.ajax({
	type: 'GET',
    url: 'http://ga-wdi-api.meteor.com/api/posts/search/myName',
	dataType: 'json',
	success: function(response){
		console.log(response);
	}
});
```

##Update - PUT

Update existing information in the database.

- find the information that you want to update
- a form that a user fills out that submits to the server and modifies the existing information

OR

- the server updates data in its database from some other data source, such as an AJAX request

```javascript
$.ajax({
	type: 'PUT',
    url: 'http://ga-wdi-api.meteor.com/api/posts/epfL7Qg6NeH5MBK56',
	data: {
		user: 'yourName',
		title: 'My Modified Title',
		text: 'A new description for my annotation',
		dateModified: new Date()
	},
	dataType: 'json',
	success: function(response){
		console.log(response);
	}
});
```
##Delete - DELETE

Delete existing information in the database.

- find the information that you want to delete

- a button that a user clicks that tells the server to delete existing information

- there should be a confirmation message before deletion

```javascript
$.ajax({
	type: 'DELETE',
    url: 'http://ga-wdi-api.meteor.com/api/posts/epfL7Qg6NeH5MBK56',
	success: function(response){
		console.log(response);
	}
});
```