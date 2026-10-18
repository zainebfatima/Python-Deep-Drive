Lab 18: OOP — Inheritance Basics

Objectives

- Understand the concept of inheritance in Object-Oriented Programming (OOP).
- Extend an existing class to create a new subclass.
- Override methods in a subclass to provide extended functionality.
- Use the "super()" function to access methods or attributes in a parent class.

Concepts Learned

1. Inheritance

Inheritance allows a child class to reuse attributes and methods from a parent class.

2. Parent Class

A parent class is the original class whose features can be inherited by another class.

Example: "Person"

3. Child Class (Subclass)

A child class inherits features from a parent class and can define additional features of its own.

Example: "Student(Person)"

4. Method Overriding

Method overriding happens when a child class defines its own version of a method inherited from the parent class.

5. The "super()" Function

The "super()" function allows a child class to call methods from its parent class.

Practical Code

class Person:
    def introduce(self):
        print("Hello!")


class Student(Person):
    def introduce(self):
        super().introduce()
        print("I am a student.")


student1 = Student()
student1.introduce()

Expected Output

Hello!
I am a student.

Dry Run

1. Python defines the "Person" class and its "introduce()" method.
2. Python defines the "Student" class, which inherits from "Person".
3. The "Student" class overrides the parent's "introduce()" method.
4. Python creates the "student1" object.
5. Python calls "student1.introduce()".
6. "super().introduce()" calls the parent's method and prints "Hello!".
7. The next print statement displays "I am a student."

Key Takeaways

- Inheritance promotes code reuse.
- A child class can inherit methods and attributes from a parent class.
- Method overriding allows a child class to change inherited behavior.
- "super()" provides access to the parent's implementation.
- Inheritance helps organize and maintain larger Python programs.

Result

Successfully completed Lab 18 and verified the practical code output in the terminal.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/12549821-cec9-4943-937f-8bd1c5b9d417" />

