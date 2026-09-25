Lab 4: Arithmetic & Expressions

Objectives

- Understand and apply basic arithmetic operations using Python.
- Differentiate between integer division and float division.
- Write and execute scripts to perform arithmetic expressions.

What I Learned

In this lab, I learned how Python performs basic arithmetic calculations using different operators.

Arithmetic Operators

Operator| Meaning| Example
"+"| Addition| "10 + 3 = 13"
"-"| Subtraction| "10 - 3 = 7"
"*"| Multiplication| "10 * 3 = 30"
"/"| Normal/float division| "10 / 3 = 3.333..."
"//"| Integer/floor division| "10 // 3 = 3"
"%"| Remainder| "10 % 3 = 1"
"*"| Power| "10 * 3 = 1000"

Integer Division vs Normal Division

The "/" operator gives the normal division result and returns a float.

10 / 3

Output:

3.3333333333333335

The "//" operator gives the floor/integer division result.

10 // 3

Output:

3

The "%" operator gives the remainder.

10 % 3

Output:

1

Example

For:

17 ÷ 5

Python gives:

17 // 5 = 3
17 % 5 = 2
17 / 5 = 3.4

This means 5 fits into 17 three complete times, with 2 left over.

Operator Precedence

Python follows an order when evaluating expressions:

1. Brackets "()"
2. Power "**"
3. Multiplication, division, integer division, and remainder "* / // %"
4. Addition and subtraction "+ -"

Examples:

print(10 + 5 * 2)
print((10 + 5) * 2)
print(20 - 6 / 2)
print(2 ** 3 + 4)

Output:

20
30
17.0
12

Practical Script

num1 = 20
num2 = 89

print("Number 1:", num1)
print("Number 2:", num2)

print("Addition:", num1 + num2)
print("Subtraction:", num1 - num2)
print("Multiplication:", num1 * num2)
print("Division:", num1 / num2)
print("Integer Division:", num1 // num2)
print("Remainder:", num1 % num2)

Key Takeaway

"/" gives the normal division result, "//" gives the whole-number quotient, "%" gives the remainder, and "**" calculates a power.

Lab Status

Lab 4 completed successfully. ✅
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/7186ca9c-cda1-42e5-beb8-f74e0ea92e7c" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/35aed4e9-7375-405c-a32d-a64424e6a4a4" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/f845e036-3a98-46ed-9b62-f046da4dddd0" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/7e191815-31e2-418d-aaeb-37bc4b9bb25a" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b8099749-f340-4372-b231-cbe2f817e7b7" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/e68b6f3c-8d44-4de2-afc0-44a036b55129" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/d3591dff-935e-4392-8328-183b095f5909" />






