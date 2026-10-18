Lab 17: OOP — Defining Classes

Objectives

- Understand the basics of Object-Oriented Programming (OOP).
- Differentiate between class attributes and instance attributes.
- Create and manipulate objects in Python.

Concepts Learned

1. Object-Oriented Programming (OOP)

OOP is a programming approach that organizes code using classes and objects.

2. Classes

A class is a blueprint used to create objects.

Example:

class Student:
    school = "ABC School"

3. Objects

An object is an individual instance created from a class.

Example:

student1 = Student()

4. Class Attributes

Class attributes belong to the class and can be accessed through its objects.

Example:

school = "ABC School"

5. Instance Attributes

Instance attributes store information specific to each object.

Example:

self.name = name
self.age = age

6. The "_init_()" Method

The "_init_()" method initializes an object's attributes when a new object is created.

7. The "self" Parameter

"self" refers to the current object.

Practical Code

class Student:
    school = "ABC School"

    def _init_(self, name, age):
        self.name = name
        self.age = age


student1 = Student("Ali", 18)
student2 = Student("Sara", 17)

print(student1.name)
print(student2.name)

print(student1.school)
print(student2.school)

Expected Output

Ali
Sara
ABC School
ABC School

Dry Run and Practice

- Created two objects using - the same class.
- Observed how "_init_()" assigns values to each object.
- Accessed instance attributes using dot notation.
- Practised changing an object's age.
- Explored how an object-specific attribute can differ from a class attribute.

Key Takeaways

- A class is a blueprint for creating objects.
- Objects created from the same class can have different instance attributes.
- Class attributes can be accessed through the class or its objects.
- Assigning an attribute to one object does not automatically change other objects.
- Dry running helps track program execution and understand how values change.

Result

Successfully completed Lab 17 and verified the expected output in the terminal
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/f74e6590-fc3a-4a6a-b1c2-e59860d2258a" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/d86eb7e3-0695-4149-b212-0a0631c580cc" />

