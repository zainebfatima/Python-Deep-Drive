Python Deep Dive — Lab 39

Python Style Checks & Formatting (PEP 8)

Status: Completed
Score: 88/100

1. Objectives

- Understand PEP 8 coding standards.
- Check Python code for style violations using Flake8.
- Automatically format Python code using Black.
- Understand the purpose of autopep8.
- Write clean, readable, and consistent Python code.

2. Key Concepts

PEP 8

PEP 8 is the official Python style guide. It provides recommendations for writing readable and consistent Python code.

Important conventions:

- Use 4 spaces for indentation.
- Use "snake_case" for variables and functions.
- Use "PascalCase" for class names.
- Add spaces around operators.
- Keep lines reasonably short (79 characters is the recommended limit).

Flake8

Flake8 checks Python code and reports style violations and certain coding errors.

It does not automatically fix or format code.

Command:

flake8 lab39.py

Black

Black is an automatic Python code formatter. It reformats code to maintain consistent formatting.

Command:

black lab39.py

autopep8

autopep8 automatically fixes many PEP 8 style violations.

Show proposed changes without modifying the original file:

autopep8 --diff lab39.py

Apply formatting directly:

autopep8 --in-place lab39.py

3. Practical Implementation

Created a Python file:

nano lab39.py

Initial code:

name="Zaineb"
age=19
security_level="high"
print("Name:",name)
print("Age:",age)

4. Flake8 Errors

Initially, Flake8 reported several style violations.

Error| Meaning
E225| Missing whitespace around an operator
E203| Unwanted whitespace before punctuation
E231| Missing whitespace after a comma
W391| Blank line at the end of the file

These were formatting issues, not problems with the program's basic logic.

5. Formatting and Verification

First, I used Black:

black lab39.py

Output confirmed:

"1 file reformatted"

Then I checked the formatted code:

cat lab39.py

Next, I ran Flake8 again:

flake8 lab39.py

No output appeared, meaning no Flake8 issues were reported.

Finally, I tested autopep8:

autopep8 --diff lab39.py

No output appeared because there were no formatting changes to suggest.

6. Important Differences

Tool| Main Purpose
PEP 8| Provides Python style guidelines
Flake8| Checks and reports issues
Black| Automatically formats code
autopep8| Automatically fixes many PEP 8 violations

7. What I Learned

- Clean formatting improves code readability.
- Flake8 helps identify style problems.
- Black saves time by automatically formatting code.
- autopep8 provides another way to fix PEP 8 violations.
- A program can run correctly while still having style violations.
- Checking code after formatting is an important habit.

8. Final Lab Result

Lab 39 successfully completed — 88/100.

All practical formatting and verification steps were completed successfully.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/c19a51f9-b3cb-402d-9d2e-6bf2fa497c54" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/3ccd32f8-8dc8-4439-aab3-5f84d8d1962f" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/effcde84-2cb6-4fa0-8b80-8c3d5ab07a49" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/01e3a215-4dbc-495f-9649-83c1bb3e9410" />



