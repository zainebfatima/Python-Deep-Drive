# Lab 20: Using Lambda & Higher-Order Functions

## 🎯 Objectives

- Understand lambda functions and their syntax in Python.
- Learn higher-order functions: map(), filter(), and reduce().
- Implement practical examples using lambda and higher-order functions.

---

## 1. Lambda Functions

A lambda function is a small anonymous function written in one expression.

### Syntax
python
lambda arguments: expression


### Example
python
square = lambda x: x * x
print(square(5))


*Output:*
text
25

A lambda function automatically returns the result of its expression, so we don't need to write return.

---

## 2. The map() Function

map() applies a function to every item in an iterable.

python
numbers = [1, 2, 3, 4, 5, 6]

squares = list(map(lambda x: x * x, numbers))
print(squares)


*Output:*
text
[1, 4, 9, 16, 25, 36]

*Key idea:* map() transforms every item.

---

## 3. The filter() Function

filter() selects items that satisfy a condition.

python
numbers = [1, 2, 3, 4, 5, 6]

evens = list(filter(lambda x: x % 2 == 0, numbers))
print(evens)


*Output:*
text
[2, 4, 6]

*Key idea:* filter() keeps items for which the condition is True.

---

## 4. The reduce() Function

reduce() combines items repeatedly to produce one final result. It must be imported from functools.

python
from functools import reduce

numbers = [1, 2, 3, 4, 5, 6]

total = reduce(lambda a, b: a + b, numbers)
print(total)


*Output:*
text
21


### Dry Run
text
1 + 2 = 3
3 + 3 = 6
6 + 4 = 10
10 + 5 = 15
15 + 6 = 21

*Key idea:* reduce() combines items into one result.

---

## 5. Complete Practical Program

This script includes an active pdb.set_trace() breakpoint so you can run it locally and step through the calculations interactively.

python
from functools import reduce
import pdb

numbers = [1, 2, 3, 4, 5, 6]

# Lambda function
square = lambda x: x * x
print("Square:", square(5))

# map(): square every number
squares = list(map(lambda x: x * x, numbers))
print("Squares:", squares)

# Trigger Python Debugger before processing data further
print("\n--- Entering Debugger Mode ---")
pdb.set_trace()

# filter(): select even numbers
evens = list(filter(lambda x: x % 2 == 0, numbers))
print("Even numbers:", evens)

# reduce(): calculate the total
total = reduce(lambda a, b: a + b, numbers)
print("Total:", total)


*Expected Output:*
text
Square: 25
Squares: [1, 4, 9, 16, 25, 36]

--- Entering Debugger Mode ---
> lab20.py(19)<module>()
-> evens = list(filter(lambda x: x % 2 == 0, numbers))
(Pdb) 


---

## 6. Debugging with PDB

Python's built-in debugger lets us pause execution and inspect variables.

### Setting a breakpoint
Add this line before the section you want to inspect:
python
pdb.set_trace()

Make sure you import pdb first:
python
import pdb


### Useful PDB commands

| Command | Purpose |
| :--- | :--- |
| n | Execute the next line |
| s | Step into a function call (or step inside a lambda) |
| p numbers | Print the value of the numbers variable |
| p squares | Inspect the squares list |
| l | Display nearby source code context |
| c | Continue running until the next breakpoint |
| q | Quit the debugger and stop execution |

### What I Practised
- Set a breakpoint right before the filter() execution block.
- Inspected the current contents of numbers and squares using p.
- Used n to safely execute the script lines one by one.
- Used s to step directly into the lambda function to watch parameters update.
- Observed how execution loops internally through data structures.
- Checked how a running total accumulates during each reduction pass.

> 💡 *Important:* PDB shows the current execution state. A variable's value changes only when the relevant assignment or iteration executes.

---

## 7. Comparing Loops and Higher-Order Functions

A normal loop can perform the same tasks as these functional tools. For example, calculating a total with a loop:

python
numbers = [1, 2, 3, 4, 5, 6]
total = 0

for number in numbers:
    total = total + number

print(total)


*Output:*
text
21

Higher-order functions express common data-processing tasks concisely. However, normal loops are often easier to read when conditional logic becomes deeply nested or highly complicated.

---

## 🛡️ Cybersecurity Connection

In security automation and log analysis, higher-order functions are essential. For example, when parsing massive SIEM or firewall logs:
- filter() allows you to rapidly screen out noise and focus purely on malicious indicators (like flagging specific attacking IP addresses or unauthorized 403 status codes).
- map() allows you to standardize unstructured string logs into clean, unified data formats or timestamps across automated tools.

---

## 8. Key Takeaways

- lambda creates a small, anonymous, one-expression function.
- map() transforms every item inside an iterable.
- filter() screens items based on a true/false condition.
- reduce() progressively combines items down into a single final value.
- pdb helps us inspect program execution contexts safely line-by-line.
- *Readable code is more important* than writing the shortest possible code line.

---

## 9. Lab Status

- [x] Lambda functions
- [x] map()
- [x] filter()
- [x] reduce()
- [x] Practical implementation
- [x] PDB debugging practice
- [x] Variable inspection
- [x] Running-total loop

*Status:* Completed ✅

*Repository:* CyberSecurity-journey  
*Lab:* Python Deep Dive — Lab 20  
*Next:* Lab 21 — continue the Python Deep Dive roadmap.

---

## 10. Questions I Asked During This Lab

### Q1. Why do we use map(), filter(), and reduce() if we still need to write expressions and conditions?
*My understanding:*
These functions reduce boilerplate loop code and make the intent of an operation obvious to other developers. We provide the internal filter logic, but Python handles the heavy lifting of execution under the hood:
- map() handles applying a transformation to every item.
- filter() handles selecting items that meet a condition.
- reduce() handles combining items into a final result.

A normal loop can always perform these tasks. The best choice depends entirely on team readability choices and context.

### Q2. What is the difference between n and s in PDB?
- n (next) executes the current line of code and steps over functions, jumping directly to the next sequential script block.
- s (step) forces PDB to step inside any active execution frame (like a function or lambda declaration) on that line to see how it operates inside.

### Q3. Why does PDB step into the lambda function multiple times during reduce() operations?
*My understanding:*
Because reduce() works iteratively through an array. When using s (step), PDB intercepts the inner logic every time the lambda function triggers. Since reduce() loops over elements behind the scenes to combine them sequentially, PDB steps inside the lambda once for every item pair until a single value is returned
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/4b3e36a5-de3b-4dee-b404-e0f663081a7a" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/6df95b2b-44b4-4a2f-80e4-93ea4cb8cf91" />

