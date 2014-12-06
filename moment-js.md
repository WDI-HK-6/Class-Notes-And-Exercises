# Moment.JS
##http://momentjs.com

##Install
If possible, don't use the built-in JavaScript Date object. Its limitations are pretty severe.

http://momentjs.com/docs/#/use-it/browser/

Download **moment.js** and reference it in the head of your document.

##Usage

###Setting Dates
```javascript
// calling moment() will create a new object 
// with the current time's information
var now = moment();

// you can also put in a custom date as a string
// default is YYYY-MM-DD
var date1 = moment("1995-12-25");

// if your date is not the default format you must
// specify what number corresponds to what value
var date2 = moment("12-25-1995", "MM-DD-YYYY");

// if your date is in Unix Offset (milliseconds since Jan 1, 1970)
// just pass it in directly as a number
var date3 = moment(1318781876406);

// Unix Offset CAN be negative
var date3 = moment(-1318781876406);
// Is 1928-03-18T15:42:03+08:00

// if your date is in Unix Offset BUT is a string,
// use a lowercase 'x'
var date3 = moment('1318781876406', 'x');
```
###Getting Back an Integer

```javascript
var date1 = moment("1995-12-25");

date1.valueOf()
// 819820800000

date1.date();
// 25

date1.month();
// 11 -> NOTE this is the actual month number minus 1

date.year();
// 1995

```

###Getting Back a String

```javascript
var date1 = moment('1995-12-25');

date1.format();
// "1995-12-25T00:00:00+08:00"

date1.format('DD');
// "25"
date1.format('MM');
// "12" -> NOTE this is the actual number (not minus one)

date1.format('MMMM');
// "December"

date1.format('YYYY');
// "1995"

date1.format('YYYY-MM-DD');
// "1995-12-25"
```

###UTC Dates

UTC dates are in the form of an array and months always start from 0.
```javascript

var date5 = moment.utc([1995, 11, 25]);

// INVALID DATE due to month
var dateX = moment.utc([1995, 12, 25]); 

date5.format();
// "1995-12-25T00:00:00+00:00"

date5.format('MMMM');
// "December"

date5.date();
// 25

date5.month();
// 12

```
