Lab 34 — Simple Scripting for File Management

Overview

In this lab, I learned how to use Python scripts to manage files and directories. I explored how scripting can automate repetitive file-management tasks instead of performing them manually.

Objectives

- Understand basic file management using Python scripts.
- Learn how to list files.
- Learn how to copy files.
- Learn how to rename files.
- Understand the benefits of automation over manual file operations.

1. Listing Files Using Python

Module: "os"

The "os" module allows Python to interact with the operating system, including files and directories.

import os

files = os.listdir(".")

print(files)

Key concepts:

- "os.listdir(".")" — Lists all entries in the current directory.
- "." — Represents the current directory.
- ".." — Represents the parent directory.
- "~" — Represents the home directory in the Linux shell.

2. Filtering Python Files

I learned how to filter files based on their extensions.

import os

files = os.listdir(".")

for file in files:
    if file.endswith(".py") and os.path.isfile(file):
        print(file)

Key concepts:

- "for" loop — Iterates through directory entries.
- ".endswith(".py")" — Checks whether a filename ends with ".py".
- "os.path.isfile(file)" — Checks whether an entry is an actual file.
- "and" — Both conditions must be True.

Important: "os.listdir()" returns both files and directories. Filtering by extension alone does not guarantee that an entry is an actual file.

3. Copying Files Using Python

Module: "shutil"

The "shutil" module provides functions for copying and managing files.

import shutil

shutil.copy("notes.txt", "backup.txt")

print("File copied successfully!")

Key concepts:

- "shutil.copy(source, destination)" — Copies a file.
- The original file remains unchanged.
- If the destination already exists, its contents are overwritten.

Practical exercise:

Created a sample file:

echo "Learning Python file management" > notes.txt

Ran the Python script and verified both files using:

ls

Verified their contents using:

cat notes.txt
cat backup.txt

Both files contained the same text.

4. Renaming Files Using Python

Function: "os.rename()"

import os

os.rename("backup.txt", "my_backup.txt")

print("File renamed successfully!")

Key concepts:

- "os.rename(old_name, new_name)" — Renames an existing file.
- It changes the filename rather than creating a second copy.
- The original filename no longer exists after a successful rename.

5. Combined Lab Script

import os
import shutil

# 1. List Python files
files = os.listdir(".")

for file in files:
    if file.endswith(".py") and os.path.isfile(file):
        print(file)

# 2. Copy a file
shutil.copy("notes.txt", "backup.txt")
print("File copied successfully!")

# 3. Rename the copied file
os.rename("backup.txt", "my_backup.txt")
print("File renamed successfully!")

6. Important Commands and Functions

Function| Purpose
"os.listdir()"| Lists directory contents
".endswith()"| Checks filename endings
"os.path.isfile()"| Checks whether an entry is a file
"shutil.copy()"| Copies files
"os.rename()"| Renames files

7. What I Learned

- How Python interacts with files and directories.
- How to list and filter files.
- How to distinguish actual files from directories.
- How to copy files without deleting the original.
- How to rename files using Python.
- How to combine multiple operations in one script.

8. Why Is Scripting Useful?

Scripting saves time and effort by automating repetitive tasks. It reduces manual work, makes file management easier, and allows us to manage large numbers of files efficiently.

Real-world example: Instead of manually copying hundreds of files, a Python script can automate the process.

Lab Summary

In this lab, I used Python's built-in "os" and "shutil" modules to perform basic file-management operations.

I learned that scripting provides flexibility, saves time, and makes repetitive tasks easier to automate.

Status: Practical objectives completed.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/79a4bbd6-efc7-466b-9a1c-bb00f842c3c5" />
