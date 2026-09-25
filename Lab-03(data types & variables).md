Lab 3 — Data Types & Variables

Objectives

- Understand the concept of data types and variables in programming.
- Learn how to create and manipulate different data types in Python.
- Identify common Python data types such as "int", "float", "str", and "bool".
- Understand and practice implicit and explicit type casting in Python.

Concepts Learned

1. Variables

A variable is a name that refers to a value.

name = "Zaineb"
age = 18

Here:

- "name" is the variable name.
- ""Zaineb"" is the value.
- "=" is the assignment operator.

2. Common Python Data Types

Python provides different data types for different kinds of values.

name = "Zaineb"
age = 18
height = 5.2
is_student = True

Variable| Value| Data Type
"name"| ""Zaineb""| "str"
"age"| "18"| "int"
"height"| "5.2"| "float"
"is_student"| "True"| "bool"

The "type()" function can be used to identify a value's data type.

print(type(name))
print(type(age))
print(type(height))
print(type(is_student))

3. Strings vs Numbers

Values that look similar can have different data types.

age = 18
age_text = "18"

"age" is an integer, while "age_text" is a string.

Therefore:

print(age + 2)

produces:

20

while:

print(age_text + "2")

produces:

182

The second example demonstrates string concatenation.

4. Explicit Type Casting

Explicit type casting occurs when the programmer tells Python to convert a value to another type.

Example:

number_text = "25"

number = int(number_text)

print(number + 5)
print(type(number))

Output:

30
<class 'int'>

Common type conversion functions include:

int()    → integer
float()  → floating-point number
str()    → string
bool()   → Boolean

5. Implicit Type Casting

Implicit type casting occurs when Python automatically handles a compatible type conversion during an operation.

Example:

a = 10
b = 2.5

result = a + b

print(result)
print(type(result))

Output:

12.5
<class 'float'>

Python automatically handles the integer and floating-point number together, resulting in a "float".

Practical Experiments

Experiment 1 — Identifying Data Types

Tested:

name = "Zaineb"
age = 18
height = 5.2
is_student = True

Confirmed their types using "type()".

Experiment 2 — String vs Integer

Tested:

age = 18
age_text = "18"

Confirmed that:

18    → int
"18"  → str

Experiment 3 — Explicit Casting

Converted:

"25" → 25

using:

int("25")

Experiment 4 — Implicit Casting

Tested:

10 + 2.5

and confirmed that the result was:

12.5

with the type:

float

Key Takeaways

- Variables provide names for values.
- Python has different data types for different kinds of data.
- "str", "int", "float", and "bool" are fundamental Python data types.
- "type()" can be used to inspect a value's type.
- ""18"" and "18" are different data types.
- Explicit casting is performed by the programmer.
- Implicit casting can be handled automatically by Python.
- Data types affect how Python performs operations.

Lab Status

Completed and understood.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/0c19ea33-eea6-44d2-a5d2-951b8fab3eab" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/05b30d9e-bea5-4437-9291-ffe8c0e8f0e7" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/2f73c3d2-d363-4edb-8780-3193c5fc5782" />



