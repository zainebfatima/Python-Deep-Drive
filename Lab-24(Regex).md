 Python Deep Dive — Lab 24: Basic Regular Expressions (Regex)

📌 Lab Overview

Topic: Basic Regular Expressions (Regex)
Language: Python
Module: "re"
Environment: Ubuntu Terminal
File: "lab24_regex.py"

🎯 Lab Objectives

- Understand the basic concept of regular expressions.
- Learn how to use Python's "re" module.
- Find, match, search, and replace patterns in strings.
- Practise special characters, character sets, and capturing groups.

---

1. What Is Regex?

Regex stands for Regular Expression.

In simple words, regex helps us find particular patterns inside text.

For example:

- Find digits in a sentence.
- Find a name.
- Find spaces.
- Replace one word with another.
- Extract specific information from a larger sentence.

Regex can be useful when analysing text, processing logs, and working with cybersecurity data.

2. Setting Up the Lab

Created a separate directory and Python file in the Ubuntu terminal.

mkdir -p ~/lab24_regex
cd ~/lab24_regex
nano lab24_regex.py

To run the file:

python3 lab24_regex.py

3. Importing the Regex Module

import re

What I learned: "re" is Python's built-in module for working with regular expressions.

4. Finding Digits with "\d"

import re

text = "I am learning Python 24"

result = re.findall(r"\d", text)

print(result)

Output:

['2', '4']

My understanding

- "re.findall()" finds all matches.
- "\d" matches one digit at a time.
- Because "2" and "4" are separate digits, they appear separately.

5. Finding Complete Numbers with "\d+"

import re

text = "Lab 24 has 3 exercises"

numbers = re.findall(r"\d+", text)

print("Numbers:", numbers)

Output:

Numbers: ['24', '3']

What I learned

The "+" means one or more consecutive matches.

- "\d" finds individual digits.
- "\d+" keeps consecutive digits together.
- "24" becomes one match, while "3" becomes another.

6. Other Useful Regex Patterns

Pattern| Meaning
"\d"| Matches a digit
"\d+"| Matches one or more consecutive digits
"\w"| Matches a word character, such as a letter, digit, or underscore
"\w+"| Matches one or more consecutive word characters
"\s"| Matches whitespace, such as a space
"[aeiou]"| Matches any one of the listed vowels
"()"| Captures a particular part of a match

Example: Finding vowels

import re

text = "education"

result = re.findall(r"[aeiou]", text)

print(result)

Output:

['e', 'u', 'a', 'i', 'o']

My observation: The vowels were returned in the order they appeared in the word.

7. Understanding "re.match()" and "re.search()"

Using "re.match()"

import re

text = "Python is fun"

result = re.match(r"Python", text)

if result:
    print("Match found:", result.group())
else:
    print("No match")

Output:

Match found: Python

"re.match()" checks whether the pattern matches at the beginning of the text.

When I changed the pattern to look for a word that was not at the beginning, it returned "No match".

Using "re.search()"

import re

text = "I am learning Python"

result = re.search(r"Python", text)

if result:
    print("Match found:", result.group())
else:
    print("No match")

Output:

Match found: Python

My understanding

- "re.match()" checks the beginning.
- "re.search()" searches through the text for the first match.

My own explanation: "search()" looks through the line, while "match()" checks only the beginning.

8. Replacing Text with "re.sub()"

import re

text = "cat is cute"

result = re.sub(r"cat", "dog", text)

print(result)

Output:

dog is cute

What I learned: "re.sub()" replaces matching text and returns the updated string.

9. Understanding Capturing Groups "()"

This was an important concept I practised carefully.

Suppose we have:

import re

text = "My name is Zain"

result = re.search(r"My name is (\w+)", text)

print(result.group(0))
print(result.group(1))

Output:

My name is Zain
Zain

My understanding in simple words

Imagine we have the sentence:
"Student Ali is 19 years old"

We want to extract only "Ali" or "19" instead of printing the whole matching phrase.

Parentheses "()" tell Python which part we want to capture separately.

- "group(0)" gives the entire matched text.
- "group(1)" gives the first captured part.
- "group(2)" gives the second captured part, if there is one.

Example with two groups

import re

text = "Student Ali is 19 years old"

result = re.search(r"Student (\w+) is (\d+)", text)

print(result.group(0))
print(result.group(1))
print(result.group(2))

Output:

Student Ali is 19
Ali
19

The question I asked

What happens if we do not use groups?

My answer:

Python can still find matching text, but we cannot use "group(1)" to retrieve a separately captured part if we have not defined a capturing group.

My final understanding:

If I want to print one specific part instead of the whole matching phrase, I can use parentheses "()" to capture that part and "group(1)" to retrieve it.

10. Final Mini-Challenge

import re

text = "Student Zain is 19 years old and studies Python"

name = re.search(r"Student (\w+)", text)
age = re.findall(r"\d+", text)
updated_text = re.sub(r"Python", "Cybersecurity", text)

print("Name:", name.group(1))
print("Age:", age)
print("Updated sentence:", updated_text)

Final output:

Name: Zain
Age: ['19']
Updated sentence: Student Zain is 19 years old and studies Cybersecurity

What this challenge tested

- "re.search()" found the matching phrase.
- "(\w+)" captured the name.
- "group(1)" extracted the name.
- "re.findall(r"\d+", text)" found the complete age.
- "re.sub()" replaced "Python" with "Cybersecurity".

I successfully ran this challenge in the terminal and received the expected output.

---

11. Questions and Answers from My Lab

Q1. What does "\d" do?

It matches one digit at a time.

Q2. What is the difference between "\d" and "\d+"?

"\d" matches individual digits, while "\d+" matches one or more consecutive digits together.

Q3. What does "\w+" match?

One or more consecutive word characters, such as letters, digits, or underscores.

Q4. What does "\s" match?

Whitespace, such as a space.

Q5. What is the difference between "re.match()" and "re.search()"?

"re.match()" checks the beginning of the string. "re.search()" looks for the first match anywhere in the string.

Q6. What does "re.findall()" do?

It returns all non-overlapping matches in a list.

Q7. What does "re.sub()" do?

It replaces matching text with replacement text.

Q8. Why do we use parentheses "()" in regex?

To capture a particular part of a match separately.

Q9. What is the difference between "group(0)" and "group(1)"?

"group(0)" returns the entire match. "group(1)" returns the first captured group.

Q10. What happens if we do not use capturing groups?

We can still search for and match text, but we cannot retrieve a separately captured group using "group(1)" if no capturing group exists.

---

12. Mistakes, Confusion, and Lessons Learned

- At first, I needed clarification about why "\d" returned digits separately.
- I learned that "\d+" keeps consecutive digits together.
- I initially confused "re.match()" with searching through an entire sentence. Testing it helped me understand the difference.
- I needed a simpler explanation of capturing groups.
- I learned that "group(0)" returns the full match and "group(1)" returns the first captured part.
- I initially selected the full match instead of the captured name in the final challenge. I corrected my understanding after reviewing the difference between "group(0)" and "group(1)".

Important lesson: Testing predictions in the terminal and asking questions helped me understand the concepts instead of merely memorising syntax.

---

13. Final Lab Summary

In Lab 24, I learned how to use Python's "re" module to search for patterns in text, find digits and vowels, match text at the beginning, search throughout a sentence, replace words, and capture specific information with groups.

I practised each concept using Python code in the Ubuntu terminal and completed a final mini-challenge successfully.

Status: Beginner regex objectives practised; further practice will help strengthen my understanding.

Next step: Continue to the next Python Deep Dive lab after reviewing these concepts.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b1e4e6f2-dbe5-4eb6-b05e-142dcb673b95" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/70f83f36-8451-4955-aeb7-0e2ec7245492" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ef311a66-b621-47a6-8e11-1d03f8c18d03" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/616a7f3e-04e2-4380-a937-b1936786ad32" />




