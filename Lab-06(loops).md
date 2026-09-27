Python Deep Dive — Lab 6: For & While Loops

📌 Lab Overview

In this lab, I learned how to use "for" and "while" loops in Python to repeat code efficiently.

I also learned how to control loops using loop variables, conditions, and the "break" statement.

To apply the concepts practically, I built a Limited-Attempt Login System.

---

🎯 Objectives

- Understand the basic use of "for" and "while" loops.
- Identify when to use "for" vs "while".
- Learn how to manipulate loop variables.
- Understand how loop conditions control execution.
- Learn how "break" can immediately stop a loop.
- Build a simple login system with limited attempts.

---

🔹 1. "for" Loop

A "for" loop is useful when I know how many times I want something to repeat or when I want to go through a sequence of values.

Example

for i in range(1, 6):
    print(i)

Output

1
2
3
4
5

---

🔹 2. Understanding "range()"

The basic structure is:

range(start, stop, step)

- start → where the sequence begins
- stop → where the sequence stops (the stop number is not included)
- step → how much the value changes each time

Example

for i in range(2, 11, 2):
    print(i)

Output

2
4
6
8
10

My understanding:

«Start at 2, stop before 11, and jump by 2.»

---

🔹 3. "while" Loop

A "while" loop keeps executing code while a condition is true.

Example

count = 1

while count <= 5:
    print(count)
    count = count + 1

Output

1
2
3
4
5

The important part is changing the loop variable:

count = count + 1

Without updating "count", the condition could remain true and create an infinite loop.

---

🔹 4. "for" vs "while"

"for"

I use a "for" loop when the number of repetitions or the sequence is known.

Example:

for i in range(1, 11):
    print(i)

"while"

I use a "while" loop when repetition depends on a condition.

Example:

while count > 0:
    # code

Simple way to remember

"for" → I know what I need to go through.

"while" → I keep going while something is true.

---

🔐 Mini Project: Limited-Attempt Login System

To practice the concepts from Lab 5 and Lab 6, I created a simple login system that allows the user only three attempts.

The program:

1. Starts with 3 attempts.
2. Asks for a username and password.
3. Checks whether the credentials are correct.
4. Decreases the attempt count after a failed attempt.
5. Uses "break" when the login is successful.
6. Shows a temporary lock message when all attempts are used.

Project Code

count = 3

while count > 0:
    print("Attempts left:", count)

    username = input("Enter your username: ")
    password = input("Enter your password: ")

    if username == "admin" and password == "1234":
        print("Login Successful")
        break

    elif username == "admin" and password != "1234":
        print("Incorrect Password")

    count = count - 1

if count == 0:
    print("Too many failed attempts. Account temporarily locked.")

---

🔹 Understanding "break"

The "break" statement immediately exits the loop.

In my project:

if username == "admin" and password == "1234":
    print("Login Successful")
    break

If the correct credentials are entered on the first attempt, the loop stops immediately instead of continuing through the remaining attempts.

For example:

Attempts left: 3
Login Successful

The remaining attempts are not used.

---

🔹 Understanding the Attempt Counter

The counter starts at:

count = 3

After each failed attempt:

count = count - 1

So the value changes like this:

3 → 2 → 1 → 0

The loop condition is:

while count > 0:

When "count" becomes "0", the condition becomes false and the loop ends.

---

🧪 Project Testing

Correct credentials

Attempts left: 3
Enter your username: admin
Enter your password: 1234
Login Successful

The "break" statement stops the loop immediately.

Failed attempts

Attempts left: 3
Incorrect Password

Attempts left: 2
Incorrect  Password

Attempts left: 1
Incorrect Password

Too many failed attempts. Account temporarily locked.

---

🧠 Key Learnings

- A "for" loop is useful when the sequence or number of repetitions is known.
- A "while" loop continues while its condition remains true.
- "range()" controls the values used by a "for" loop.
- The third argument of "range()" is the step.
- Loop variables can be updated during execution.
- "break" immediately exits a loop.
- A loop condition determines when a "while" loop stops.
- I learned how to combine loops with conditional statements to create a practical program.
- I practiced debugging syntax, indentation, and logic errors while building the project.

---

🔐 Cybersecurity Connection

Loops are very important in cybersecurity programming.

They can be used for tasks such as:

- Processing multiple inputs.
- Checking multiple results.
- Reading lists of data.
- Automating repetitive security tasks.
- Processing logs and records.
- Building simple security-related tools.

The limited-attempt login project helped me understand how programming logic can be used to control authentication attempts.

«Note: This project is a simple educational simulation and does not represent how real authentication systems securely handle passwords or account lockouts.»

---

✅ Lab Status

Lab 6 — Completed ✅

I successfully learned and practiced:

- "for" loops
- "while" loops
- "range()"
- Loop variables
- Loop conditions
- "break"
- Limited-attempt logic
- Practical loop-based programming
- Basic debugging and indentation
- <img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/7124a45f-96f2-47fe-b97f-2422a2abe210" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/0ab926e1-f7a7-49e2-9c36-1e46efbc1d74" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/611e46c1-b9a1-4e51-b55d-7cf6128e2110" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/f98dd5eb-22d7-4fda-8663-ae112f304aab" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/11ee1043-fde3-497a-97df-f363b8cc36fe" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/7a4e9b41-85f1-46cd-9664-3e0437f3eb07" />





