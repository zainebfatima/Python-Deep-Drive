Lab 30: Basic SQLite Usage in Python

Status: Completed
Topic: Database Fundamentals with SQLite

1. Objectives

By completing this lab, I learned how to:

- Connect Python to an SQLite database.
- Create a database table.
- Insert records into a table.
- Retrieve records using SQL queries.
- Fetch and display database results.
- Prevent duplicate records using "PRIMARY KEY" and "INSERT OR IGNORE".

2. Complete Python Program

import sqlite3

# Connect to the database
connection = sqlite3.connect("school_lab30.db")
cursor = connection.cursor()

# Create the students table
cursor.execute("""
CREATE TABLE IF NOT EXISTS students (
    id INTEGER PRIMARY KEY,
    name TEXT,
    age INTEGER
)
""")

# Insert a student without duplicating the same ID
cursor.execute("""
INSERT OR IGNORE INTO students (id, name, age)
VALUES (1, 'Ali', 15)
""")

# Save database changes
connection.commit()

# Retrieve all student records
cursor.execute("SELECT * FROM students")
results = cursor.fetchall()

# Display the results
print("Student records:")

for student in results:
    print(student)

# Close the database connection
connection.close()

3. Important Concepts

Concept| Meaning
"sqlite3"| Python module for working with SQLite databases.
"connect()"| Connects to a database or creates it if it does not exist.
"cursor()"| Creates an object used to execute SQL commands.
"execute()"| Executes an SQL statement.
"CREATE TABLE"| Creates a table to store records.
"IF NOT EXISTS"| Prevents an error if the table already exists.
"PRIMARY KEY"| Uniquely identifies each record.
"INSERT INTO"| Adds a record to a table.
"INSERT OR IGNORE"| Skips an insertion that violates a uniqueness constraint.
"commit()"| Saves database changes.
"SELECT *"| Retrieves all columns from a table.
"fetchall()"| Returns all remaining query results as a list.
"close()"| Closes the database connection.

4. Understanding the Output

Expected output:

Student records:
(1, 'Ali', 15)

The result is a tuple containing the student's ID, name, and age.

- "1" is the student's ID.
- "'Ali'" is the student's name.
- "15" is the student's age.

The parentheses represent a tuple, and the list returned by "fetchall()" contains the retrieved records.

5. Understanding the Duplicate Record Problem

Initially, running the program repeatedly inserted another Ali record each time.

Why did this happen?

SQLite saves data in the database file. Running an "INSERT" statement again attempts another insertion; it does not automatically replace the previous record.

How I fixed it:

1. Used a fresh database file for the updated table structure.
2. Added "id INTEGER PRIMARY KEY" to enforce unique IDs.
3. Used "INSERT OR IGNORE" to skip duplicate IDs.
4. Used "commit()" to save changes.

Expected result: Running the corrected program multiple times keeps the same student record instead of adding another record with ID "1".

Note: "INSERT OR IGNORE" works for duplicate IDs because the table has a primary key. "CREATE TABLE IF NOT EXISTS" does not modify an existing table's structure.

6. Common Mistakes

- Forgetting to call "commit()" after inserting data.
- Assuming each program run starts with an empty database.
- Expecting "CREATE TABLE IF NOT EXISTS" to update an existing table.
- Using "fetchall()" before executing a "SELECT" query.
- Forgetting to close the connection when finished.

7. Lab Completion Checklist

- [x] Connected to an SQLite database.
- [x] Created a table.
- [x] Inserted a student record.
- [x] Saved changes with "commit()".
- [x] Retrieved records using "SELECT".
- [x] Fetched results using "fetchall()".
- [x] Understood tuples and database output.
- [x] Learned how "PRIMARY KEY" helps prevent duplicate IDs.
- [x] Understood why repeated program runs can cause duplicates.

8. Final Learning Summary

This lab introduced me to the fundamentals of database operations in Python. I learned that SQLite stores data persistently, SQL commands manipulate database records, and a primary key helps maintain unique record identifiers.

Key takeaway: Python can connect to a database, store information, retrieve it, and help maintain data integrity using SQLite.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/02d75e8f-ba43-495a-bc7b-b03011211e29" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/e44e6213-f627-44a4-95c8-58b48f1de007" />

