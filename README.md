# happy_iqy

Excel Web Query - What in the world is that? If you are like the other 99.9% of MS Excel users, you probably have never heard of microsoft excel web queries (note: statistic made up).

<p align="center">
  <img src="https://raw.githubusercontent.com/alexfrancow/happy_iqy/master/images/2018-09-21_122613.png"/>
</p>

Excel web queries are powerful! Web queries are basically like having a web browser built into Excel that attempts to format the content, putting individual pieces of data into separate cells. You can then use Excel formulas (like =A1/B2) to work directly with the data you've downloaded. And you don't have to know anything about perl, cgi, php, javascript, etc.

The real key to creating a dynamic excel web query is to create your own ".iqy" file. In it's basic form, the ".iqy" file is simply a TEXT file with three main lines:

```iqy
WEB
1
https://www.thedomain.com/script.pl?paramname=value&param2=value2
```

You can create the file using a simple text editor! 

To make the query dynamic, replace the value of each parameter in the web query file (queryname.iqy) with:

```iqy
["paramname","Enter the value for paramname:"]
```

Want to see how this would apply to a Google search? The form that I used above consists of HTML code that looks like this:

```html
<form action="https://www.google.com/search">
<input type="text" name="q" value="excel web query">
<input type="submit" value="Search Google">
</form>
```

Notice that "q" is the name of the parameter, and the action tells you what the URL should be. The dynamic web query file for a simple google search would look like this:

```iqy
WEB
1
https://www.google.com/search?q=["keyword","Enter the Search Term:"]
```

## Configuration

You must create an '.iqy' file and add the following lines:

```iqy
WEB
1
<URL for '.dat' file>
```

You can choose any example of this repository, in the url for the .dat file add the raw of any example.

### Calc example

```iqy
WEB
1
https://raw.githubusercontent.com/alexfrancow/happy_iqy/master/examples/calc-excel2016.dat
```
