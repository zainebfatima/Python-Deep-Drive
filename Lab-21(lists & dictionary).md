# 🐍 Lab 21: List & Dictionary Comprehensions

## 📌 Lab Overview
* *Lab Number:* 21
* *Topic:* List and Dictionary Comprehensions
* *Status:* Completed concept practice

## 🎯 Objectives
* Understand list comprehensions to create lists in fewer lines.
* Learn dictionary comprehensions to create key-value pairs.
* Use conditions inside comprehensions to filter data.
* Understand how comprehensions can replace traditional loops.
* Practise writing code independently and correcting mistakes.

---

## 1. What Is a Comprehension?
A comprehension is a shorter way to create a list or dictionary using a loop. Instead of writing multiple lines using a traditional loop, we can often perform the same task in one line.

---

## 2. List Comprehension

### Example 1: Calculate Squares
python
squares = [n ** 2 for n in range(1, 6)]
print(squares)

* *Output:* [1, 4, 9, 16, 25]
* *Logic:*
  * [] creates a list.
  * n ** 2 calculates the square of each number.
  * for n in range(1, 6) takes numbers from 1 to 5 (excluding 6).

### Example 2: Filter Odd Numbers
python
odds = [n for n in range(1, 11) if n % 2 != 0]
print(odds)

* *Output:* [1, 3, 5, 7, 9]
* *Logic:*
  * % (modulo) gives the remainder.
  * n % 2 != 0 checks whether the remainder is not zero.
  * != means not equal to.

### Example 3: Filter Even Numbers
python
evens = [n for n in range(1, 11) if n % 2 == 0]
print(evens)

* *Output:* [2, 4, 6, 8, 10]
* *Logic:* n % 2 == 0 selects numbers that have a remainder of zero when divided by 2.

---

## 3. Dictionary Comprehension
A dictionary stores data in key-value pairs. 

* *Example syntax:* student = {"Ali": 80, "Sara": 90} (Where "Ali" and "Sara" are keys, and 80 and 90 are their values).

### Example 1: Dictionary of Odd Numbers
python
odds = {n: n for n in range(1, 11) if n % 2 != 0}
print(odds)

* *Output:* {1: 1, 3: 3, 5: 5, 7: 7, 9: 9}
* *Logic:* {} creates a dictionary. The first n is the key, and the second n is the value.

### Example 2: Dictionary of Squares
python
squares = {n: n ** 2 for n in range(1, 6)}
print(squares)

* *Output:* {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
* *Logic:* n before the : is the key, and n ** 2 after the : is the value. 

### Example 3: Dictionary of Doubles
python
doubles = {n: n * 2 for n in range(1, 4)}
print(doubles)

* *Output:* {1: 2, 2: 4, 3: 6}
* *Logic:* The original number is the key, and n * 2 multiplies it by 2 to create the value.

---

## 4. Important Difference: * vs **

| Operator | Meaning | Example | Result |
| :--- | :--- | :--- | :--- |
| * | Multiplication | 2 * 3 | 6 |
| ** | Power / Exponent | 2 ** 3 | 8 |
| ** 2 | Square | 3 ** 2 | 9 |
| ** 3 | Cube | 2 ** 3 | 8 |

💡 *My learning point:* A single star * means multiplication, while two stars ** mean power.

---

## 5. List vs Dictionary Comprehension

| Feature | List | Dictionary |
| :--- | :--- | :--- |
| *Brackets* | [] | {} |
| *Stores* | Individual Items | Key-Value pairs (key: value) |
| *Example* | [n * 2 for n in range(1, 4)] | {n: n * 2 for n in range(1, 4)} |
| *Main Purpose* | Create a sequence of items | Create a mapped data structure |

---

## 6. Challenges I Attempted

### Challenge 1: Calculate Squares
* *Task:* Create a list of squares from 1 to 5.
* *Code:* squares = [n ** 2 for n in range(1, 6)]
* *Result:* Correct. 

### Challenge 2: Calculate Cubes
* *Task:* Create a list of cubes from 1 to 4.
* *First Attempt Mistake:* I wrote range(1, 6), which included 5 and outputted 125.
* *Correction:*
  python
  cubes = [n ** 3 for n in range(1, 5)]
  
* *Lesson learned:* The stop value in range() is always excluded. Using meaningful variable names like cubes makes code cleaner.

### Challenge 3: Find Odd Numbers
* *First Attempt Mistake:* squares = [if n / 2 == 0 for n in range(2, 10)]
* *Problems identified:* The if condition was out of place, / was used instead of %, and the main expression was missing before the for loop.
* *Correction:*
  python
  odds = [n for n in range(1, 11) if n % 2 != 0]
  

### Challenge 4: Dictionary of Odd Numbers
* *Task:* Create a dictionary matching odd numbers to themselves.
* *Code:* odds = {n: n for n in range(1, 11) if n % 2 != 0}
* *Result:* Correct.

### Challenge 5: Dictionary of Squares
* *Task:* Map numbers 1–5 to their squares.
* *Code:* squares = {n: n ** 2 for n in range(1, 6)}
* *Result:* Correct (fixed a quick typo where I wrote for nin instead of for n in).

### Challenge 6: Dictionary of Doubles
* *Task:* Map numbers 1–3 to their doubled value.
* *Code:*
  python
  doubles = {n: n * 2 for n in range(1, 4)}
  print(doubles)
  
* *Result:* Correct. Outputted {1: 2, 2: 4, 3: 6} smoothly.
