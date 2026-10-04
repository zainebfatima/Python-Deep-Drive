# 🐍 Python Deep Dive — Lab 12
## File I/O Basics

### 🎯 Objectives

By the end of this lab, I learned how to:

- Understand the basic concepts of File I/O in Python.
- Read from and write to files using Python's built-in functions.
- Use context managers to efficiently handle files.

---

## 📚 What I Learned

### 1. What is File I/O?

I/O means *Input / Output*.

In Python, File I/O allows a program to interact with files.

- *Input* → Reading data from a file 📖
- *Output* → Writing data to a file ✍️

Example:

```text
Python → ✍️ writes → notes.txt
Python ← 📖 reads  ← notes.txt
Writing to a File
I learned how to use "w" mode to write to a file.
file = open("notes.txt", "w")

file.write("Hello, Zaineb!")

file.close()
If notes.txt does not exist, Python creates it.
Important:
"w" means write mode.
If the file already exists, "w" can replace its existing contents.
📖 Reading from a File
I learned how to read the contents of a file using "r" mode.
file = open("notes.txt", "r")

content = file.read()

print(content)

file.close()
Output:
Hello, Zaineb!
Important:
"r" means read mode.
If the file does not exist, Python gives a FileNotFoundError.
➕ Append Mode
I learned how to add new information to an existing file without replacing its old content.
with open("notes.txt", "a") as file:
    file.write("Welcome to Python!\n")
Important:
"a" means append mode.
It adds new content to the end of the file.
If the code is run multiple times, the text will be added multiple times.
🧹 Context Managers
Instead of manually opening and closing a file:
file = open("notes.txt", "r")

content = file.read()

print(content)

file.close()
I learned to use a context manager:
with open("notes.txt", "r") as file:
    content = file.read()

print(content)
The with statement automatically handles closing the file after the block is finished.
🧠 My Understanding
I think of with as:
"Python, manage this file for me."
This makes the code shorter, cleaner, and safer.
📋 File Modes
Mode
Purpose
"r"
Read
"w"
Write
"a"
Append
Easy way to remember:
"r" → 📖 Read
"w" → ✍️ Write
"a" → ➕ Add
🧪 Practical Work
During this lab, I created:
file_io.py
notes.txt
My Python program was able to:
Create a text file.
Write text into it.
Read the text.
Append additional text.
Use a context manager to handle the file.
💡 Important Difference
I also learned the difference between viewing a file with Linux and running Python code.
Linux:
cat notes.txt
This only displays the contents of the file.
Python:
python3 file_io.py
This executes the Python code inside file_io.py.
🛡️ Cybersecurity Connection
File I/O is very useful in cybersecurity.
Python programs can use files to:
Store scan results.
Read configuration files.
Save logs.
Process lists of targets.
Record program output.
Analyze text-based data.
For example, a future security tool could save its results into:
scan_results.txt
and then Python could read and process those results.
🧠 Key Takeaways
File I/O allows Python to interact with files.
"w" is used for writing.
"r" is used for reading.
"a" is used for appending.
read() gets file contents.
write() puts data into a file.
with open(...) is the recommended way to manage files.
File I/O Flow
📄 File
   ↓
open()
   ↓
read() / write()
   ↓
with → automatically handles closing
✅ Lab Status
[x] Understand File I/O
[x] Create a file using Python
[x] Write to a file
[x] Read from a file
[x] Understand "r" mode
[x] Understand "w" mode
[x] Understand "a" mode
[x] Append data to a file
[x] Use context managers
[x] Complete practical File I/O exercises
Lab 12 completed successfully! 🚀
```
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/a1a26ec7-f871-4e67-b9e1-b5a3f350ec93" />
