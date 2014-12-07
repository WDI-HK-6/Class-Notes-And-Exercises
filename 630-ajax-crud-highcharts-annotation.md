#AJAX and HighCharts Exercise

## Core Stuff

###Create and Read

Make a page like this: http://ga-student-page.meteor.com/playground/highcharts-annotation

- Use Moment.js to preserve your sanity: 

https://github.com/HK-WDI-November-2014/javascript-exercises/blob/master/moment-js.md

- Make sure the graph is grabbing data from an API.

- Make sure it can POST new annotations to the server (don't forget to specific your name in the hash when you post).

- Make sure those new annotations pop up on the chart (GET + api/posts/search/yourName).

## Harder Stuff

### Update and Delete

- Grab the ```_id``` of each post and use jQuery to add them in HTML ```data-``` attributes on the buttons that you press.

- You can later use jQuery to grab the ids out of the `data-` attribute on that element.

- If you have a button coded like:

```html
<button data-id="NJIH89233is928" class="edit-button"></button>
```

You can then use jQuery to grab the ID using ```this```

```javascript
$('button.edit-button').on('click', function(){
	var annotationId = $(this).data('id');
});
```

- In addition, make sure you can view all of your annotations in a list (GET). Check out Bootstrap Modals and Sidebars.

- In addition, make sure you can update and delete all of your existing annotations in the list (GET, POST, PUT, DELETE) using buttons, forms, and AJAX.