# Logic

##Start with Data Sources

***Quandl and GA-RESTful-API

1. Grabbing Data from Sources - ```createChartAndAnnotationsTable()```
	- use Ajax to GET date from Quandl
		- success:
			- save Quandl data into a variable
				- use Ajax to GET ***my*** annotations from GA-API
					- success:
						- save annotations into a variable
						- now we have both Quandl data and my annotations in variables
					  - create the entire chart
					  - create the annotations table
		          - embed the ```_id``` of each annotation into the annotations table

##Once I have data, I can do stuff.

2. Create - ```submitAnnotation()```
	- get form contents
	- modify form contents 
		- add dateCreated
		- add my user name
		- convert dates to Unix Offset
	- use Ajax to send form contents to GA-API
		- success
			- ```createChartAndAnnotationsTable()```

3. Read
	- GET requests for both Quandl and GA-API
  - ```createChartAndAnnotationsTable()```

4. Update - ```updateAnnotation()```
	- press button, grab ```_id``` from '``data-``' attribute
	- find matching ```_id``` in annotations variable
	- create and pre-fill update form using matching annotation
	- submit
	- get form contents
	- modify form contents 
		- add dateCreated
		- add my user name
		- convert dates to Unix Offset
	- use Ajax to PUT form contents to GA-API
		- success
			- ```createChartAndAnnotationsTable()```

5. Delete - ```deleteAnnotation```
	- press button, grab ```_id``` from '``data-'`` attribute
	- use Ajax to send DELETE request using the ```_i```
		- success
			- ```createChartAndAnnotationsTable()```