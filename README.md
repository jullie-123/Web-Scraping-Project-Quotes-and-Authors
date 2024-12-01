# Web Scraping Project

## Overview
This project involves web scraping a website containing inspiring quotes and their authors. The aim was to gather meaningful data for educational purposes.

## Data Sources
Data was got from Quotes to Scrape website

## Tools and libraries used
- Python
- BeautifulSoup: For parsing HTML content.
- Requests: For making HTTP requests.
- Pandas: For data cleaning and analysis.
- Jupyter Notebook: For documenting and presenting the workflow.

## Data Extraction
- Sent HTTP requests to fetch the webpage's HTML.
- Used BeautifulSoup to parse and extract relevant data elements.

```python
import requests

from bs4 import BeautifulSoup

url = 'http://quotes.toscrape.com/.'

response = requests.get(url)

soup = BeautifulSoup(response.text, 'html.parser')

print(soup)
```

```python
quotes = soup.find_all('span', class_='text')

 authors = soup.find_all('small', class_='author')

for i in range(len(quotes)):
    print(f'Quote: {quotes[i].text.strip()}')
    print(f'Author: {authors[i].text.strip()}')
    print('---')
```


