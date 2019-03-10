# Web Scraping with Python and BeautifulSoup


In this project, I discuss web scraping technique using BeautifulSoup, which is the Python library for parsing HTML and XML documents. 


## Table of contents:-


The contents of this project are divided into various sections which are as follows:-


1.	Introduction to web scraping


2.	Accessing a web page


3.	Introduction to HTML


4.	Class and id properties


5.	Introduction to BeautifulSoup


6.	Import Python libraries


7.	Installing BeautifulSoup


8.	Import installed libraries


9.	Access HTML content from a webpage


10.	Parse HTML content of the webpage


11.	Get the title of webpage


12.	View the data in pretty format


13.	BeautifulSoup functions – find() and find_all()


14.	BeautifulSoup objects


15.	Access children property of object


16.	Access html tags within a webpage


17.	Print the tables


18.	Print the table rows


19.	Print the table headers


20.	Print the table cells


=========================================================================================


## 1. Introduction to Web Scraping


**Web scraping** is a technique used to extract large amounts of data from websites. **Web scraping** is also known as **web harvesting**, **web data extraction** or **screen scraping**. The data is extracted from the websites and saved to a local file in the computer. This is most commonly done by writing an automated program. The program queries a web server, requests data (in the form of html and other files) and then parses that data to extract the required information. Web scraping encompasses a wide variety of programming techniques and technologies. The examples include data analysis, natural language parsing and information security. 


Most of the websites can only be viewed using a web browser. They do not offer the functionality to save a copy of this data for personal use. The only option then is to manually copy and paste the data. It is a very tedious job which can take many hours to complete. Web Scraping is the technique of automating this process. Web scraping a web page involves fetching it and extracting from it. Fetching is the downloading of a page. Once fetched, then extraction can take place.










## 2. Accessing a web page

A two way process takes place, when we try to access a web page. At first, our web browser makes a request to a web server.
This request is called a `GET` request, since we try to get files from the server. Then the server sends back files that tell our browser how to render the page for us. The files fall into few main categories as follows:-


- **HTML** - contains the main content of the page.

- **CSS** - add styles to make the page look nicer.

- **JS** - Javascript files add interactively to web pages.

- **Images** - image formats, such as JPG and PNG allow web pages to show pictures.


The browser receives all the files. It renders the page and displays it to us. When we perform web scraping, we are mainly interested in the main content of the web page, which is html.





## 3. Introduction to HTML

HTML stands for **Hyper Text Markup Language**. It is the language to create web pages. It is a markup language that tells a browser how to layout content. 


HTML consists of elements called **tags**. The most basic tag is the `<html>` tag. This tag tells the web browser that everything inside of it is HTML. In HTML, tags are nested and we can go inside another tags.

There are two other tags inside an html tag. The **head tag** and the **body tag**. The main content of the web page goes into the body tag. The head tag contains data about the title of the page and other information.

Tags have commonly used names that depend on their position in relation to other tags:

- **parent tag** — a parent tag is a tag which contains another tag inside. 

- **child tag** — a child is a tag inside another tag. 

- **sibling tag** — a sibling is a tag that is nested inside the same parent as another tag.


The examples of common html tags are as follows:-


- **a tags** - a tags are links. They tell the browser to render a link to another web page.


- **p tags** - p tag defines a paragraph and any text inside the tag is shown as a separate paragraph.


- **href** - href property of the tag determines where the link goes.

- **div** — indicates a division, or area of the page.


- **b** — bolds any text inside.


- **i** — italicizes any text inside.


- **table** — creates a table.



- **form** — creates an input form.



## 4. Class and id properties


Class and id are special properties that give HTML elements names. They make them easier to interact with while scraping. One element can have multiple classes, and a class can be shared between elements. 

Each element can only have one id, and an id can only be used once on a page. 

Classes and ids are optional and not all elements will have them.


## 5. Introduction to BeautifulSoup

**BeautifulSoup** is a Python library for parsing HTML and XML documents. It was released in 2004.  It contains simple commands that could be used to parse contents from the HTML documents. It creates a parsed tree for parsed pages that can be used to extract data from HTML documents. It is useful for web scraping.
BeautifulSoup provides few simple methods and Python idioms for navigating, searching and modifying a parsed tree. It provides a toolkit for dissecting a document and extracting the information. 
Today, it is considered the most sophisticated and advanced library for web scraping. It is also one of the most common and popular approaches for web scraping.
BeautifulSoup is available for Python 2.7 and Python 3. In this project, I will explore BeautifulSoup.




## 6. Import Python libraries


I need the default Python libraries - NumPy and Pandas for data manipulation and cleaning purposes. Also, I need the Matplotlib and Seaborn libraries for data visualization. So, I will import the default Python libraries as follows:-

`import numpy as np`
`import pandas as pd`
`import matplotlib.pyplot as plt`
`import seaborn as sns`
`%matplotlib inline`




## 7. Installing BeautifulSoup

BeautifulSoup is not a default Python library. So, we need to install it before using it. Also, we need the requests http library for this project.

The BeautifulSoup library's name is beautifulsoup4 which stands for Beautiful Soup, version 4.

I have Python 3.7.1 already installed on my system. So, we should run the following commands to install requests http library and beautifulSoup4 module.

`$ pip install requests`

`$ pip install beautifulsoup4`














## 8. Import installed libraries

Next, I will import the required libraries to use in this project.

The `urllib.request` library is used to open URLs. 

The `BeautifulSoup` library is used to extract data from html files. 

I will import these libraries as follows:-

`import requests`
`from bs4 import BeautifulSoup`





## 9. Access HTML content from a webpage

I have imported the necessary libraries for web scraping. Now, I will specify the url containing the dataset and pass it to `urlopen()` to access the html content of the webpage.

`url = 'http://stats.espncricinfo.com/wi/content/records/223646.html'`

`html = urlopen(url)`



## 10. Parse HTML content of the webpage

I have accessed the html content of the webpage. Next, I will create a BeautifulSoup object from the html. 

This is done by passing the html to the BeautifulSoup() function. The BeautifulSoup package is used to parse the html, that is, take the raw html text and break it into Python objects. The second argument 'html.parser' is the html parser to parse the html document.

`soup = BeautifulSoup(html, 'html.parser')`


### Check the type of object

Now, I will check the type of the soup object with the type() function as follows:-

`type(soup)`

The above command returns `bs4.BeautifulSoup` as the type of the soup object. 



## 11. Get the title of webpage

The soup object allows us to extract useful information about the website we are scraping. We can access the title of the webpage as follows:-

`print(soup.title)`


## 12. View the data in pretty format

I will now print out the HTML content of the webpage, formatted nicely, using the `prettify` method on the `BeautifulSoup` object. It gives the visual representation of the parsed tree created from the raw html content.

`print(soup.prettify())`




## 13. BeautifulSoup functions - find() and find_all()

BeautifulSoup has two main functions - **find()** and **find_all()**. 

We can use these functions to filter html pages to find lists of desired tags, or a single tag, based on their attributes.


The definitions of the two functions, as given in the BeautifulSoup documentation are as follows:-


`find_all(tag, attributes, recursive, text, limit, keywords)`

`find(tag, attributes, recursive, text, keywords)`



- The `tag` argument is the string name of a tag or even a Python list of string tag names.


- The `attributes` argument takes a Python dictionary of attributes and matches tags that contain any one of those attributes.


- The `recursive` argument is a boolean. It signifies how deep into the document we want to search. If recursive is set to True,  the find_all function looks into children, and children's children, for tags that match the parameters. If it is False, it will look only at the top-level tags in the document. By default, recursive is set to True.
  
  
- The `text` argument matches content based on the text content of the tags.


- The `limit` argument is used only in the find_all() method. find() is equivalent to the same find_all(), with a limit of 1.
  We can set this if we are interested only in retrieving the first x items from the page.


- The `keyword` argument allows to select tags that contain a particular attribute or set of attributes.





## 14. BeautifulSoup objects


BeautifulSoup transforms a complex HTML document into a complex tree of Python objects. 


There are four kinds of BeautifulSoup objects: BeautifulSoup, Tag, NavigableString and Comment.


- The `BeautifulSoup` object itself represents the document as a whole. We can treat it as a Tag object. It supports most of 
  the methods for navigating the tree and searching the tree.
  
  
- A `Tag` object corresponds to an XML or HTML tag in the original document. Tags have a lot of attributes and methods. The most   important features of a tag are its name and attributes. They can be accessed as `tag.name` and `tag.attrs`.


- `NavigableString` objects are used to represent text within tags, rather than the tags themselves.

- `Comment` object is used to find HTML comments in comment tags.



## 15. Access children property of object

All the tags are nested. So, we can move through the structure one level at a time. We can first select all the elements at the top level of the page using the `children` property of soup. The `children` property returns a list generator. So we need to call the list function on it as follows:-

`list(soup.children)`

## 16. Access html tags within a webpage

We can use the **find_all()** method of soup to extract useful html tags within a webpage. 

Examples of useful tags include < a > for hyperlinks, < table > for tables, < tr > for table rows, < th > for table headers, and < td > for table cells. 

The code below shows how to extract all the hyperlinks within the webpage.

`links = soup.find_all('a')`

`links`





## 17. Print the tables

The tables can be printed with the following command:-

`tables = soup.find_all('table')`

`tables`




## 18. Print the table rows

We can print the table rows as follows:-


`rows = soup.find_all('tr')`

`rows`



## 19. Print the table headers

We can print the table headers as follows:-

`headers = soup.find_all('th')`

`headers`


There are 11 columns in the table. 

The column headers are - `player name`, `playing span`, `matches played`, `innings batted`, `not outs`, `runs scored`, `highest inns score`, `batting average`, `hundreds scored`, `fifties scored` and `ducks scored`.




## 20. Print the table cells


We can print the table cells as follows:-

`cells = soup.find_all('td')`

`cells`
