Lab 26: Decorators — Basic Usage

Objectives

- Understand Python decorators and their basic syntax.
- Implement a decorator to add extra behaviour to existing functions.
- Understand logging and caching as examples of reusable behaviour.

1. What Is a Decorator?

A decorator adds extra behaviour to a function without changing its original code.

Think of it like adding an extra layer around a function.

2. Basic Decorator

def my_decorator(func):
    def wrapper():
        print("Starting function...")
        func()
    return wrapper


@my_decorator
def greet():
    print("Hello!")


greet()

Output

Starting function...
Hello!

How It Works

- "func": Receives the original function.
- "wrapper()": Adds extra behaviour and calls the original function.
- "return wrapper": Returns the wrapper function.
- "@my_decorator": Applies the decorator to "greet()".
- "greet()": Calls the decorated function.

3. Reusing a Decorator

The same decorator can be applied to multiple functions.

@my_decorator
def welcome():
    print("Welcome to Python!")


welcome()

Output

Starting function...
Welcome to Python!

This avoids repeating the same extra code in every function.

4. Caching with a Decorator

Caching stores previously calculated results so they can be reused.

def my_decorator(func):
    cache = {}

    def wrapper(n):
        if n in cache:
            print("Using saved result")
            return cache[n]

        result = func(n)
        cache[n] = result
        return result

    return wrapper


@my_decorator
def square(n):
    print("Calculating...")
    return n * n


print(square(5))
print(square(5))

Output

Calculating...
25
Using saved result
25

How Caching Works

1. The first call calculates "5 * 5".
2. "cache[n] = result" saves the result under the key "5".
3. The second call finds "5" in the cache.
4. Python reuses the saved result "25".

5. Key Concepts

Concept| Purpose
Decorator| Adds behaviour to a function
Wrapper| Controls the extra behaviour
Logging| Records program activity
Caching| Reuses saved results
"return wrapper"| Returns the wrapper function
"cache[n] = result"| Saves a calculated result

6. Debugging Experience

During the caching exercise, I encountered:

TypeError: 'NoneType' object is not callable

Cause: I had forgotten to return the wrapper function from the decorator.

Fix:

return wrapper

This reminded me that indentation and return statements are important when working with nested functions and decorators.

What I Learned

- How decorators receive and wrap functions.
- Why "return wrapper" is different from "return wrapper()".
- How the "@" syntax applies a decorator.
- How one decorator can be reused with multiple functions.
- How a simple dictionary-based cache saves and reuses results.
- How to debug a decorator by checking return statements and indentation.

Lab Status: Completed

Next Step: Continue to the next Python Deep Dive lab.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/52b0cfe3-2523-4e0d-afe1-e61a8bac5d53" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/9b88cfb2-e94b-4943-a929-11af10c6387c" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/c5eb8ea0-60ba-4a22-a273-bafea95ca74b" />


