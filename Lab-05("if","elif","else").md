 Python Deep Dive — Lab 5

Understanding Conditionals ("if", "elif", "else")

🎯 Objectives

By completing this lab, I learned how to:

- Use "if", "elif", and "else" statements.
- Control program flow using conditions.
- Handle multiple possible conditions.
- Compare values using comparison operators.
- Use logical operators such as "and".
- Classify input based on conditions.
- Understand the difference between strings and integers when comparing values.

---

📚 Concepts Learned

1. "if"

The "if" statement checks whether a condition is true.

age = 20

if age >= 18:
    print("Adult")

---

2. "if" and "else"

"else" runs when the "if" condition is false.

age = 15

if age >= 18:
    print("Adult")
else:
    print("Minor")

---

3. "if", "elif", and "else"

"elif" allows Python to check another condition if the previous condition was false.

marks = 75

if marks >= 90:
    print("Grade A")
elif marks >= 70:
    print("Grade B")
elif marks >= 50:
    print("Grade C")
else:
    print("Fail")

Python checks the conditions from top to bottom and executes the first condition that is true.

---

🔢 Comparison Operators

Operator| Meaning
">"| Greater than
"<"| Less than
">="| Greater than or equal to
"<="| Less than or equal to
"=="| Equal to

Important Lesson

I learned that ">=" and "<=" include equality.

For example:

num >= 0

means:

«The number is greater than OR equal to zero.»

For positive/negative/zero classification, I used:

if num > 0:
    print("Positive")
elif num < 0:
    print("Negative")
else:
    print("Zero")

---

🧪 Practice: Number Classification

I created a program that takes a number from the user and classifies it as positive, negative, or zero.

num = int(input("Enter a number: "))

if num > 0:
    print("Positive")
elif num < 0:
    print("Negative")
else:
    print("Zero")

Example

Enter a number: -7
Negative

Enter a number: 0
Zero

---

🔐 Logical Operator: "and"

I learned that "and" requires both conditions to be true.

Example:

username = input("Enter your username: ")
password = input("Enter your password: ")

if username == "admin" and password == "1234":
    print("Login Successful")
else:
    print("Login Failed")

The login succeeds only when both conditions are true.

---

🧠 Important Discovery: String vs Integer

During the login exercise, I initially used:

password = int(input("Enter your password: "))

and compared it with:

password == "1234"

This failed because:

1234   → integer
"1234" → string

I corrected it by using:

password = input("Enter your password: ")

This taught me that Python treats strings and integers as different data types, even when they contain similar-looking values.

---

💡 Key Takeaways

- "if" is used to make a decision.
- "elif" checks another condition.
- "else" handles the remaining case.
- Python evaluates conditional branches from top to bottom.
- Once a true branch is found, the remaining branches are skipped.
- "and" requires both conditions to be true.
- "input()" returns a string by default.
- "int()" converts input into an integer.
- Comparison operators are essential for decision-making in Python.
- Small logical mistakes can change the result even when the program runs without errors.

---

🔐 Cybersecurity Connection

Conditionals are important in cybersecurity programming because security tools and scripts often need to make decisions based on input.

Examples include:

- Checking whether credentials are valid.
- Validating user input.
- Checking access permissions.
- Classifying scan results.
- Automating security checks.
- Handling different responses from systems.

This lab was my first step toward using Python to build decision-making logic for cybersecurity automation.

---

📝 Lab Status

Lab 5 — Completed ✅

I practiced the concepts by writing and testing the code myself rather than simply copying examples.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/05bacfcc-2d7b-4191-b197-ecb73522f902" />
