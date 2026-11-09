Python Deep Dive – Lab 36: Collections Module ("deque" & "Counter")

1. Lab Objectives

- Understand Python's "collections" module.
- Learn how to use "deque" for efficient operations at both ends.
- Learn how to use "Counter" to count repeated items.
- Practise these tools with real Python code.

2. What is the Collections Module?

Python's "collections" module provides specialised container data types that make working with data easier and more efficient.

Two useful tools are:

- "deque"
- "Counter"

---

3. Deque – Double-Ended Queue

A "deque" (pronounced "deck") is a data structure that allows us to add and remove elements from both ends.

Import deque

from collections import deque

Create a deque

students = deque(["Ali", "Sara", "Ahmed"])
print(students)

Output:

deque(['Ali', 'Sara', 'Ahmed'])

Important deque methods

Method| Purpose
"append()"| Adds an item to the right end
"appendleft()"| Adds an item to the left end
"pop()"| Removes an item from the right end
"popleft()"| Removes an item from the left end

Practical Example

from collections import deque

students = deque(["Ali", "Sara", "Ahmed"])

students.append("Zain")
students.appendleft("Hamza")

students.popleft()
students.pop()

print(students)

Output:

deque(['Ali', 'Sara', 'Ahmed'])

How deque works

1. Initially: Ali, Sara, Ahmed
2. "append("Zain")": Adds Zain to the right.
3. "appendleft("Hamza")": Adds Hamza to the left.
4. "popleft()": Removes Hamza.
5. "pop()": Removes Zain.

Result: The original three students remain.

Why use deque instead of a list?

A deque is especially useful when we frequently add or remove elements from the beginning and end.

- Deque operations at either end are approximately O(1).
- Removing the first element from a list using "pop(0)" requires shifting the remaining elements and takes O(n).

Real-world applications:

- Task queues
- Browser history
- Scheduling systems
- Managing incoming and outgoing data

---

4. Counter – Counting Elements

"Counter" is another tool from the collections module.

It counts how many times each item appears in a collection.

Import Counter

from collections import Counter

Create a Counter

students = Counter(["Ali", "Sara", "Ali", "Ahmed", "Sara", "Ali"])

print(students)

Output:

Counter({'Ali': 3, 'Sara': 2, 'Ahmed': 1})

Count a specific item

print(students["Ali"])

Output:

3

This tells us that Ali appears three times.

Display all items by frequency

print(students.most_common())

Output:

[('Ali', 3), ('Sara', 2), ('Ahmed', 1)]

Display only the top two items

print(students.most_common(2))

Output:

[('Ali', 3), ('Sara', 2)]

Understanding most_common()

- "most_common()" returns all items ordered by frequency.
- "most_common(1)" returns only the most frequent item.
- "most_common(2)" returns the top two items.

---

5. Practical Understanding Challenge

Consider this code:

from collections import Counter

votes = Counter(["A", "B", "A", "C", "A", "B"])

print(votes.most_common(1))

Output:

[('A', 3)]

Explanation:

- A received 3 votes.
- B received 2 votes.
- C received 1 vote.

Therefore, A is the most frequent item.

---

6. Deque vs Counter

Feature| Deque| Counter
Main purpose| Manage elements at both ends| Count repeated elements
Creates| Double-ended queue| Frequency dictionary
Important methods| "append()", "pop()", "popleft()"| "most_common()"
Common use| Queues and scheduling| Voting and frequency analysis

---

7. Interview Questions

Q1. What is the collections module?

A: It provides specialised container data types that extend Python's built-in collections.

Q2. What is deque?

A: Deque is a double-ended queue that allows efficient insertion and removal from both ends.

Q3. What is the difference between "pop()" and "popleft()"?

A: "pop()" removes from the right, while "popleft()" removes from the left.

Q4. What is Counter?

A: Counter is a dictionary-like class that counts the frequency of hashable objects.

Q5. What does "most_common()" do?

A: It returns elements ordered by their frequency, from highest to lowest.

Q6. Why use deque instead of a list for operations at both ends?

A: Deque provides approximately O(1) operations at both ends, whereas inserting or removing at the beginning of a list takes O(n).

---

8. What I Learned

- How to import specialised tools from Python's collections module.
- How to create and manipulate a deque.
- How to add and remove elements from both ends.
- How to count repeated items using Counter.
- How to retrieve individual counts.
- How to use "most_common()" to find frequently occurring items.
- How to distinguish between deque and Counter.

Lab Status

Completed: Deque and Counter syntax practice, practical coding, and output verification.

Next step: Continue to Python Deep Dive Lab 37.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/dae229ff-3bfd-4224-a27a-558f83ca7523" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/386a65c3-7765-4697-a346-3b82cca3e5d3" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b23379b9-f75a-4961-ae28-bfb1dc1ec990" />


