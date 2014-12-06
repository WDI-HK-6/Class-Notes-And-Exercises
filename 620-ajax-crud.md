#AJAX for CRUD

![enter image description here](http://i.stack.imgur.com/RyM1b.png)

##Create - POST

Creating new information in the database.

- Create a form that gathers user input
- send a POST request to /api/posts with the data from the form

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

- Send a GET request that returns data to be displayed on the page
- Create a page or section that displays the data from the response

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

- Create a method for a user to edit a particular peice of data
- Create a form that gathers user input for editing that particular data
- send a POST request to /api/posts/:id with the data from the form

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