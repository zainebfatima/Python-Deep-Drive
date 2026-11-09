 Lab 27 — Context Managers in Python

🎯 Objectives

By the end of this lab, I learned how to:

- Understand context managers and the "with" statement.
- Understand the purpose of "_enter()" and "exit_()".
- Handle files safely using "with open()".
- Understand how context managers behave when an error occurs.
- Understand how "return True" and "return False" affect exceptions.

---

1. What Is a Context Manager?

A context manager helps manage resources by setting them up before work and cleaning them up afterward.

Simple example: Opening a file, writing data, and automatically closing the file when the work is finished.

The "with" statement is used to work with a context manager.

2. Creating Our Own Context Manager

class MyContext:
    def _enter_(self):
        print("Entering the context")
        return self

    def _exit_(self, exc_type, exc_value, traceback):
        print("Exiting the context")


with MyContext() as context:
    print("Inside the with block")

print("Program finished")

Output

Entering the context
Inside the with block
Exiting the context
Program finished

Explanation

- "class MyContext:" creates our own context manager class.
- "_enter_()" runs when the "with" block begins.
- "return self" gives the current object to the variable "context".
- The code inside the "with" block performs the required work.
- "_exit_()" runs when the block finishes, including when an exception occurs.
- "exc_type", "exc_value", and "traceback" provide information about an exception. If no exception occurs, they are "None".
- "Program finished" prints after the "with" block completes normally.

Remember: "_enter()" = start, "with" block = work, "exit_()" = cleanup.

---

3. Understanding Exceptions in "_exit_()"

class MyContext:
    def _enter_(self):
        print("Entering the context")
        return self

    def _exit_(self, exc_type, exc_value, traceback):
        print("Exiting the context")
        print("Error type:", exc_type)
        print("Error value:", exc_value)
        return False


with MyContext() as context:
    print("Inside the with block")
    result = 10 / 0

print("Program finished")

Important observations

- "10 / 0" raises a "ZeroDivisionError".
- Python calls "_exit_()" even though an exception occurs.
- "exc_type" contains the exception type.
- "exc_value" contains the error message.
- "return False" allows the exception to continue propagating.
- Because the exception is not handled, "Program finished" does not print.

"return True" vs "return False"

Return value| Behaviour
"return False"| The exception continues propagating.
"return True"| The exception is suppressed.
"return None"| The exception continues propagating; this is the default if nothing is returned.

Important: Suppressing an exception does not fix the underlying problem. For example, if "10 / 0" fails, suppressing the exception does not produce a valid result for "result".

---

4. File Context Managers

Python provides a built-in context manager for file handling.

with open("notes.txt", "w") as file:
    file.write("Hello Python!")

print("File closed:", file.closed)

Output

File closed: True

Explanation

- "open("notes.txt", "w")" opens a file in write mode.
- If the file does not exist, Python normally creates it.
- If it already exists, write mode replaces its existing contents.
- "file.write()" writes text into the file.
- When the "with" block ends, Python closes the file automatically.
- "file.closed" returns "True" when the file is closed.

Checking the file inside and outside the block

with open("notes.txt", "w") as file:
    file.write("Python Lab 27")
    print("Inside:", file.closed)

print("Outside:", file.closed)

Output:

Inside: False
Outside: True

Inside the block, the file is still open. Outside the block, it has been closed.

What happens if an error occurs?

with open("notes.txt", "w") as file:
    file.write("Hello!")
    result = 10 / 0

print("File closed:", file.closed)

The file is closed when Python leaves the "with" block, even though a "ZeroDivisionError" occurs. However, the error still appears because it has not been handled, so the final "print()" is not reached.

---

5. Reading a File

with open("students.txt", "r") as file:
    print(file.read())

- ""students.txt"" is the name of the file to read.
- ""r"" means read mode.
- "file.read()" reads the file's contents.
- The file must exist at the specified path; otherwise, Python raises "FileNotFoundError".

If the Python file and text file are in the same directory, the filename alone is usually enough.

---

6. Real-World Uses

Context managers are useful for:

1. File handling: Reading logs, writing reports, and saving scan results.
2. Database operations: Managing transactions or connections, depending on the library.
3. Network operations: Managing responses and releasing resources in supported libraries.
4. Cybersecurity automation: Processing log files and storing security scan results.
5. Resource management: Making sure resources are cleaned up even when an error occurs.

Benefits

- Automatic cleanup.
- Cleaner and more readable code.
- Less repetitive setup and cleanup code.
- Reduced risk of leaving files or other resources open.
- More reliable resource management when errors occur.

---

7. Quiz and Revision

Q1. What is the purpose of a context manager?

Answer: To manage a task or resource and help ensure proper cleanup.

Q2. Which method runs when entering a context?

Answer: "_enter_()"

Q3. Which method runs when leaving a context?

Answer: "_exit_()"

Q4. Why is "with open()" useful?

Answer: It automatically closes the file when the block ends.

Q5. What does "file.closed" return inside an active "with" block?

Answer: "False", assuming the file is still open.

Q6. What does "return False" do in "_exit_()"?

Answer: It allows an exception to continue propagating.

Q7. What does "return True" do in "_exit_()"?

Answer: It suppresses the exception, but it does not fix the underlying error.

Q8. What happens if a file is opened in ""r"" mode but does not exist?

Answer: Python raises "FileNotFoundError".

---

8. What I Learned

- A context manager manages setup and cleanup.
- The "with" statement makes context managers easy to use.
- "_enter()" starts the context and "exit_()" handles its exit.
- File context managers close files automatically, even when an exception occurs.
- Suppressing an exception is different from fixing it.
- Context managers are useful in everyday Python programming, automation, and cybersecurity tasks.

Lab 27 completed! ✅
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/40df9236-4db7-42ab-aa87-e425149f7714" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/90d65057-10c1-41cd-92ba-604d853730d8" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/f00335c5-7486-4b40-9abe-bfbd4e05989d" />


