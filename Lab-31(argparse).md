[7:01 pm, 30/10/2026] ...: Lab 31: CLI Applications with argparse

1. Learning Objectives

- Understand the basics of creating Command Line Interface (CLI) applications.
- Learn how to use Python's "argparse" module.
- Develop a simple CLI application that accepts user input and produces output.
- Understand automatic help text generation.

2. What is a CLI?

CLI stands for Command Line Interface.

It allows users to interact with an application by typing commands into a terminal instead of clicking buttons or using graphical menus.

Examples:

- Python command-line tools
- Git commands
- Linux utilities
- Network security tools

3. What is argparse?

"argparse" is a built-in Python module used to parse command-line arguments.

It allows users to provide information when launching an application without repeatedly opening and modifying its source code.

Why use argparse?

- Accept user input through terminal commands.
- Make applications easier to operate.
- Avoid manually changing input values inside source code.
- Generate automatic help instructions.
- Handle required and optional arguments.

4. Important argparse Components

Component| Purpose
"import argparse"| Imports the module
"ArgumentParser()"| Creates an argument parser
"add_argument()"| Defines an argument
"parse_args()"| Reads command-line arguments
"args.name"| Accesses a supplied argument
"required=True"| Makes an argument compulsory
"default="| Provides a default value
"type=float"| Converts input into a floating-point number
"help="| Describes an argument

5. Practical 1: Greeting Application

Code

import argparse

parser = argparse.ArgumentParser(
    description="A simple greeting application"
)

parser.add_argument(
    "--name",
    help="Enter the user's name"
)

args = parser.parse_args()

print("Hello", args.name)

Execution

python3 laab31.py --name Zaineb

Output:

Hello Zaineb

Another example:

python3 laab31.py --name Ali

Output:

Hello Ali

Observation: We can change the supplied name without modifying the Python source code.

6. Required Arguments

The "required=True" parameter makes an argument compulsory.

Example:

parser.add_argument(
    "--name",
    required=True
)

If the user runs:

python3 laab31.py

Output: An error indicating that the required "--name" argument is missing.

If the user provides the argument:

python3 laab31.py --name Sara

Output:

Hello Sara

7. Default Values

The "default" parameter provides a fallback value when the user doesn't supply an argument.

Example:

parser.add_argument(
    "--name",
    default="Guest"
)

Without an argument:

python3 laab31.py

Output:

Hello Guest

With an argument:

python3 laab31.py --name Zaineb

Output:

Hello Zaineb

8. Automatic Help Generation

One of the useful features of "argparse" is automatic help generation.

Command:

python3 laab31.py --help

Or:

python3 laab31.py -h

It displays:

- Application usage instructions.
- Available arguments.
- Argument descriptions.
- Automatically generated help information.

We can customize the help output using "description" and "help".

9. Practical 2: CLI Calculator

We created a simple calculator that accepts two numbers and an operation through terminal arguments.

Code

import argparse

parser = argparse.ArgumentParser(
    description="A simple CLI calculator"
)

parser.add_argument("--num1", type=float, required=True)
parser.add_argument("--num2", type=float, required=True)
parser.add_argument("--operation", required=True)

args = parser.parse_args()

print(args.num1)
print(args.num2)
print(args.operation)

if args.operation == "add":
    result = args.num1 + args.num2

print("Result:", result)

Execution

python3 calculator.py --num1 10 --num2 5 --operation add

Output:

10.0
5.0
add
Result: 15.0

Understanding the workflow

1. "argparse" receives the supplied arguments.
2. "parse_args()" processes them.
3. Python performs the calculation.
4. "print()" displays the result.

Important: "argparse" collects the input; it does not perform the calculation itself.

10. argparse vs input()

input()| argparse
Requests input while the program runs.| Receives arguments when launching the program.
Uses the "input()" function.| Uses "add_argument()" and "parse_args()".
Interactive input.| Command-line arguments.

11. Common Errors and Lessons

- FileNotFoundError / can't open file: Check the Python filename and current directory.
- Missing required argument: Supply the compulsory argument.
- Incorrect argument name: Use the argument name defined with "add_argument()".
- Unexpected input type: Use the correct "type" parameter when defining arguments.
- Unrecognized argument: Check spelling and the defined CLI options.

12. Real-World Applications

"argparse" is useful for developing:

- IP address checking tools.
- File-processing utilities.
- Automation scripts.
- Data-processing applications.
- Cybersecurity command-line tools.

Connection to My Portfolio Projects

Security IP Checker:

python3 ip_checker.py --file ips.txt

Users could provide a file directly through the terminal instead of modifying the source code.

13. Key Takeaways

- CLI applications operate through terminal commands.
- "argparse" makes Python applications easier to interact with.
- Arguments can be required or optional.
- Default values provide fallback inputs.
- "--help" and "-h" generate automatic help instructions.
- Command-line arguments make applications more flexible and reusable.

Lab Status: All four learning objectives completed successfully.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/e8142218-bf80-457e-a268-d1c2d37e2643" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/45caaccf-b73a-489d-a61e-7994881b04fc" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/2b1179d9-5fa6-4f61-a5d8-bbf2c163871d" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/0b39721b-d7e6-4dda-ac77-301a3a689995" />



