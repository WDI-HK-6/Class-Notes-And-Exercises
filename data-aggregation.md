#Data Aggregation

Use the following link to grab the following weekly gasoline data;

https://www.quandl.com/api/v1/datasets/BTS_MM/RETAILGAS.json?trim_start=1995-01-02&trim_end=2012-10-15&auth_token=E6kNzExHjay2DNP8pKvB

You have a client who wants to be able to easily switch between the following views:

- Use HighCharts to make a chart of weekly gasoline data.

- Use HighCharts to make a chart of monthly gasoline data (averaging the weeklies).

- Use HighCharts to make a chart of quarterly gasoline data.

- Use HighCharts to make a chart of yearly gasoline data.

Feel free to display all data on one chart, so this would mean your series array would have four different hashes.

This will help you a lot:

http://www.w3schools.com/jsref/jsref_obj_date.asp

If you're feeling intrepid, try and use Moment.JS:

http://momentjs.com/
