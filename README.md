## Web Scraping

### Accessing Data Using BeautifulSoup

Use BeautifulSoup to get quotes, authors, and tags from [Quotes to Read](http://quotes.toscrape.com/).

Before answering these questions, go to the site and inspect the page. Make sure to look at what links there are and how the site is structured.

Reminder of CSS selector rules:

 - Start with HTML Element Type
 - `.` (period) means "with the following class"
 - `#` (hash symbol) means "with the following id"

CSS selector examples:

---

Element: `<div id="masterSearchResults">...</div>`

Selector: `"div#masterSearchResults"`

---

Element: `<ul id="authorList"><li>Stephen King</li></ul>` (inner `li` tag)

Selector: `"ul#authorList li"`

---


```python
from bs4 import BeautifulSoup
import requests
```


```python
# Make a get request to retrieve the page
html_page = requests.get('http://quotes.toscrape.com/') 
# Pass the page contents to beautiful soup for parsing
soup = BeautifulSoup(html_page.content, 'html.parser')
```

1. Get the first author and the path for the author's page as a tuple from the [homepage](http://quotes.toscrape.com/).


```python
# Your code here
```

2. Write a function to get **all** the authors and href links for the authors from the [homepage](http://quotes.toscrape.com/)



```python
def authors(url):
    '''
    input: url
    
    return: a dictionary of of authors and their urls
            {'author_1':'url_of_author_1', 'author_2':'url_of_author_2' ...}
    '''
    # your code here
```


```python
# run this cell to test the function
print(authors('http://quotes.toscrape.com/'))
print('\n')
print(authors('http://quotes.toscrape.com/page/3'))
```

### Pagination

3. Get the first author on each of the first 5 pages of quotes. You can get to the next page with the next button at the bottom of the homepage.



```python
# Your code here
```

4. Write a function to get all of the quotes from a page.


```python
def get_some_quotes(url):
    '''
    input: url, number of pages to scrap (just scrape the home page if no argument is passed in)
    
    return: a list of dictionaries of quotes with their attributes
            [{'quote':'quote_1_text', 'author':'url_of_author_1'}, 
            {'quote':'quote_2_text', 'author':'url_of_author_2', 'quote_tags':[list_of_quote_2_tags]}, ...]
    '''
    # your code here
```


```python
# set the result of the function to a variable
quotes = get_some_quotes('http://quotes.toscrape.com/' )
quotes
```


```python

```
