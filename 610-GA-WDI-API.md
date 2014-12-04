#GA WDI - RESTful API DOCUMENTATION

##REST

REpresentational State Transfer

A simple **Verb-Path-(Data)** request to a server can be used to manage assets and responses on a properly-configured server.

![enter image description here](http://i.stack.imgur.com/RyM1b.png)

##POST

Send a POST request to http://ga-wdi-api.meteor.com/api/posts

Data:
```javascript
{
	user: 'yourName',
	title: 'My Annotation Title',
	text: 'Something describing my annotation',
	x: Date.parse("2011-02-10"),
	dateCreated: new Date()
}
```
Result: 

A unique ID for your new Post if successful.
```javascript
epfL7Qg6NeH5MBK56
```

##SEARCHING FOR YOUR POSTS

Send a GET request to http://ga-wdi-api.meteor.com/api/posts/search/yourName

Result: 

An array of all your posts.
```javascript
[Object, Object, Object, Object, Object, Object]
```

##GETTING A SINGLE POST

Send a GET request to http://ga-wdi-api.meteor.com/api/posts/:_id

```javascript
http://ga-wdi-api.meteor.com/api/posts/epfL7Qg6NeH5MBK56
```

##UPDATING A SINGLE POST
Send a PUT request to http://ga-wdi-api.meteor.com/api/posts/:_id

```javascript
http://ga-wdi-api.meteor.com/api/posts/epfL7Qg6NeH5MBK56
```

##DELETING A SINGLE POST
Send a DELETE request to http://ga-wdi-api.meteor.com/api/posts/:_id

```javascript
http://ga-wdi-api.meteor.com/api/posts/epfL7Qg6NeH5MBK56
```

##GET

Send a GET request to http://ga-wdi-api.meteor.com/api/posts

Result: 

An array of all posts.

```javascript
[Object, Object, Object, Object, Object, Object]
```