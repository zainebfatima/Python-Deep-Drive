 Python Deep Dive — Lab 9

Dictionaries & Key Operations

📌 Lab Overview

In this lab, I learned about dictionaries in Python and how to work with key-value pairs.

I learned how dictionaries are different from lists, how to access values using keys, and how to add, update, remove, and iterate through dictionary data.

---

🎯 Objectives

- Understand the structure and use of dictionaries in Python.
- Learn how to add, update, access, and remove dictionary entries.
- Learn how to check whether a key exists.
- Explore dictionary methods for working with keys, values, and items.
- Practice iterating through dictionary data using "for" loops.
- Build a small terminal-based Student Record Manager.

---

📚 What I Learned

1. Creating a Dictionary

Dictionaries use curly brackets "{}" and store data as key-value pairs.

student = {
    "name": "Ali",
    "age": "19",
    "course": "Python"
}

Here:

- ""name"" is the key.
- ""Ali"" is the value.
- ""age"" is the key.
- ""19"" is the value.

A dictionary itself can be stored inside a variable.

---

2. Accessing Values

I can access a value by using its key:

print(student["name"])

Output:

Ali

Unlike a list, I don't need to remember a numerical index. I can use a meaningful key.

---

3. Adding a New Key-Value Pair

If a key doesn't already exist, assigning a value adds a new entry.

student["country"] = "Pakistan"

---

4. Updating a Value

If the key already exists, assigning a new value updates it.

student["age"] = "20"

The existing value is replaced.

Important rule:

Key already exists → Update the value
Key doesn't exist  → Add a new key-value pair

---

5. Removing Data with "del"

I can remove a key-value pair using "del":

del student["age"]

This removes both the key and its value.

---

6. Removing Data with ".pop()"

".pop()" also removes a key-value pair, but it can return the removed value.

removed = student.pop("course")

print(removed)

Output:

Python

This means the removed value can be stored in another variable.

---

7. Checking if a Key Exists

The "in" operator can check whether a key exists:

print("name" in student)

Output:

True

If the key doesn't exist:

print("city" in student)

Output:

False

This can help prevent errors when working with data.

---

8. Getting All Keys

The ".keys()" method gives access to all dictionary keys.

print(student.keys())

We can also loop through the keys:

for key in student.keys():
    print(key)

---

9. Getting All Values

The ".values()" method gives access to all values.

print(student.values())

We can also loop through the values:

for value in student.values():
    print(value)

---

10. Getting Keys and Values with ".items()"

The ".items()" method allows us to work with both the key and value together.

for key, value in student.items():
    print(key, value)

Example output:

name Ali
age 19
country Pakistan

---

11. Using ".get()"

".get()" is another way to access a value.

print(student.get("name"))

Output:

Ali

If the key doesn't exist, ".get()" returns "None" instead of immediately producing a "KeyError".

print(student.get("city"))

Output:

None

I can also provide a default value:

print(student.get("city", "Not available"))

Output:

Not available

---

12. Using ".update()"

".update()" can add or update multiple key-value pairs.

student.update({
    "course": "Cybersecurity",
    "city": "Lahore"
})

If a key already exists, its value is updated.

If the key doesn't exist, it is added.

---

💻 Final Terminal Project

Student Record Manager

For the final project, I created a small student record system using a dictionary.

The project combined:

- Dictionary creation
- Accessing values
- Updating values
- Adding new values
- Removing values
- ".pop()"
- Checking keys with "in"
- ".items()"
- "for" loops

Project Code

student = {
    "Name": "Ali",
    "Age": "19",
    "course": "python",
    "city": "lahore"
}

print(student["Name"])
print(student["course"])

student["course"] = "cybersecurity"
print(student["course"])

student["country"] = "Pakistan"

removed_city = student.pop("city")
print("Removed city:", removed_city)

print("city" in student)

for key, value in student.items():
    print(key, value)

Example Output

Ali
python
cybersecurity
Removed city: lahore
False
Name Ali
Age 19
course cybersecurity
country Pakistan

---

🐛 Error I Encountered

During the project, I encountered:

KeyError: 'city'

The reason was that ""city"" had already been removed using ".pop()".

When I tried to remove ""city"" again, Python couldn't find the key.

I fixed it by making sure ".pop("city")" was used only once and storing the removed value:

removed_city = student.pop("city")

This helped me understand that dictionary operations actually change the dictionary.

---

🧠 Key Takeaways

- A dictionary stores information using key-value pairs.
- Keys are used to access their corresponding values.
- Existing keys can be updated.
- New keys can be added.
- "del" and ".pop()" can remove entries.
- ".pop()" can also return the removed value.
- ".keys()" gives keys.
- ".values()" gives values.
- ".items()" gives keys and values together.
- ".get()" provides safer access to possibly missing keys.
- ".update()" can add or update multiple entries.
- Dictionaries work very well with "for" loops.

---

🚀 Practical Connection

Dictionaries are useful when working with structured information such as:

- Student records
- Employee information
- User profiles
- Configuration data
- API responses
- Cybersecurity-related data

Instead of remembering numerical indexes, I can use meaningful keys to access the information I need.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ecfcb9dc-e3a5-492e-be17-c45b6c3c39cc" />

