Lab 13: Handling ExceptionsLab 13: Handling Exceptions

Objectives

- Understand the fundamentals of exception handling in Python.
- Learn how to use "try", "except", and "finally" blocks.
- Practice handling errors in Python programs.
- Identify and manage different types of exceptions.

What is Exception Handling?

An exception is an error that occurs while a Python program is running.

Exception handling allows us to handle errors without allowing the program to crash unexpectedly.

The main keywords are:

- "try" — contains code that might cause an error.
- "except" — handles the error if it occurs.
- "finally" — runs whether an error occurs or not.

1. Basic try and except

try:
    number = 10 / 0
    print(number)

except:
    print("Something went wrong!")

Output:

Something went wrong!

The division by zero caused an error, so Python moved to the "except" block.

2. Handling ValueError

try:
    number = int(input("Enter a number: "))
    print(number)

except ValueError:
    print("Please enter a valid number!")

When "25" was entered, the program ran normally.

When "hello" was entered, Python produced a "ValueError", which was handled by the "except" block.

3. Using finally

try:
    number = int(input("Enter a number: "))
    print(number)

except ValueError:
    print("Please enter a valid number!")

finally:
    print("Program finished.")

The "finally" block ran whether the input was valid or invalid.

"finally" is useful for cleanup tasks such as closing files or connections.

4. Exception Handling with Addition

try:
    num1 = int(input("Enter first number: "))
    num2 = int(input("Enter second number: "))

    result = num1 + num2
    print("Answer:", result)

except ValueError:
    print("Please enter numbers only.")

finally:
    print("Calculation attempt finished.")

Valid numbers produced the answer, while invalid input was handled by "except".

5. Handling ZeroDivisionError

try:
    number = int(input("Enter a number: "))
    result = 100 / number
    print("Result:", result)

except ValueError:
    print("Please enter numbers only.")

except ZeroDivisionError:
    print("The number cannot be zero.")

Different errors can have different "except" blocks.

- "ValueError" → invalid value, such as "hello" when an integer is expected.
- "ZeroDivisionError" → attempting to divide by zero.

6. Handling FileNotFoundError

try:
    file = open("missing.txt", "r")
    print(file.read())

except FileNotFoundError:
    print("The file was not found.")

If the requested file does not exist, "FileNotFoundError" is handled instead of allowing the program to stop with an unhandled error.

7. Handling IndexError

try:
    names = ["Ali", "Sara", "Zain"]
    print(names[5])

except IndexError:
    print("That position does not exist.")

The list only has indexes "0", "1", and "2", so accessing index "5" causes an "IndexError".

Exception Types Practiced

Exception| Example
"ValueError"| Converting ""hello"" to an integer
"ZeroDivisionError"| Dividing a number by zero
"FileNotFoundError"| Opening a file that does not exist
"IndexError"| Accessing a list position that does not exist

Key Takeaways

- "try" is used for code that might cause an error.
- "except" handles an error.
- Multiple "except" blocks can handle different types of errors.
- "finally" runs whether an error occurs or not.
- Exception handling makes programs more reliable and prevents unexpected crashes.
- Different exception types help us handle different problems appropriately.

Practical Understanding

Exception handling is useful in real-world Python programs, including cybersecurity scripts. For example, a script may need to read a file, process user input, connect to a resource, or work with lists and data. If something goes wrong, exception handling allows the program to respond appropriately instead of stopping unexpectedly.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/bb91bf9e-5498-4257-a443-2b4382d46669" />

