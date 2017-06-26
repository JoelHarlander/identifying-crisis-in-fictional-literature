## In this project I look at how we can extract context from fictional literature, and identify if we can get information about real world events.

We will be using the same data that the [Ngram Viewer](https://books.google.com/ngrams)

# 1. Getting the data
Using XPath and Requests libraries for python I downloaded all the files that met the following requirements:
- English
- data from fictional books
By default Requests loads all the data into memory before writing it, some of the files were larger than  12GB so the stream option was needed to write the files to disk blocks at a time.
Data located here: http://storage.googleapis.com/books/ngrams/books/datasetsv2.html

#2. Loading the data into a PostgreSQL database
We now have a multitude of compressed Tab Separated files(TSV's) containing our data.
To extract each one would be a pain, we know each file contains only one CSV so it makes sense to programmatically do this.
Line by line I extracted the TSV's and inserted them into the database directly.

Our data now looks like this:
![Top 1000 rows](images/1000.png)

