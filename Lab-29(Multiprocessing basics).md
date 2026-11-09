Lab 29: Multiprocessing Basics

Objectives

1. Understand the basics of multiprocessing in Python.
2. Learn to create and manage multiple processes.
3. Differentiate between processes and threads, especially regarding memory sharing.

1. What Is Multiprocessing?

Multiprocessing is a Python technique that allows a program to run multiple processes. Each process can execute its own task independently.

Processes can run on separate CPU cores when the system and workload allow it.

Example: A program can use separate processes to perform multiple independent calculations.

2. Important Concepts

"multiprocessing"

A Python module used to create and manage processes.

import multiprocessing

"Process()"

Creates a process object.

p = multiprocessing.Process(target=task)

- "target=task" specifies the function the child process will execute.
- Use "target=task", not "target=task()", to pass the function without calling it immediately.

"start()"

Starts the child process.

p.start()

"join()"

Waits for the child process to finish.

p.join()

"args"

Passes arguments to the target function.

p = multiprocessing.Process(target=task, args=("A",))

The comma in "("A",)" makes it a single-element tuple.

Main Guard

if _name_ == "_main_":

Protects the program's entry point. It is particularly important for multiprocessing on platforms that use the "spawn" start method, including Windows.

3. Creating a Child Process

import multiprocessing

def task():
    print("Hello from the child process!")

if _name_ == "_main_":
    p = multiprocessing.Process(target=task)
    p.start()
    p.join()

    print("Main process finished!")

Expected Output

Hello from the child process!
Main process finished!

The main process waits for the child to finish before printing its final message.

4. Creating Multiple Processes

import multiprocessing

def task(name):
    print(f"Hello from process {name}!")

if _name_ == "_main_":
    p1 = multiprocessing.Process(target=task, args=("A",))
    p2 = multiprocessing.Process(target=task, args=("B",))

    p1.start()
    p2.start()

    p1.join()
    p2.join()

    print("Both processes finished!")

Expected Output

Hello from process A!
Hello from process B!
Both processes finished!

The A and B messages may appear in either order because process scheduling is not guaranteed. The final message appears after both processes finish.

5. Understanding Memory Separation

Consider this example:

import multiprocessing

def change_count():
    count = 5
    print("Child process count:", count)

if _name_ == "_main_":
    count = 0

    p = multiprocessing.Process(target=change_count)
    p.start()
    p.join()

    print("Main process count:", count)

Expected Output

Child process count: 5
Main process count: 0

Explanation:

- The main process has "count = 0".
- The function creates its own local variable, "count = 5".
- The child process prints its local value.
- The main process still prints "0".

This example demonstrates local variable scope. More generally, separate processes have separate memory spaces, so changing a variable in one process does not automatically update the corresponding variable in another process.

To exchange data between processes, Python provides mechanisms such as "multiprocessing.Queue" and shared memory.

6. Processes vs. Threads

Feature| Multiprocessing| Multithreading
Execution unit| Process| Thread
Memory| Separate process memory| Threads can share process memory
Communication| Often requires explicit mechanisms| Shared variables can be used
CPU parallelism| Can use multiple CPU cores| Depends on the workload and Python implementation
Common uses| CPU-intensive independent tasks| I/O tasks such as waiting for network responses

Important: Shared memory between threads can introduce race conditions when multiple threads modify the same data. Synchronization tools, such as locks, can help protect shared data.

7. Questions and Answers

Q1. What is multiprocessing?

Multiprocessing allows a program to run multiple processes independently.

Q2. What does "Process()" do?

It creates a process object.

Q3. What is the purpose of "target"?

It specifies the function that the child process should execute.

Q4. What does "start()" do?

It starts the process.

Q5. What does "join()" do?

It waits for the process to finish.

Q6. Why is "if _name_ == "_main_":" important?

It protects the main entry point and helps prevent unintended process creation, especially with the "spawn" method.

Q7. Why does the main process still print "count = 0"?

The child function's local variable is separate from the main process's variable.

Q8. Can threads share memory?

Yes. Threads within the same process can access shared variables.

Q9. Can processes exchange data?

Yes. They can use mechanisms such as queues, pipes, and shared memory.

Q10. Why might two process messages appear in different orders?

The operating system controls process scheduling, so the order is not guaranteed.

8. Practical Uses of Multiprocessing

- Performing CPU-intensive calculations.
- Processing independent data batches.
- Running multiple independent tasks.
- Using multiple CPU cores when appropriate.

9. Lab Summary

In this lab, I learned how to:

- Import the "multiprocessing" module.
- Create processes with "Process()".
- Specify functions with "target".
- Pass arguments using "args".
- Start processes using "start()".
- Wait for processes using "join()".
- Use the main guard.
- Understand process memory separation.
- Differentiate multiprocessing from multithreading.

10. Key Takeaway

Multiprocessing uses separate processes that generally have separate memory spaces. Multithreading uses multiple threads within one process, allowing them to share memory. The appropriate approach depends on the task, performance needs, and data-sharing requirements.

Lab 29 Status: Completed
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/f622298d-64b5-4606-bd1f-6f0ccfb7de10" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/0055ab02-d5f1-45f0-871b-4e6589aa45de" />

