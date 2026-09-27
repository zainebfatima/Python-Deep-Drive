Python Deep Dive — Lab 7: Lists & List Methods

📌 Lab Overview

In this lab, I learned how to work with lists in Python.

I practiced creating lists, accessing items using indexes, modifying existing items, adding and removing items, sorting lists, and iterating through lists using a "for" loop.

I also connected the list concepts with the "for" loop concepts learned in Lab 6.

---

🎯 Objectives

- Understand the basic concept of lists in Python.
- Learn how to create, modify, and manage lists using built-in list methods.
- Implement common operations such as appending, removing, sorting, and iterating over lists.
- Understand list indexing.
- Practice combining lists with "for" loops.

---

🔹 1. Creating a List

A list allows multiple values to be stored inside one variable.

Example:

fruits = ["apple", "banananaa", "orange", "lemon", "strawberry"]

Instead of creating separate variables for every fruit, I can store them together inside one list.

---

🔹 2. List Indexing

Python uses indexes to access individual items in a list.

Important point:

«Python starts counting indexes from 0.»

Example:

print(fruits[0])

Output:

apple

Example:

print(fruits[4])

Output:

strawberry

Index structure:

0 → apple
1 → banananaa
2 → orange
3 → lemon
4 → strawberry

---

🔹 3. Modifying a List Item

I can change an existing item by using its index.

Example:

fruits[3] = "watermelon"

print(fruits[3])

Output:

watermelon

This changes the item at index "3" from ""lemon"" to ""watermelon"".

---

🔹 4. Adding Items with ".append()"

The ".append()" method adds a new item to the end of a list.

Example:

fruits.append("mango")

print(fruits)

The ""mango"" item is added to the end of the list.

---

🔹 5. Removing Items with ".remove()"

The ".remove()" method removes a specific value from the list.

Example:

fruits.remove("orange")

print(fruits)

This removes ""orange"" from the list.

---

🔹 6. Removing Items with ".pop()"

The ".pop()" method can remove an item using its index.

If no index is provided, it removes the last item.

Remove the last item:

fruits.pop()

Remove an item using its index:

fruits.pop(1)

For example, if ""banananaa"" is at index "1", then:

fruits.pop(1)

removes ""banananaa"".

Difference

.remove() → removes a specific value
.pop()    → removes an item using its position

---

🔹 7. Sorting a List

The ".sort()" method arranges list items.

Example:

fruits = ["strawberry", "apple", "watermelon", "mango"]

fruits.sort()

print(fruits)

Output:

['apple', 'mango', 'strawberry', 'watermelon']

For strings, ".sort()" arranged the items alphabetically.

---

🔹 8. Iterating Through a List

I learned that a "for" loop can directly go through each item in a list.

Example:

fruits = ["apple", "mango", "strawberry"]

for fruit in fruits:
    print(fruit)

Output:

apple
mango
strawberry

Important Understanding

In:

for fruit in fruits:

"fruits" is the whole list.

"fruit" is a temporary variable representing one item at a time.

Python does not actually understand that ""fruit"" means a singular fruit. The variable name is chosen by the programmer.

For example, this also works:

for i in fruits:
    print(i)

The variable could be called "i", "x", "item", or something else.

Meaningful variable names are mainly useful for humans reading the code.

---

🧠 Key Learnings

- A list stores multiple values in one variable.
- Python list indexes start from "0".
- Individual list items can be accessed using indexes.
- List items can be modified using their indexes.
- ".append()" adds an item to the end of a list.
- ".remove()" removes a specific value.
- ".pop()" removes an item by index or removes the last item when no index is given.
- ".sort()" arranges list items.
- A "for" loop can iterate directly through a list.
- The variable used in a "for" loop is chosen - by the programmer.
- Python cares about the code structure, not the English meaning of variable names.

---

🔗 Connection With Previous Labs

Lab 7 connected directly with concepts from Lab 6.

In Lab 6, I learned:

for i in range(...)

In Lab 7, I learned that I can use a "for" loop directly with a list:

for fruit in fruits:
    print(fruit)

This makes it easier to process multiple pieces of data.

---

🔐 Cybersecurity Connection

Lists are very useful in cybersecurity because security programs often need to work with collections of data.

Examples include:

- Lists of usernames
- Lists of IP addresses
- Lists of domains
- Lists of URLs
- Lists of file names
- Lists of security scan results

Later, Python lists can be combined with loops and conditions to process this type of data automatically.

---

📝 Practice Completed

During this lab, I practiced:

- Creating a list ✅
- Accessing list items ✅
- Understanding indexes ✅
- Modifying list items ✅
- Adding items with ".append()" ✅
- Removing items with ".remove()" ✅
- Removing items with ".pop()" ✅
- Sorting lists with ".sort()" ✅
- Iterating through lists with "for" loops ✅

---

🚧 Next Step

Continue practicing lists by combining them with:

- "for" loops
- "if" statements
- Conditions
- More list operations

This will connect the concepts from Lab 5, Lab 6, and Lab 7.

Core list concepts and common list methods practiced successfully. 🚀

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/1839d178-650e-48da-9086-4440d894b8c0" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/42fdc92e-a954-44f7-83c3-367d7d62ffe1" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b7941807-cbce-4953-b7ed-3b5eb7021492" />



- 
