Lab 28 — Multithreading Basics

1. Objective

Learn how to create and run multiple threads in Python, understand shared variables, identify race conditions, and use locks to protect shared data.

2. Key Definitions

- Thread: A worker that performs a task within a program.
- "threading": A Python module used to work with threads.
- "Thread()": Creates a new thread.
- "target": Specifies the function a thread will execute.
- ".start()": Starts the thread.
- ".join()": Waits for a thread to finish.
- Shared variable: A variable that multiple threads can access.
- "count": A variable used to store a number.
- "global": Allows a function to modify a global variable.
- Race condition: A problem that can occur when threads access or modify shared data in an unsafe way.
- "threading.Lock()": Creates a lock to control access to shared resources.
- "with lock:": Protects a section of code so only one thread at a time can execute that section using the same lock.

3. Practical 1 — Creating Two Threads

import threading

def worker1():
    print("Ali is working")

def worker2():
    print("Sara is working")

t1 = threading.Thread(target=worker1)
t2 = threading.Thread(target=worker2)

t1.start()
t2.start()

t1.join()
t2.join()

print("Both workers finished")

What I Learned

- Each thread runs its assigned function.
- ".start()" begins the thread.
- ".join()" waits for that thread to finish.
- The workers' output order can vary.
- The final message appears after both threads finish.

4. Practical 2 — Reading a Shared Variable

import threading

count = 0

def show_count():
    print(count)

t1 = threading.Thread(target=show_count)
t2 = threading.Thread(target=show_count)

t1.start()
t2.start()

t1.join()
t2.join()

Expected Output

0
0

What I Learned

Both threads can access the same global variable. Since neither thread changes it, both print "0".

5. Practical 3 — Incrementing a Shared Variable

import threading

count = 0

def increase():
    global count
    count = count + 1
    print(count)

t1 = threading.Thread(target=increase)
t2 = threading.Thread(target=increase)

t1.start()
t2.start()

t1.join()
t2.join()

print("Final count:", count)

Expected Result

Final count: 2

The individual printed values may vary in order or, in unsafe concurrent code, may not reliably show every update.

What I Learned

- "global count" allows the function to modify the global variable.
- "count = count + 1" increases the value by one.
- Two successful increments should produce a final count of "2".
- A correct result in one run does not prove that concurrent updates are always safe.

6. Practical 4 — Using a Lock

import threading

count = 0
lock = threading.Lock()

def increase():
    global count

    with lock:
        count = count + 1
        print("Count:", count)

t1 = threading.Thread(target=increase)
t2 = threading.Thread(target=increase)

t1.start()
t2.start()

t1.join()
t2.join()

print("Final count:", count)

Expected Output

Count: 1
Count: 2
Final count: 2

The order of the two "Count" messages can vary, but the lock protects the increment and print section.

What I Learned

- "threading.Lock()" creates a lock.
- "with lock:" protects the code inside it.
- If one thread holds the lock, another thread using the same lock must wait.
- The lock is released automatically when execution leaves the "with" block, including when an exception occurs.
- Locks are useful when multiple threads access shared data that needs protection.

7. Challenges and Mistakes

- Learned that thread output order is not guaranteed.
- Learned that ".start()" starts a thread, while ".join()" waits for it.
- Learned that changing a shared variable requires care.
- Learned that a race condition may not appear in every execution.
- Learned that a lock helps protect shared data, but should only be used where needed.

8. Real-World Cybersecurity Connection

A security application might use separate threads to process login events and check suspicious IP addresses.

If multiple threads update the same report or shared counter, a lock may help prevent conflicting updates. Separate tasks that do not share mutable data may not need a lock.

9. Final Summary

In this lab, I practised creating threads, running functions concurrently, waiting for threads to finish, sharing variables, incrementing a counter, understanding race conditions, and protecting shared data with a lock.

Main takeaway: Threads allow multiple tasks to make progress concurrently, while locks help coordinate safe access to shared resources.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/cc1e9510-5f73-4ec1-a6c3-02daf8e51ead" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/934ef1de-8fc6-42d7-8d02-08145e3e9779" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/8010bea2-c147-402a-9709-42342ffafc33" />


