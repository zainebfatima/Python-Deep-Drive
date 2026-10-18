🐍 Python Deep Dive — Lab 23: Using Requests for HTTP Calls

📌 Lab Overview

Lab Number: 23
Topic: Using Python "requests" for HTTP Calls
Environment: Ubuntu Cloud Terminal — Al-Nafi
Python Version: Python 3.12
Virtual Environment: "venv"
Requests Version: 2.34.2
Status: Completed ✅

---

🎯 Learning Objectives

By completing this lab, I learned how to:

1. Send HTTP GET requests using Python's "requests" library.
2. Understand HTTP status codes such as "200" and "404".
3. Read and parse JSON responses using "response.json()".
4. Send query parameters using "params".
5. Access nested dictionary values.
6. Handle HTTP errors using "raise_for_status()".
7. Use "try" and "except" to handle request exceptions.
8. Set a timeout for HTTP requests.

---

1. Setting Up the Environment

I used a Python virtual environment to keep the lab's dependencies separate.

python3 -m venv venv
source venv/bin/activate
pip install requests

I verified the installed library version:

python3 -c "import requests; print(requests._version_)"

Output:

2.34.2

Setup problems I encountered

- The initial virtual environment setup failed because "ensurepip" was unavailable.
- Installing the required package initially encountered APT download errors ("404").
- I updated the package lists and installed "python3.12-venv" before continuing.

What I learned: Python virtual environments may require additional system packages before they can be created successfully.

«Environment note: My Al-Nafi cloud terminal is temporary, so files and virtual environments may disappear when the session closes.»

---

2. Understanding HTTP GET Requests

I used the HTTP testing service "httpbin.org" to send a GET request.

import requests

response = requests.get("https://httpbin.org/get")

print("status code:", response.status_code)
print("response URL:", response.url)
print("response text:", response.text)

Important output

status code: 200
response URL: https://httpbin.org/get

The response body contained JSON-formatted information, including request headers, the observed public IP address, and the requested URL.

What I learned

- "requests.get()" sends an HTTP GET request.
- "response" stores the server's response.
- "response.status_code" tells me the HTTP status.
- "response.url" shows the final request URL.
- "response.text" returns the response body as text.

HTTP status codes

Status code| Meaning
"200 OK"| The request succeeded.
"404 Not Found"| The requested resource was not found.
"500 Internal Server Error"| The server encountered an error.

Important: A "404" response is an HTTP response, not automatically a Python syntax error.

---

3. Query Parameters with "params"

I learned how to send additional information with a GET request.

import requests

url = "https://httpbin.org/get"

params = {
    "course": "python",
    "lab": 23
}

response = requests.get(url, params=params)

print(response.url)
print(response.text)

The request URL includes query parameters, similar to:

https://httpbin.org/get?course=python&lab=23

The server's JSON response contains an "args" object with the submitted parameters.

Why use "params=params"?

requests.get(url, params=params)

- The first "params" is the argument name expected by the "requests" library.
- The second "params" is my Python dictionary variable.
- This tells Python to send the dictionary's key-value pairs as query parameters.

Question I answered: Why do we use "params=params"?

Correct answer: B — To send query parameters with the request.

What I understood

A URL can contain extra information after "?". The "requests" library can build that query string from a dictionary, so I do not have to construct the URL manually.

---

4. Parsing JSON into Python Data

I learned that a server can return JSON data and that "response.json()" can parse it into Python objects.

data = response.json()

For an object-shaped JSON response, the result is normally a Python dictionary.

Example:

{
  "course": "Python",
  "lab": 23
}

After parsing, I can access the values like this:

print(data["course"])
print(data["lab"])

Output:

Python
23

Accessing nested dictionaries

Our "httpbin.org/get" response stored the query parameters inside "args".

The structure looked like this:

data["args"]

That gives me the inner dictionary. To access a particular value:

print(data["args"]["course"])
print(data["args"]["lab"])

Expected output:

python
23

The "lab" value in this "httpbin" response is represented as the string ""23"" because query parameters are transmitted as text.

My questions and understanding

Question: How do I access the "lab" value inside "args"?

Answer:

data["args"]["lab"]

First, access "args"; then access "lab" inside it.

Question: What does "response.json()" do?

Answer: It parses the JSON response into Python data. Depending on the JSON structure, that data may be a dictionary, list, string, number, Boolean, or "None".

Mini-challenge: If the dictionary contains "{"course": "Python"}", how do I get the course?

Answer:

data["course"]

I initially selected the wrong option in the JSON challenge, then corrected my understanding: an object-shaped JSON response becomes a dictionary, not automatically a list.

---

5. Understanding "try", "except", and "raise_for_status()"

I learned how to handle HTTP errors rather than letting an HTTP error interrupt the normal flow without being handled.

Testing an intentional 404 response

import requests

response = requests.get("https://httpbin.org/status/404")

print("Status code:", response.status_code)

Expected output:

Status code: 404

This endpoint intentionally returns a "404" status for testing.

What does "raise_for_status()" do?

response.raise_for_status()

It raises an HTTP-related exception for unsuccessful HTTP status codes, such as "404" or "500".

If the response is successful, such as "200", it normally continues without raising an HTTP status exception.

Handling the exception

import requests

try:
    response = requests.get(
        "https://httpbin.org/status/404",
        timeout=10
    )

    response.raise_for_status()
    print("Request successful!")

except requests.exceptions.RequestException as error:
    print("Request error:", error)

Actual result

Request error: 404 Client Error: Not Found ...

The URL continued after the error message, so it is shortened here for readability.

Why did this happen?

1. The GET request returned status "404".
2. "raise_for_status()" raised an HTTP error.
3. Python moved to the matching "except" block.
4. The error message was printed.
5. ""Request successful!"" was skipped because execution had moved into the exception handler.

Result: The error-handling test worked correctly. ✅

Understanding each keyword

- "try": Runs code that may encounter an exception.
- "except": Handles a matching exception.
- "as error": Stores the exception object in a variable named "error".
- "raise_for_status()": Raises an exception for unsuccessful HTTP status codes.
- "timeout=10": Limits how long the request waits for a response before timing out.

A timeout or connection problem can also raise a request exception. A timeout does not mean the server returned status "404"; they are different kinds of problems.

---

6. My Final Working Code

This combines query parameters, HTTP requests, JSON parsing, nested dictionary access, and error handling.

import requests

url = "https://httpbin.org/get"

params = {
    "course": "python",
    "lab": 23
}

try:
    response = requests.get(
        url,
        params=params,
        timeout=10
    )

    print("status code:", response.status_code)

    response.raise_for_status()

    data = response.json()

    print("course:", data["args"]["course"])
    print("lab:", data["args"]["lab"])

except requests.exceptions.RequestException as error:
    print("Request error:", error)

Actual successful output

status code: 200
course: python
lab: 23

The request succeeded, the JSON was parsed, and the values were extracted from the nested "args" dictionary.

---

7. Errors I Faced and How I Fixed Them

This section records my actual debugging experience, not just the final solution.

Error 1: "SyntaxError: expected ':'"

What happened: Python reported an error at the "except" line.

What I discovered: The "except" statement needed to be written as a complete statement on one line, including the exception type, the "as error" variable, and the ending colon.

Correct:

except requests.exceptions.RequestException as error:

Incorrect:

except

Lesson: Python keywords and their required syntax must be written correctly. "except" cannot stand alone when defining a specific exception handler.

Error 2: "IndentationError: expected an indented block after 'except'"

What happened: Python complained that the "except" block had no correctly indented body.

Fix:

except requests.exceptions.RequestException as error:
    print("Request error:", error)

Lesson: The code inside "except" must be indented. The "try" and "except" statements themselves align at the same indentation level.

Error 3: "SyntaxError: invalid syntax"

What happened: I had typed the exception class incorrectly as "RequestsException" rather than "RequestException", and at one point the "except" keyword was missing.

Fix:

except requests.exceptions.RequestException as error:

Lesson: Exception names are case-sensitive and must match the library's actual class name.

Error 4: Code formatting during copy-paste

What happened: Copying code into the terminal editor made indentation and line placement confusing.

Fix: I replaced the incorrect lines with the correct syntax and checked that the "try" block and "except" block were aligned properly.

Lesson: When debugging Python, inspect the actual file—not just how code appears in a chat message or wraps on a small screen.

Error 5: Confusion about the "except" line

What happened: I thought the exception details might belong on the next line.

What I learned: The exception declaration belongs on the same line as "except", and the colon goes at the end:

except requests.exceptions.RequestException as error:

The body goes on the next line, indented.

Personal debugging takeaway: I figured out that the "except" statement needed to be written correctly as one complete line. This was a useful lesson in reading Python's syntax errors carefully.

---

8. Questions I Asked During This Lab

Q1. Why use "params=params"?

Answer: The first "params" is the "requests.get()" argument, and the second is my dictionary variable. This sends the dictionary's values as query parameters.

Q2. What does "response.json()" do?

Answer: It parses the response body as JSON and returns the corresponding Python data structure.

Q3. How do I access a value inside a nested dictionary?

Answer: Use one key at a time.

data["args"]["lab"]

Q4. Why did the "except" line produce a syntax error?

Answer: The statement was incomplete or incorrectly written. The complete line requires the exception class, "as error", and a colon.

Q5. Why did we use "raise_for_status()"?

Answer: To raise an exception for HTTP error status codes so they can be handled in the "except" block.

Q6. Why was the output so short compared with the amount of code?

Answer: The code performed several steps behind the scenes: sent a request, received a response, checked its status, parsed JSON, extracted two values, and prepared error handling. The final output showed only the information we asked Python to print.

My realization: A short output does not mean the program did very little. Much of the work happens behind the scenes.

---

9. Final Mini-Challenges and Answers

Challenge 1: HTTP status codes

Question: If the server returns "200", what does it mean?

- A) The request succeeded.
- B) The page was not found.
- C) The internet is definitely disconnected.

My answer: A ✅

Challenge 2: Nested dictionary access

Question: How do I print the lab value from "data["args"]"?

My answer:

print(data["args"]["lab"])

Result: Correct. The value was "23" (represented as a string in the HTTPBin query arguments).

Challenge 3: Final JSON mini-challenge

Given:

data = response.json()

And a dictionary containing a "lab" key, which is correct?

- A) "print(data["lab"])"
- B) "print(data.lab)"
- C) "print(response["lab"])"

My answer: A ✅

Reason: Dictionary values are accessed using square brackets and the key.

---

10. Connection to Cybersecurity and Burp Suite

This lab connects directly to my cybersecurity learning journey.

Python Requests vs. Burp Suite

- Python Requests: Sends HTTP requests programmatically, making it useful for automation and repeatable testing.
- Burp Suite HTTP history: Helps me inspect requests and responses exchanged by a browser and a web application.
- HTTP status codes: Help me understand how a server responded to a request.
- Query parameters: Can reveal how an application receives search terms, identifiers, filters, and other input.

I also connected this concept to my earlier VDP exploration, where I examined domains and web assets.

Security reminder: I should only test systems I own or have explicit authorization to assess, and I must follow each program's scope and rules.

---

11. What I Learned

By the end of Lab 23, I could:

- Send a GET request with Python.
- Read an HTTP status code.
- Inspect a response URL and response body.
- Parse JSON into Python data.
- Extract values from nested dictionaries.
- Send query parameters using "params".
- Recognize the difference between "200" and "404".
- Use "raise_for_status()" to raise HTTP errors.
- Catch request exceptions with "try" and "except".
- Debug syntax and indentation errors.

My biggest lesson

Understanding the code matters more than memorizing it. I learned to trace the request, understand the response, access the data, and handle errors. I also learned that syntax and indentation are part of making a program work.

---

✅ Lab 23 Completed

Next step: Continue to Lab 24 in the Python Deep Dive series.

Documented as part of my ongoing Python and cybersecurity learning journey.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/476defe1-bf42-4d04-8471-1669d4a74da0" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ad8d5123-407f-4cdb-a57a-0aeb436d7e27" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/e736111e-4469-4c07-a427-97490741e343" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/98e73dfb-193f-455c-a7d0-d2ee9ebf5e9a" />



