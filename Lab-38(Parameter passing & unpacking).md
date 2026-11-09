Python Deep Dive — Lab 38: Parameter Passing & Unpacking

Lab Objectives

- Understand parameter passing and arguments.
- Use default parameters.
- Understand "*args".
- Understand "**kwargs".
- Unpack lists using "*".
- Unpack dictionaries using "**".

1. Parameters vs Arguments

A parameter is a variable written inside a function definition.

An argument is the actual value passed when calling the function.

def student(name):
    print(name)

student("Ali")

- "name" is the parameter.
- ""Ali"" is the argument.

2. Default Parameters

A default parameter has a predefined value.

def student(name="Unknown"):
    print(name)

student()
student("Zaineb")

Output:

Unknown
Zaineb

If no argument is provided, Python uses the default value.

3. *args — Variable Positional Arguments

"*args" allows a function to accept multiple positional arguments.

Python collects these arguments into a tuple.

def security_alerts(*args):
    print(args)
    print(len(args))

security_alerts("Login Alert", "Malware", "Unusual Traffic")

Output:

('Login Alert', 'Malware', 'Unusual Traffic')
3

- "args" stores all received arguments.
- "len(args)" counts the arguments.
- A tuple is created to store them.

4. **kwargs — Variable Keyword Arguments

"**kwargs" allows a function to accept multiple keyword arguments.

Python collects them into a dictionary.

def alert_details(**kwargs):
    print(kwargs)
    print(kwargs["severity"])

alert_details(ip="192.168.1.10", severity="High")

Output:

{'ip': '192.168.1.10', 'severity': 'High'}
High

- "kwargs" stores key-value pairs.
- "kwargs["severity"]" accesses the value associated with the "severity" key.

5. * Unpacking — Lists

The "*" operator unpacks an iterable into separate positional arguments.

def add(a, b, c):
    print(a + b + c)

numbers = [5, 10, 15]

add(*numbers)

Output:

30

"add(*numbers)" is equivalent to:

add(5, 10, 15)

6. ** Unpacking — Dictionaries

The "**" operator unpacks dictionary key-value pairs into keyword arguments.

def student_info(name, age):
    print(name)
    print(age)

student = {
    "name": "Zaineb",
    "age": 19
}

student_info(**student)

Output:

Zaineb
19

"student_info(**student)" is equivalent to:

student_info(name="Zaineb", age=19)

7. Practical Implementation

File: "lab38.py"

# 1. Normal Parameter Passing + Default Parameter
def analyst_info(name, role="Security Analyst"):
    print("Analyst:", name)
    print("Role:", role)


# 2. *args - Accept Multiple Positional Arguments
def security_alerts(*args):
    print("\nSecurity Alerts:")
    print("Total received:", len(args))


# 3. **kwargs - Accept Multiple Keyword Arguments
def alert_details(**kwargs):
    print("\nAlert Details:")
    print(kwargs)


# 4. * Unpacking - Unpack a List
def calculate_alerts(alert1, alert2, alert3):
    print("\nTotal alerts:", alert1 + alert2 + alert3)


# 5. ** Unpacking - Unpack a Dictionary
def analyst_details(name, department, experience):
    print("\nAnalyst Details:")
    print("Name:", name)
    print("Department:", department)
    print("Experience:", experience)


# Function Calls
analyst_info("Zaineb")

security_alerts(
    "Suspicious Login",
    "Malware Detection",
    "Unusual Traffic"
)

alert_details(
    ip="192.168.1.10",
    severity="High",
    status="Under Review"
)

numbers = [5, 10, 15]
calculate_alerts(*numbers)

analyst = {
    "name": "Zaineb",
    "department": "Cybersecurity",
    "experience": 1
}

analyst_details(**analyst)

Run the program:

python3 lab38.py

8. Important Differences

Syntax| Purpose| Result
"*args"| Collect positional arguments| Tuple
"**kwargs"| Collect keyword arguments| Dictionary
"*list"| Unpack list elements| Positional arguments
"**dict"| Unpack dictionary pairs| Keyword arguments

Remember:

- "args" and "*kwargs" are used in function definitions.
- "" and "*" are used for unpacking in function calls.

9. Knowledge Check

1. What is the difference between a parameter and an argument?
2. What happens when a function receives no value for a required parameter?
3. What data type does "*args" create?
4. What data type does "**kwargs" create?
5. What does "len(args)" return?
6. What is the purpose of "*" when calling a function?
7. What is the purpose of "**" when calling a function?

10. Lab Completion

- [x] Normal parameter passing
- [x] Default parameters
- [x] "*args"
- [x] "**kwargs"
- [x] List unpacking
- [x] Dictionary unpacking
- [x] Practical implementation

Status: Completed

Key Learning: Python provides flexible ways to pass, collect, and unpack arguments, making functions more reusable and adaptable.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/90d7643f-a52e-4bc2-b330-ebd06cb38ed8" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/59d5e30e-f683-4c4e-b1ba-05002e635040" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/5e681e5e-1247-4712-b0a4-1c7eeb64f947" />


