Lab 32 — Logging with Python's Logging Module

Date: November 2, 2026
Topic: Python Logging Module
Status: Completed ✅

---

1. Objectives

- Understand the importance of logging in software development.
- Learn to use Python's "logging" module.
- Configure logging levels and formats.
- Implement logging in a Python application to track different severity levels.

2. What is Logging?

Logging is a way for a Python application to record events that happen while it is running.

It helps developers understand:

- What the application is doing.
- When an event occurred.
- Whether something unexpected happened.
- Where an error occurred.

Real-world example:

Imagine a security system that records:

- Application started.
- User logged in successfully.
- Invalid login attempt.
- An error occurred.

These records help developers monitor applications and investigate problems.

3. Logging vs print()

print()| logging
Displays messages| Records application events
Mainly used for simple output| Used for application monitoring and debugging
No built-in severity levels| Provides different severity levels
No automatic timestamps| Can include timestamps and other details

4. Five Logging Levels

Python provides five commonly used logging levels.

Level| Purpose
DEBUG| Detailed information for debugging
INFO| Records normal application activities
WARNING| Indicates something unexpected
ERROR| Indicates an operation has failed
CRITICAL| Indicates a serious problem

Order of severity:

"DEBUG → INFO → WARNING → ERROR → CRITICAL"

Example

import logging

logging.basicConfig(level=logging.DEBUG)

logging.debug("This is a debug message")
logging.info("Application started")
logging.warning("Something unexpected happened")
logging.error("An error occurred")
logging.critical("A serious problem occurred")

Important concept: Logging threshold

The logging level determines which messages are displayed or recorded.

For example:

logging.basicConfig(level=logging.ERROR)

This displays:

- ERROR
- CRITICAL

It filters out DEBUG, INFO and WARNING.

5. Configuring Logging with basicConfig()

The "basicConfig()" function configures the logging system.

Example:

import logging

logging.basicConfig(
    level=logging.DEBUG,
    format="%(asctime)s - %(levelname)s - %(message)s"
)

logging.info("Application started")
logging.warning("Check your input")
logging.error("Something went wrong")

Understanding the format

- "%(asctime)s" — Date and time.
- "%(levelname)s" — Logging severity level.
- "%(message)s" — Actual log message.

This makes logs easier to read and understand.

6. Saving Logs into a File

Instead of displaying logs only in the terminal, we can save them into a separate file.

Example:

import logging

logging.basicConfig(
    filename="app.log",
    level=logging.DEBUG,
    format="%(asctime)s - %(levelname)s - %(message)s"
)

logging.info("Application started")
logging.warning("Something unexpected happened")
logging.error("An error occurred")

Python creates "app.log" and stores the logging messages there.

Useful terminal commands

ls

Lists files in the current directory.

cat app.log

Displays saved logging messages.

Important distinction:

- "cat challenge.py" — Displays Python source code.
- "cat security.log" — Displays saved logging messages.

7. File Modes: Append vs Write

Python logging supports different file modes.

Mode| Behaviour
"a"| Appends new messages without deleting previous logs
"w"| Overwrites the existing file

Example:

logging.basicConfig(
    filename="app.log",
    filemode="a",
    level=logging.DEBUG
)

The default file mode is "a".

To overwrite previous logs:

logging.basicConfig(
    filename="app.log",
    filemode="w",
    level=logging.DEBUG
)

8. Logging Exceptions

Python also provides "logging.exception()".

It records an error message along with traceback information.

A traceback helps developers understand where an error occurred.

Example

import logging

logging.basicConfig(
    filename="security.log",
    level=logging.DEBUG
)

try:
    result = 10 / 0

except ZeroDivisionError:
    logging.exception("Something went wrong")

The log contains:

- ERROR logging level.
- Custom error message.
- Exception details.
- Traceback information.

Difference between error() and exception()

logging.error("An error occurred")

Records an error message.

logging.exception("An error occurred")

Records an error message along with traceback information.

Important: "logging.exception()" is generally used inside an "except" block.

9. Practical Application — Login Checker

Created a small application to practise logging user activity.

import logging

logging.basicConfig(
    filename="security.log",
    level=logging.DEBUG,
    format="%(levelname)s: %(message)s"
)

username = "sara"
password = "2345"

logging.info("Login process started")

if username == "sara" and password == "2345":
    logging.info("Login successful")
else:
    logging.warning("Invalid login attempt")

logging.info("Application finished")

Application behaviour

- Records when the login process starts.
- Checks the username and password.
- Records successful login attempts.
- Records unsuccessful login attempts.
- Records when the application finishes.

Note: Hardcoded credentials are used only for this learning demonstration. Real applications should use secure authentication and password storage.

10. Final Mini-Project — Complete Logging Practice

Created "challenge.py" to combine the concepts learned in this lab.

import logging

logging.basicConfig(
    filename="security.log",
    level=logging.DEBUG,
    format="%(levelname)s: %(message)s"
)

logging.debug("This is a debug message")

username = "sara"
password = "2345"

logging.info("Login process started")

if username == "sara" and password == "2345":
    logging.info("Login successful")
else:
    logging.warning("Invalid login attempt")

logging.info("Application finished")

try:
    number = int("hello")

except ValueError:
    logging.exception("Invalid number")

logging.error("An error occurred")
logging.critical("This is a serious problem")

Verification

Executed the application:

python challenge.py

Checked the log file:

cat security.log

Result: Successfully executed the application and verified the saved logging messages, including all five severity levels and exception traceback information.

11. Questions & Answers

Q1. What is logging?

Logging records events and activities that happen while an application runs.

Q2. What is the difference between print() and logging?

"print()" displays simple output, whereas logging provides structured messages with severity levels and optional timestamps.

Q3. How many commonly used logging levels does Python provide?

Five: DEBUG, INFO, WARNING, ERROR and CRITICAL.

Q4. What happens when we configure logging with level=logging.ERROR?

Only ERROR and CRITICAL messages are recorded.

Q5. What does basicConfig() do?
It configures the logging system, including the logging level, format and output destination.

Q6. What does filename="security.log" do?

It saves logging messages into the specified file.

Q7. What is the difference between filemode="a" and filemode="w"?

"a" appends new messages, while "w" overwrites existing content.

Q8. What is logging.exception()?

It records an error message along with traceback information.

Q9. Why is traceback useful?

It helps developers identify where and why an exception occurred.

Q10. What is the purpose of logging.DEBUG?

It provides detailed information useful for debugging an application.

12. Mistakes & Lessons Learned

Mistake 1: Reading the wrong file

Initially, I used "cat" on my Python file instead of my logging file.

Solution: Used the correct command:

cat security.log

Lesson: Always verify the filename before assuming something is wrong with the code.

Mistake 2: Understanding file modes

Initially, I needed clarification about appending and overwriting log files.

Lesson: "a" preserves previous logs, whereas "w" overwrites them.

Lesson 3: Understanding logging.exception()

Learned that exception logging provides traceback information, which makes debugging easier.

13. Key Takeaways

- Logging helps monitor application behaviour.
- Python provides five commonly used logging levels.
- "basicConfig()" configures logging.
- Custom formats make log records easier to understand.
- Logs can be saved in external files.
- File modes control whether previous logs are preserved.
- "logging.exception()" records traceback information.
- Logging is an important practice in software development and cybersecurity.

---

Final Status: Lab 32 Completed Successfully ✅

Next Lab: Lab 33 — Continue Python Deep Dive.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/64cd077b-1bfd-4913-9140-37f2c34e6e96" />
