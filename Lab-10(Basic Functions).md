🐍 Python Deep Dive — Lab 10: Basic Functions

📌 Lab Overview

In this lab, I learned the basics of functions in Python. I learned how to define and call functions, use parameters, use default parameters, and pass arguments using both positional and keyword arguments.

I also created a simple greeting function and practiced using "return" to send a value back from a function.

---

🎯 Objectives

- Introduce the concept of functions in programming.
- Learn to define and call functions with and without parameters.
- Understand default parameters and keyword arguments.
- Demonstrate practical usage by creating a greeting function.

---

1️⃣ What is a Function?

A function is a reusable block of code that performs a specific task.

Instead of writing the same code again and again, we can put it inside a function and call the function whenever we need it.

Example

def greet():
    print("Hello!")

greet()

Output

Hello!

Here:

- "def" is used to define a function.
- "greet" is the function name.
- "()" contains parameters if needed.
- "greet()" calls the function.

---

2️⃣ Function with a Parameter

A parameter allows us to give information to a function.

def greet(name):
    print("Hello,", name)

greet("Ali")
greet("Sara")

Output

Hello, Ali
Hello, Sara

The same function can be reused with different values.

---

3️⃣ Multiple Parameters

A function can have more than one parameter.

def introduce(name, field):
    print("My name is", name)
    print("I study", field)

introduce("Ali", "Cybersecurity")

Output

My name is Ali
I study Cybersecurity

The order of positional arguments matters.

---

4️⃣ Default Parameters

A parameter can have a default value.

def greet(name="friend"):
    print("Hello,", name)

greet()
greet("Ali")

Output

Hello, friend
Hello, Ali

If no value is provided, Python uses the default value.

---

5️⃣ Keyword Arguments

Keyword arguments allow us to specify which parameter each value belongs to.

def introduce(name, field):
    print("Name:", name)
    print("Field:", field)

introduce(field="Cybersecurity", name="Ali")

Output

Name: Ali
Field: Cybersecurity

The order does not matter when using keyword arguments because the parameter names are explicitly provided.

---

6️⃣ Functions with "return"

I also practiced using "return".

def add(a, b):
    return a + b

result = add(10, 7)

print(result)

Output

17

Important Difference

- "print()" → displays something on the screen.
- "return" → sends a value back from the function.

I found "print()" easier to understand, so I focused mainly on simple functions using "print()" during this lab.

---

7️⃣ Practical Greeting Function

My final simple greeting function was:

def greet(name):
    print("Hello,", name)

greet("Zaineb")
greet("Ali")
greet("Sara")

Output

Hello, Zaineb
Hello, Ali
Hello, Sara

This demonstrated how one function can be reused with different arguments.

---

🧠 What I Learned

In this lab, I learned that:

- Functions help organize and reuse code.
- "def" is used to create a function.
- A function is executed when we call it.
- Parameters allow functions to receive information.
- Default parameters provide a value when no argument is given.
- Keyword arguments let us specify parameters by name.
- "return" can send a value back from a function.
- The same function can be called multiple times with different values.

---

💻 Terminal Practice

I created and ran my Python file from the Ubuntu terminal:

nano lab10.py

Then I executed it with:

python3 lab10.py

This helped me understand that Python executes the code that is actually saved inside the file.

---

🔐 Cybersecurity Connection

Functions are very important in cybersecurity programming because they allow us to organize repeated tasks into reusable pieces of code.

For example, later I can create functions for:

- validating user input
- checking passwords
- processing URLs
- analyzing files
- scanning information
- processing security results

Learning functions is an important step toward building larger Python security tools.

---

✅ Lab Status

Lab 10 — Basic Functions: COMPLETED ✅

Next: Lab 11
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/2f3983e1-0c97-4d30-9c71-88f58e333a78" />

