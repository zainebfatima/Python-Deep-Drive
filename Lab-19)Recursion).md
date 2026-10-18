Python Deep Dive — Lab 19: Basic Recursion Example

📌 Lab Information

- Lab Number: 19
- Topic: Basic Recursion
- Language: Python
- Environment: Ubuntu 24.04
- Status: Completed ✅

---

🎯 Objectives

- Understand the concept of recursion in programming.
- Implement a recursive solution to calculate the factorial of a number.
- Learn the differences between recursion and iteration.
- Understand the basic idea of tail recursion.
- Practise debugging using print statements.

🧠 1. What Is Recursion?

Recursion is a programming technique in which a function calls itself to solve a smaller version of the same problem.

A recursive function generally has two important parts:

- Base Case: The condition that stops the recursion.
- Recursive Case: The part where the function calls itself again.

Without a proper base case, a recursive function may continue calling itself until Python raises a "RecursionError".

🔢 2. Understanding Factorial

The factorial of a non-negative integer is the product of all positive integers up to that number.

For example:

"4! = 4 × 3 × 2 × 1 = 24"

Other examples:

- "0! = 1"
- "1! = 1"
- "3! = 6"
- "5! = 120"

Factorial is useful as a learning example because it demonstrates how recursion breaks a problem into smaller steps.

💻 3. Recursive Factorial Program

def factorial(n):
    if n == 0 or n == 1:
        return 1

    return n * factorial(n - 1)


number = 5
answer = factorial(number)

print("Number:", number)
print("Factorial:", answer)

Expected Output

Number: 5
Factorial: 120

🔍 4. Understanding the Code

Base Case

if n == 0 or n == 1:
    return 1

This condition stops the recursion when "n" reaches "0" or "1".

Recursive Case

return n * factorial(n - 1)

- "n - 1" reduces the problem.
- "factorial(n - 1)" calls the same function with a smaller number.
- "n *" multiplies the current number by the returned result.

🔄 5. Dry Run of factorial(4)

The function calls move toward the base case:

factorial(4)
    factorial(3)
        factorial(2)
            factorial(1)
                Returns 1

After reaching the base case, the answers return:

factorial(1) = 1
factorial(2) = 2 × 1 = 2
factorial(3) = 3 × 2 = 6
factorial(4) = 4 × 6 = 24

Final Answer: 24

This process demonstrates that recursive calls go deeper first, then pending calculations are completed as the calls return.

🐞 6. Debugging with Print Statements

I used print statements to observe the function calls and returned results.

def factorial(n):
    print("Entering factorial with n =", n)

    if n == 0 or n == 1:
        print("Base case reached")
        return 1

    result = n * factorial(n - 1)

    print("Returning result for n =", n, ":", result)
    return result


print("Final answer:", factorial(4))

Observed Output

Entering factorial with n = 4
Entering factorial with n = 3
Entering factorial with n = 2
Entering factorial with n = 1
Base case reached
Returning result for n = 2 : 2
Returning result for n = 3 : 6
Returning result for n = 4 : 24
Final answer: 24

Debugging Observation

The output helped me understand two phases:

1. Going down: The function calls itself with smaller values until the base case is reached.
2. Coming back up: Each pending multiplication is completed, and the result is returned.

I also tested "factorial(5)" and confirmed that the final answer was "120".

⚖️ 7. Recursion vs Iteration

Recursion| Iteration
A function calls itself.| A loop repeats instructions.
Requires a base case.| Requires a loop termination condition.
Uses function-call stack space.| Usually uses less extra memory for factorial.
Useful for naturally nested problems.| Often simpler for straightforward repetition.

Both approaches can calculate factorial correctly.

🚀 8. Introduction to Tail Recursion

Tail recursion is a form of recursion where the recursive call is the final operation performed by the function.

Example:

def factorial_tail(n, result=1):
    if n <= 1:
        return result

    return factorial_tail(n - 1, result * n)


print(factorial_tail(5))

Output:

120

The "result" parameter carries the running answer into the next call.

Important: Python does not automatically optimise tail recursion. For large calculations, iteration is generally more practical.

🔐 9. Practical Applications

Factorial itself is mainly a learning example. Recursion is useful in several real programming tasks:

- Directory traversal: Exploring folders and their subfolders.
- Nested data processing: Processing data structures containing other structures.
- Tree algorithms: Exploring hierarchical data and dependency trees.
- Algorithm design: Breaking a problem into smaller versions of itself.

In cybersecurity, recursive directory traversal can help build tools that enumerate files and folders during authorised investigations.

🧪 10. Practical Tests

Input| Expected Result| Status
"factorial(0)"| "1"| To verify
"factorial(1)"| "1"| To verify
"factorial(3)"| "6"| To verify
"factorial(4)"| "24"| Completed
"factorial(5)"| "120"| Completed

The additional test cases can be run to verify the program further.

📚 11. What I Learned

- Recursion means a function calls itself.
- A base case stops further recursive calls.
- A recursive case reduces the problem.
- Factorial can be calculated using recursion.
- Recursive calls return results in reverse order of their descent.
- Print debugging helps reveal program execution flow.
- Iteration and recursion can solve the same problem in different ways.
- Tail recursion carries a running result into the next call.

✅ Lab Conclusion

In this lab, I implemented a recursive factorial function, traced its execution, and used print statements to observe recursive calls and returned results.

I successfully tested the program with "factorial(4) = 24" and "factorial(5) = 120".

This lab established the foundation for understanding recursion and applying it to practical programming tasks, including recursive directory traversal.

---

Next Lab: Lab 20 — To be continued according to the Python Deep Dive roadmap.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/262b4116-0c13-45b3-984f-360d49594019" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ca3d4338-15dc-4125-8f10-ed9b4c782893" />

