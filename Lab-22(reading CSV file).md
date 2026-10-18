# 🐍 Python Deep Dive — Lab 22: Reading CSV Files

## 📌 Overview
In this lab, I learned how to use Python's built-in csv module to read structured text data (like spreadsheets) and convert the data into Python lists and dictionaries.

### 🎯 Cybersecurity & Bug Bounty Connection
Security researchers frequently handle massive lists of data, such as subdomains, IP addresses, or leaked user accounts, which are exported as CSV files. Knowing how to parse CSV data with Python allows me to automate target filtering and identify high-value assets quickly during target mapping.

---

## 📁 Step 1: Environment Setup & Target Data

First, I created the dedicated lab directory and initialized a target data file (students.csv) directly from the terminal using the nano editor:

bash
mkdir -p lab22_csv
cd lab22_csv
nano students.csv


*Data inside students.csv:*
csv
Name,Age,Grade
Ali,12,7
Sara,13,8
Ahmed,11,6


### 💡 Core Mechanics of CSV
* *CSV* stands for *Comma-Separated Values*.
* Every single line represents a distinct row (record).
* Commas act as boundaries separating each individual data field.
* The first line serves as the header block, defining the names of the data columns.

---

## 🧠 Step 2: Processing Basic Rows (csv.reader)

This structural path reads the data sequentially, treating each row as a standard list of items.

python
import csv

with open("students.csv", "r") as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)


### 💻 Expected Terminal Output
python
['Name', 'Age', 'Grade']
['Ali', '12', '7']
['Sara', '13', '8']
['Ahmed', '11', '6']


### 🔍 Code Logic Break-down

| Code Component | Functional Execution |
| :--- | :--- |
| import csv | Loads the native Python CSV engine. |
| open("students.csv", "r") | Accesses the targeted document in standard read mode. |
| as file | Binds the opened target data stream to a variable named file. |
| csv.reader(file) | Prepares an active data pointer to scroll through the dataset. |
| for row in reader: | Moves step-by-step through every row in the file. |
| with open(...) | Automatically terminates the file connection once the block finishes to save memory. |

### 🧪 Dry Run Mechanics
Because the underlying target file contains four raw text lines (including the top header heading), the loop runs exactly *four distinct times*, printing out each list item consecutively.

---

## 📚 Step 3: Storing Data via Dictionaries (csv.DictReader)

Instead of working with raw lists, this advanced configuration dynamically maps the column header to specific dictionary keys, collecting them cleanly inside a master list container.

python
import csv

students = []  # Storage container for the finalized records

with open("students.csv", "r") as file:
    reader = csv.DictReader(file)  # Converted keys are dynamically pulled from row 1
    for row in reader:
        students.append(row)  # Direct injection of individual data blocks into the list

print(students)


### 💻 Expected Terminal Output
python
[
    {'Name': 'Ali', 'Age': '12', 'Grade': '7'},
    {'Name': 'Sara', 'Age': '13', 'Grade': '8'},
    {'Name': 'Ahmed', 'Age': '11', 'Grade': '6'}
]


### 💡 Data Architecture Insight
* Using csv.DictReader ignores the top header line as raw data and uses it exclusively as the structural labels (*Keys*).
* *Critical Type Rule:* Data parsed directly from a CSV file is explicitly treated as a *String (Text)* by default. If numerical math operations are required on an value like "12", it must be converted manually using int().

---

## 🖨️ Step 4: Formatting Clean Target Reports

To loop through our custom dictionary structures and output clean, reader-friendly logs on the screen:

python
for student in students:
    print("Name:", student["Name"])
    print("Age:", student["Age"])
    print("Grade:", student["Grade"])
    print("---")


### 💻 Expected Terminal Output
text
Name: Ali
Age: 12
Grade: 7
---
Name: Sara
Age: 13
Grade: 8
---
Name: Ahmed
Age: 11
Grade: 6
---


---

## 💬 Core Concepts Clarified

* *Are CSV files exclusively created by spreadsheet apps like Microsoft Excel?*
  * Correction: Excel can open and save them, but they are just plain text files. They can be created using minimalist terminal interfaces like nano.
* *Does the reader command perform the visual printing task automatically?*
  * Correction: No, the reader tool is simply an internal database processing object. We must actively use a for loop to draw out the values and print them to the screen.
* *Why do we initialize the script with students = []?*
  * Correction: This initializes an empty list array bucket. Without this placeholder bucket, data processed inside the closed loop block would vanish instantly once the script terminates
  * <img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/eef69745-bc0e-4ab3-8737-29cbda714ed8" />
  <img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/88be48ac-cca6-4968-ae53-cd5ed1ce0392" />

