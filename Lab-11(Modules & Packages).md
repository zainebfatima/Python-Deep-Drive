🐍 Python Deep Dive — Lab 11

Modules & Packages

🎯 Objectives

By the end of this lab, I learned how to:

- Understand the concept of Python modules.
- Import and use functions from modules.
- Understand the structure and purpose of packages.
- Create my own modules and packages.
- Import specific functions from a module.
- Use aliases when importing modules.

---

📚 What I Learned

1. What is a Module?

A module is a Python file (".py") that contains reusable code such as functions.

Instead of writing the same function again in another program, I can put it inside a module and import it whenever I need it.

Example

calculator.py

def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

Then I can use these functions from another file:

import calculator

print(calculator.add(10, 5))
print(calculator.subtract(10, 5))

Output:

15
5

---

🔄 Different Ways to Import

Import the whole module

import calculator

print(calculator.add(7, 3))

Import with an alias

import calculator as calc

print(calc.add(7, 3))

Here, "calc" is a shorter name for "calculator".

Import a specific function

from calculator import add

print(add(7, 3))

This imports only the "add()" function.

---

📦 What is a Package?

A package is a folder that groups related Python modules together.

My analogy:

«🍕 Function = food
🍽️ Module = plate containing food
📦 Package = box containing plates
🏠 Project = the whole kitchen/restaurant»

Example:

mypackage/
├── greetings.py
└── calculator.py

Here:

- "mypackage" → package
- "greetings.py" → module
- "calculator.py" → module
- "hello()" → function
- "multiply()" → function

---

🛠️ Creating My Own Package

I created a package called:

mypackage

Inside it, I created "greetings.py":

def hello(name):
    return "Hello, " + name

I then imported the function into "main.py":

from mypackage.greetings import hello

print(hello("Zaineb"))

Output:

Hello, Zaineb

---

🧪 Mini Challenge

I created another module inside my package:

mypackage/calculator.py

def multiply(a, b):
    return a * b

def divide(a, b):
    return a / b

Then I imported only the "multiply()" function:

from mypackage.calculator import multiply

print(multiply(6, 4))

Output:

24

---

🧠 Important Understanding

The following:

from mypackage.calculator import multiply

means:

From the "mypackage" 📦
→ go to the "calculator" module 🍽️
→ import the "multiply" function 🍕

Then:

print(multiply(6, 4))

runs the function and prints:

24

---

💡 Key Takeaway

Modules and packages help organize and reuse code.

Instead of writing the same functions repeatedly, I can write them once in a module and import them whenever I need them.

Structure

Function → Module → Package → Project

---

🛡️ Cybersecurity Connection

Modules and packages are especially useful in larger cybersecurity projects.

For example, a project could have separate modules for:

scanner.py
port_scanner.py
ip_checker.py
utils.py

Instead of putting everything into one huge Python file, I can organize related functionality into separate modules and reuse the functions where needed.

---

✅ Lab Status

- [x] Understand modules
- [x] Create a custom module
- [x] Import a module
- [x] Use a module alias
- [x] Import a specific function
- [x] Understand packages
- [x] Create a custom package
- [x] Create modules inside a package
- [x] Import a function from a package
- [x] Complete a mini challenge

Lab 11 completed successfully!
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/c6267d53-0dff-48d4-b26f-f949937be921" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/7f46ccd0-36a1-4556-b9e1-4e984c48dc51" />

