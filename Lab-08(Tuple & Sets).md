🐍 Python Deep Dive — Lab 8

Tuples & Sets

📅 Lab 8

In this lab, I learned about Tuples and Sets in Python. I focused on understanding their properties, differences, and practical uses through hands-on examples.

---

🎯 Objectives

By the end of this lab, I learned how to:

1. Understand the properties and usage of tuples in Python.
2. Understand the properties and usage of sets in Python.
3. Manipulate tuples and sets with practical examples.
4. Understand the differences between lists, tuples, and sets.

---

1️⃣ Tuples

A tuple is a collection of items that is:

- Ordered
- Indexed
- Allows duplicate values
- Immutable (cannot be changed after creation)

Tuples use round brackets "()".

Example

days = ("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")

print(days)
print(days[0])
print(days[2])
print(days[-1])

Output

('Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday')
Monday
Wednesday
Friday

---

🔢 Negative Indexing

Negative indexes allow us to access items from the end of a tuple.

days[-1]

Returns the last item.

days[-2]

Returns the second-last item.

---

🔒 Tuple Immutability

Tuples cannot be directly modified.

days[1] = "Friday"

This produces:

TypeError: 'tuple' object does not support item assignment

Tuples also don't have methods such as ".append()" because new items cannot be added directly.

---

📏 Tuple Length & Membership

days = ("monday", "tuesday", "wednesday", "thursday", "friday")

print(len(days))
print("monday" in days)
print("sunday" in days)

Output:

5
True
False

"len()" counts the number of items, while "in" checks whether an item exists.

---

🔢 Tuple Methods

"count()"

Counts how many times an item appears.

numbers = (10, 20, 10, 30, 10, 40)

print(numbers.count(10))

Output:

3

"index()"

Returns the index of the first occurrence of an item.

print(numbers.index(30))

Output:

3

---

2️⃣ Sets

A set is a collection that:

- Does not keep a reliable positional order
- Does not allow duplicate values
- Can be changed
- Uses curly brackets "{}"

Example

fruits = {"apple", "banana", "orange", "apple", "banana"}

print(fruits)

Python automatically removes duplicate values.

The order of items may vary because sets are unordered.

---

➕ Adding Items to a Set

Sets use ".add()" to add an item.

fruits = {"apple", "banana", "orange"}

fruits.add("mango")

print(fruits)

---

❌ Removing Items from a Set

"remove()"

fruits.remove("banana")

If the item does not exist, ".remove()" raises a "KeyError".

"discard()"

fruits.discard("mango")

If the item does not exist, ".discard()" does nothing and does not produce an error.

---

3️⃣ Set Operations

I practiced the main set operations using two groups of students.

python_students = {"Ali", "Sara", "Ahmed"}
cyber_students = {"Sara", "Zain", "Ahmed"}

🔗 Union

"union()" combines items from both sets and removes duplicates.

all_students = python_students.union(cyber_students)

print(all_students)

Result:

{"Ali", "Sara", "Ahmed", "Zain"}

The order may be different when printed.

---

🤝 Intersection

"intersection()" gives the items that exist in both sets.

common_students = python_students.intersection(cyber_students)

print(common_students)

Result:

{"Sara", "Ahmed"}

---

➖ Difference

"difference()" gives the items that are in the first set but not the second.

only_python = python_students.difference(cyber_students)

print(only_python)

Result:

{"Ali"}

The operation is directional:

cyber_students.difference(python_students)

would give:

{"Zain"}

---

🔀 Symmetric Difference

"symmetric_difference()" gives the items that are in one set or the other, but not both.

result = python_students.symmetric_difference(cyber_students)

print(result)

Result:

{"Ali", "Zain"}

Sara and Ahmed are excluded because they appear in both sets.

---

📊 List vs Tuple vs Set

Feature| List| Tuple| Set
Brackets| "[]"| "()"| "{}"
Ordered| ✅| ✅| ❌
Indexed| ✅| ✅| ❌
Duplicates| ✅| ✅| ❌
Changeable| ✅| ❌| ✅
Add items| ".append()"| ❌| ".add()"
Main use| Changing collections| Fixed collections| Unique items

---

🔐 Cybersecurity Connection

Tuples can be useful when storing fixed information that should not accidentally change.

For example:

http_methods = ("GET", "POST", "PUT", "DELETE")

A set can be useful when we need unique values, such as removing duplicate usernames, IP addresses, or other collected data.

For example:

unique_ips = {"192.168.1.1", "192.168.1.2", "192.168.1.1"}

print(unique_ips)

The duplicate IP address is automatically removed.

---

🧠 What I Learned

In this lab, I learned that:

- Lists are ordered and changeable.
- Tuples are ordered but immutable.
- Sets store unique items and can be changed.
- Tuples use "()".
- Sets use "{}".
- "union()" combines sets.
- "intersection()" finds common items.
- "difference()" finds items in one set but not another.
- "symmetric_difference()" finds items that exist in only one of the two sets.
- ".add()" is used to add items to sets.
- ".remove()" and ".discard()" can remove items from sets.
- Tuples are useful when data should remain fixed.
- Sets are useful when duplicate values need to be removed.

---

✅ Lab Status

Lab 8 — Completed 🎉

Next: Lab 9
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/6234bd36-3ca6-4719-882d-c467782272de" />

