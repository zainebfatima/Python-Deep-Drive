Lab 14: JSON Handling

Objectives

- Understand how to create a Python dictionary and convert it to JSON.
- Learn how to store JSON data in a file and read it back.
- Understand the use of JSON for storing configuration or data.

---

1. What is JSON?

JSON stands for JavaScript Object Notation.

JSON is a common data format used to store and exchange data between different programs and programming languages.

Python can work with JSON, but JSON is not limited to Python. Languages such as JavaScript, Java, and C# can also work with JSON.

---

2. Creating a Dictionary and Converting It to JSON

Python Code

import json

student = {
    "name": "Zaineb",
    "course": "Python",
    "field": "Cybersecurity"
}

json_data = json.dumps(student)

print(json_data)

Output

{"name": "Zaineb", "course": "Python", "field": "Cybersecurity"}

What I Learned

- "import json" imports Python's built-in JSON module.
- A dictionary stores data using keys and values.
- "json.dumps()" converts a Python dictionary into JSON-formatted data.
- The converted data was stored in the variable "json_data".

---

3. Saving JSON Data to a File

Python Code

import json

student = {
    "name": "Zaineb",
    "course": "Python",
    "field": "Cybersecurity"
}

with open("student.json", "w") as file:
    json.dump(student, file)

print("JSON data saved successfully")

Output

JSON data saved successfully

This created a file called:

student.json

The file contains:

{"name": "Zaineb", "course": "Python", "field": "Cybersecurity"}

Important Terms

- ""w"" means write mode.
- "json.dump()" writes the Python data into the JSON file.
- "student.json" is the file where the data is stored.

---

4. Reading JSON Data from a File

Python Code

with open("student.json", "r") as file:
    data = json.load(file)

print(data)

Output

{'name': 'Zaineb', 'course': 'Python', 'field': 'Cybersecurity'}

Important Terms

- ""r"" means read mode.
- "json.load()" reads JSON data from the file and converts it back into Python data.
- Reading the file does not remove the data from the file.

---

5. "dump()" vs "load()"

json.dump() → Python data → JSON file
json.load() → JSON file → Python data

A simple way to remember:

dump = PUT data into the file
load = GET data from the file

---

6. JSON for Configuration and Data Storage

JSON can be used to store:

- Application settings
- User information
- API data
- Tool configuration
- General data

For example:

{
    "username": "Zaineb",
    "theme": "dark",
    "scan_timeout": 30
}

A program can read these settings from the JSON file instead of having them directly inside the Python code.

---

Key Takeaways

- JSON is a data format, not a programming language.
- Python dictionaries use keys and values.
- "json.dumps()" converts Python data into JSON-formatted data.
- "json.dump()" writes JSON data into a file.
- "json.load()" reads JSON data from a file.
- JSON allows data to be stored and exchanged between different programs and programming languages.
- JSON is commonly used with APIs.

Lab Status

Lab 14 completed successfully. ✅
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/d425700e-9a93-4ff1-9b4a-9bfd661cf1d0" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ce9742c6-1289-4a54-9863-538e507e8d2a" />

