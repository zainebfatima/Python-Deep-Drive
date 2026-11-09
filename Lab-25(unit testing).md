 Lab 25: Introduction to Unit Testing with "unittest"

📌 Objectives

1. Understand the fundamentals of unit testing in Python.
2. Write basic test cases to verify code functionality.
3. Run tests and interpret their results.

---

🧠 What Is Unit Testing?

Unit testing is a way to check whether a small part of our code behaves as expected.

Instead of manually checking the output every time, we write tests that compare the actual result with the expected result.

Unit tests help us find mistakes, but passing tests do not guarantee that the entire program is bug-free.

🛠️ Practical Work

Step 1: Create the Project Directory

mkdir -p ~/lab25_unittest
cd ~/lab25_unittest
pwd

Step 2: Create "calculator.py"

def add(a, b):
    return a + b

What I learned:

- "def" defines a function.
- "a" and "b" are parameters that receive values.
- "return" sends the calculated result back.
- We do not need "input()" because we pass the values directly when calling the function.

For example, "add(2, 3)" returns "5".

Step 3: Create "test_calculator.py"

import unittest
from calculator import add


class TestCalculator(unittest.TestCase):

    def test_add(self):
        self.assertEqual(add(2, 3), 5)

    def test_add_another_pair(self):
        self.assertEqual(add(4, 3), 7)

    def test_add_zeros(self):
        self.assertEqual(add(0, 0), 0)


if _name_ == "_main_":
    unittest.main()

Step 4: Understand "self.assertEqual()"

self.assertEqual(add(2, 3), 5)

- "add(2, 3)" calculates the actual result.
- "5" is the expected result.
- "self.assertEqual(actual, expected)" checks whether both values are equal.
- If they match, the test passes.
- If they do not match, the test fails.

Step 5: Run the Test File

python3 test_calculator.py

Expected result:

Ran 1 test
OK

This confirmed that our first test passed.

Step 6: Deliberately Create a Failed Test

We changed the expected answer from "5" to "6":

self.assertEqual(add(2, 3), 6)

The output included:

AssertionError: 5 != 6

What this taught me:

Python calculated "5", but our test expected "6". The test failed because the actual and expected results were different.

The function itself was correct; we deliberately entered the wrong expected answer to practise reading errors.

Afterward, we restored the expected answer to "5", and the test passed again.

Step 7: Test Multiple Examples

We added three test methods:

Test method| Expected result
"test_add"| "add(2, 3) = 5"
"test_add_another_pair"| "add(4, 3) = 7"
"test_add_zeros"| "add(0, 0) = 0"

We ran the file again and received:

Ran 3 tests
OK

This demonstrated how Python can execute multiple tests automatically.

Step 8: Run Tests with Verbose Output

python3 -m unittest -v

Initially, Python reported that no tests were discovered because my file was named "teest.py".

We renamed it:

mv teest.py test_calculator.py

Then we ran:

python3 -m unittest -v

All three tests were discovered and passed.

Lesson learned: Python's default "unittest" discovery searches for files matching the "test*.py" pattern. Correct file naming matters when running automatic test discovery.

---

💬 Questions and Answers from Today's Lab

Q1. Do we need to write values inside the original function?

No. The function accepts values through its parameters when it is called. We supplied test values directly in our test methods.

Q2. What does "self.assertEqual()" mean?

It checks whether the actual result equals the expected result.

Q3. Does a passing test prove the entire program is correct?

No. It proves that the code passed the particular check we wrote. Other situations may still contain bugs.

Q4. Do we need to write a test function 1,000 times to check 1,000 IP addresses?

No. We can write a function that processes each IP using a loop. Unit tests check whether our functions behave correctly; they do not need to be repeated for every input record.

Q5. How could unit testing help in a cybersecurity project?

We can test functions that validate IP addresses, detect duplicates, or compare addresses against a list of flagged IPs. This helps us check whether our security tool behaves as expected.

Q6. Why did automatic test discovery initially find zero tests?

The filename "teest.py" did not match the default "test*.py" discovery pattern. Renaming it to "test_calculator.py" fixed the issue.

Q7. Why should we run tests after changing code?

To check that our changes have not broken previously expected behaviour.

---

🧠 Important Concepts Learned

- Unit testing
- "unittest" module
- "unittest.TestCase"
- "self.assertEqual()"
- Actual versus expected results
- Test methods and naming conventions
- Passing and failing tests
- "AssertionError"
- Running tests directly
- Automatic test discovery
- Verbose output using "-v"
- Using loops to process many records

🐛 Errors and Troubleshooting

Problem| Cause or solution
"NameError: name 'self' is not defined"| Checked the test structure and ensured "self.assertEqual()" was inside a method belonging to the test class.
"AssertionError: 5 != 6"| The expected answer was deliberately incorrect. Restored it to "5".
"Ran 0 tests"| Renamed "teest.py" to "test_calculator.py" so automatic discovery could find it.

🔐 Connection to My Cybersecurity Journey

Unit testing will help me verify the functions I build in future cybersecurity tools.

For example, in my planned Security IP Checker, I could test:

- Whether valid IP addresses are accepted.
- Whether invalid IP addresses are rejected.
- Whether duplicate addresses are detected.
- Whether flagged-IP matching follows the intended rules.

A passing test does not prove that an IP is malicious or that a security tool catches every threat. It verifies only the behaviour covered by the test.

🌱 Today's Reflection

Today, I learned that testing is not simply about running code and hoping it works. We define expected results, check actual results, investigate failures, and fix problems.

I also learned that a program can run successfully when executed directly but still require correct file naming for automatic test discovery.

My biggest takeaway: write code, test its behaviour, understand failures, and test again after changes.

✅ Lab 25 Status

- [x] Understood the purpose of unit testing.
- [x] Created a Python function.
- [x] Wrote three unit tests.
- [x] Used "self.assertEqual()".
- [x] Observed a deliberately failing test.
- [x] Restored the correct expected result.
- [x] Ran tests using "unittest".
- [x] Fixed the filename for automatic discovery.
- [x] Successfully ran all three tests.

Status: Completed

Python Deep Dive — Lab 25: Introduction to Unit Testing with "unittest"
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ba3378bf-c29e-4f6e-9f7a-b9c64b964d56" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/fe1e224a-250d-4a8d-96f9-5fbcc616b20e" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b72beee0-049f-4af8-96f5-55e58b6121cc" />


