🐍 Lab 2: Hello World & Basic Syntax

🎯 Objectives

- Understand how to create a simple Python script.
- Learn how to execute a Python script using the command line.
- Gain familiarity with Python's indentation rules to define code blocks.
- Experiment with basic syntax through simple control structures.

---

💻 Environment

Platform: Al-Nafi Lab Terminal
Operating System: Ubuntu Linux
Python Version: Python 3.12.3

---

📝 Step 1: Create a Python Script

I created a Python file using the Nano text editor:

nano hello.py

The file was named:

hello.py

---

🐍 Step 2: Write the Python Code

Inside the file, I wrote:

print("Hello, World!")

The "print()" function is used to display output on the screen.

---

▶️ Step 3: Execute the Python Script

I ran the script from the Linux command line using:

python3 hello.py

Output:

Hello, World!

This confirmed that the Python script was successfully created and executed.

---

🧠 Understanding Scripts vs. Interpreter

In Lab 1, I executed Python code directly inside the Python interpreter:

>>>

For example:

print("hello, python")

In this lab, I wrote Python code inside a ".py" file and executed the entire file from the Linux terminal:

python3 hello.py

The basic process:

Python Code
     ↓
hello.py
     ↓
python3 hello.py
     ↓
Python executes the script
     ↓
Output

---

📐 Python Indentation

Python uses indentation (spaces at the beginning of a line) to define blocks of code.

Unlike some programming languages, Python does not use curly brackets "{}" to define these blocks.

Example:

if 10 > 5:
    print("10 is greater than 5")

The indented line belongs to the "if" block.

Correct indentation is therefore an important part of Python syntax.

---

🔹 Basic Control Structure

Example:

age = 20

if age >= 18:
    print("Adult")

Here:

- "if" is a conditional statement.
- "age >= 18" is the condition.
- The indented "print()" statement runs when the condition is true.

---

🧠 What I Learned

- A Python script is usually saved with the ".py" extension.
- Python scripts can be executed from the command line.
- "print()" displays information on the screen.
- Python uses indentation to define code blocks.
- Basic control structures such as "if" use indentation to show which statements belong to them.
- Python code can be written in a file and executed whenever needed.

---

🔐 Connection to Cybersecurity

Python scripts are widely used for automation in cybersecurity.

The basic process I learned in this lab:

Write Script
    ↓
Save Script
    ↓
Execute Script
    ↓
Get Results

is the same basic workflow I will later use when creating cybersecurity automation tools.

---

✅ Lab Status

- [x] Created a Python script
- [x] Saved the script as ".py"
- [x] Executed the script using the command line
- [x] Used "print()" to display output
- [x] Learned the purpose of indentation
- [x] Explored a basic "if" control structure

---

📝 Key Takeaway

«A Python script is a file containing Python instructions that can be executed from the command line using the Python interpreter.»
