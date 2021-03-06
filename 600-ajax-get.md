
#AJAX

##Definition

**Asynchronous JavaScript**

Normally JS runs **synchronously**, meaning that it goes line by line, from the top of the document to the bottom. 
```
// Code number 1 runs here
// Code number 2 runs here
// Code number 3 runs here
```
It runs in order, which is predictable and easy to manage.

But what happens when a piece of code needs to fetch data from an external server, like Instagram?

When you are fetching data from an external server, the code needs to make a request to the server and then wait for the server to return back something. 

This takes time, and the time needed for a response from the server is unpredictable. 

- Sometimes it's fast. 
-  Sometimes it's slow. 
- Sometimes you never get a response. 
- Sometimes the response isn't even the data that you requested, but an error of some sort instead (ex. "Your request was bad and we didn't understand it.")

**How do you manage something like this when the rest of your code runs line by line?**

##Two methods of dealing with External Server Requests

###Blocking:

```javascript
//Function1 runs
//Function1 sends request to external server
//Function2 WAITS until a response gets received.
//Function2 WAITS some more
//Function2 runs (hopefully)
//Function3 finally can run
```

###Non-Blocking:

```
//Function1 runs
//Function1 sends request to external server
//Function2 runs immediately
//Function3 runs after
	//- When a response gets received, Function4 runs
```
JavaScript is **non-blocking** by nature.

##The Basics of A Request

Imagine you want someone to do an action for you. You need to specify:

- **what** you want them to do (get something, receive something, update something, delete something, etc)
- **where** you want them to do it (in their kitchen, in their living room, etc)
- **what they may need** from you to do the action
- what should happen with the **response**

**What** is determined by the verb used:
- GET: retrieve data from a server
- POST: send data to a server
- PATCH: update data on a server
- DELETE: delete data from a server

**Where** is determined by the url:
	ex. http://www.omdbapi.com/?t=matrix&y=&plot=short&r=json

For now we are only concerned with GET requests.

Example GET Request:
```javascript
$.ajax({
  type: "GET",
  url: "http://www.omdbapi.com/?t=matrix&y=&plot=short&r=json",
  dataType: "JSON",
  success: function(response){ console.log(response); }
});

$.ajax({
  type: "GET",
  url: "http://www.omdbapi.com/?t=matrix&y=&plot=short&r=json",
  dataType: "JSON",
  success: function(response){ 
    var message = "The movie title is " + response.Title + " and the plot is " + response.Plot + ".";
    console.log(message);
  }
});

$.ajax({
  type: 'GET',
  url: 'https://www.quandl.com/api/v1/datasets/FRED/GDP.json',
  dataType: 'JSON',
  success: function(response){ console.log(response) }
});

```

You can also do things like use jQuery to post things to the HTML from your response.

```html
  <div class="container">
    <div class="row">
      <div class="movie-search col-xs-12">
        <input name="movie-title" type="text" placeholder="Enter Movie Title">
      </div>
      <h1 class="item-price">HERE</h1>
    </div>
    <article>
      <div class="row">
        <h1 class="movie-title col-sm-6">
        </h1>
      </div>
      <div class="row">
        <p class="movie-rating col-xs-12">
        </p>
        <p class="movie-actors col-xs-12">
        </p>
        <p class="movie-plot col-xs-12">
        </p>
      </div>
    </article>
  </div>
```

```javascript
$('input[name="movie-title"]').keyup(function(){

  var query = $('input[name="movie-title"]').val();

  $.ajax({
    type: "GET",
    url: "http://www.omdbapi.com/?t=" + query + "&y=&plot=short&r=json",
    dataType: "JSON",
    success: function(response){ 
      $('.movie-title').text(response.Title + ' (' + response.Released + ')');
      $('.movie-actors').text(response.Actors);
      $('.movie-plot').text(response.Plot);
      $('.movie-rating').text("IMDB Rating: " + response.imdbRating);
    }
  });

});
```

**Exercise** - OMDB API and Quandl API

