Lab 33: Basic Web Scraping with Requests and BeautifulSoup

1. Objectives

- Understand the basics of web scraping using "requests" and "BeautifulSoup".
- Learn how to retrieve webpages and parse HTML content.
- Extract specific information from a webpage.

2. Libraries Used

Requests

The "requests" library is used to send HTTP requests and retrieve webpage content from a server.

BeautifulSoup

BeautifulSoup is a Python library used to parse HTML and extract specific information from webpages.

Installation:

python -m pip install requests beautifulsoup4

3. Understanding Web Scraping

Web scraping is the process of collecting specific information from webpages using code.

Basic workflow:

1. Send an HTTP request.
2. Retrieve the webpage's HTML content.
3. Parse the HTML.
4. Search for specific elements.
5. Extract the required information.

4. Retrieving a Webpage

import requests

url = "https://example.com"

response = requests.get(url)

print(response.status_code)

Important concepts:

- "requests.get(url)" sends a GET request.
- "response" stores the server's response.
- "response.status_code" returns the HTTP status code.
- "200" means the request was successful.
- "404" means the requested resource was not found.
- "500" indicates a server-side error.

5. Retrieving HTML Content

print(response.text)

"response.text" returns the webpage's HTML content as text.

6. Parsing HTML with BeautifulSoup

from bs4 import BeautifulSoup

soup = BeautifulSoup(response.text, "html.parser")

Explanation:

- "response.text" provides the HTML content.
- "BeautifulSoup()" creates a parsed representation of the HTML.
- ""html.parser"" tells BeautifulSoup which parser to use.
- "soup" stores the parsed HTML.

7. Extracting Headings

heading = soup.find("h1")

print(heading.get_text())

- "find("h1")" searches for the first matching heading.
- ".get_text()" extracts only the text without HTML tags.

8. Extracting Webpage Titles

title = soup.find("title")

print(title.get_text())

This extracts the text inside the HTML "<title>" tag.

9. Extracting Paragraphs

paragraphs = soup.find_all("p")

for paragraph in paragraphs:
    print(paragraph.get_text())

- "find_all("p")" finds all paragraph elements.
- The "for" loop processes each paragraph.
- ".get_text()" extracts the paragraph's text.

10. Extracting Links

Example HTML:

<a href="https://example.com">Visit Website</a>

Python:

links = soup.find_all("a")

for link in links:
    print(link.get_text())
    print(link.get("href"))

Important concepts:

- "find_all("a")" finds all anchor elements.
- ".get_text()" extracts the visible link text.
- ".get("href")" extracts the destination URL.

11. Understanding HTML Attributes

Example:

<a href="https://example.com" class="website-link">
    Visit Website
</a>

Element| Purpose
"a"| Anchor tag
"href"| Contains the destination URL
"class"| Identifies or groups HTML elements
"website-link"| Class attribute value

Searching by class:

soup.find("a", class_="website-link")

Why "class_"?

"class" is a reserved keyword in Python. BeautifulSoup uses "class_" to search for HTML class attributes.

12. Difference Between find() and find_all()

Method| Purpose
"find()"| Returns the first matching element
"find_all()"| Returns all matching elements

Examples:

soup.find("h1")
soup.find_all("p")
soup.find_all("a")

13. Handling Missing Elements

During this lab, we encountered:

AttributeError: 'NoneType' object has no attribute 'get_text'

Why did this happen?

The "find()" method returns "None" when it cannot find the requested HTML element.

Calling ".get_text()" on "None" causes an "AttributeError".

Solution:

heading = soup.find("h1")

if heading:
    print(heading.get_text())
else:
    print("Heading not found!")

This is an example of defensive programming: checking whether an element exists before trying to use it.

14. Debugging Techniques Used

We used print debugging to inspect returned values:

print("Heading object:", heading)
print("Page title:", soup.find("title"))

This helped us understand what BeautifulSoup actually found in the webpage.

15. Python Command-Line Concept

We also practised Python's "-c" option:

python -c 'print("Hello")'

The "-c" option executes Python code directly from the terminal without creating a Python file.

Both single and double quotation marks can define Python strings. Using different outer and inner quotation marks avoids conflicts in shell commands.

16. Key Takeaways

- "requests" retrieves webpage content.
- "response.text" provides HTML content.
- "BeautifulSoup()" parses HTML.
- "find()" searches for the first matching element.
- "find_all()" searches for all matching elements.
- ".get_text()" extracts visible text.
- ".get("href")" extracts link destinations.
- "class_" searches HTML class attributes.
- "if/else" helps handle missing elements.
- Print debugging helps inspect program behaviour.

17. Security and Responsible Scraping

When scraping webpages:

- Respect website terms and access restrictions.
- Do not bypass authentication or access controls.
- Avoid excessive requests to servers.
- Only collect information you are authorized to access.

Lab Status

Completed — Lab 33: Basic Web Scraping with Requests and BeautifulSoup.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/abe3e95a-fe63-492d-bee3-4b8900e87a4b" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/f6968c75-9b97-4685-9acd-d88a6714f2a3" />

