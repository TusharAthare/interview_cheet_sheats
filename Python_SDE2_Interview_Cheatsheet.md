
# Python SDE-2 Interview Cheatsheet

## Python Basics
**Q: How is Python an interpreted language?**  
A: Python code is executed line by line at runtime by the Python interpreter, without the need for prior compilation into machine code.

**Q: What are Python's key features?**  
- Dynamically Typed  
- Interpreted and High-Level  
- Object-Oriented  
- Extensive Standard Library  
- Multi-Paradigm Support (Procedural, Object-Oriented, Functional)

## OOP in Python
**Q: What is the difference between a class and an object?**  
A: A class is a blueprint for creating objects, while an object is an instance of a class.

**Q: How does Python support encapsulation?**  
A: Encapsulation is implemented by using private (`_` and `__`) attributes and methods to restrict access.

## Python Data Structures
**Q: What is the difference between a list and a tuple?**  
- **List**: Mutable, slower, uses more memory.  
- **Tuple**: Immutable, faster, uses less memory.

**Q: How is a dictionary implemented in Python?**  
A: Dictionaries are implemented as hash tables in Python.

**Q: How do you implement a stack/queue in Python?**  
- Stack: Use `list` with `append()` and `pop()` or `collections.deque`.  
- Queue: Use `collections.deque` or `queue.Queue` for thread-safe operations.

## File Handling
**Q: How do you read and write files in Python?**  
A: Use the built-in `open()` function with modes:  
- `'r'` for read  
- `'w'` for write  
- `'a'` for append  
- `'rb'`/`'wb'` for binary read/write

```python
# Example: Writing to a file
with open("file.txt", "w") as file:
    file.write("Hello, World!")
```

## Error Handling
**Q: How does Python handle exceptions?**  
A: Using `try`, `except`, `else`, and `finally` blocks.

```python
try:
    x = 1 / 0
except ZeroDivisionError as e:
    print("Cannot divide by zero:", e)
finally:
    print("Execution completed.")
```

## Advanced Topics
**Q: What is a Python generator?**  
A: Generators are iterators that yield values one at a time using the `yield` keyword, saving memory.

```python
def my_generator():
    for i in range(5):
        yield i
```

**Q: Explain Python's GIL (Global Interpreter Lock).**  
A: The GIL ensures that only one thread executes Python bytecode at a time, even in multi-threaded programs.

## Python Libraries and Tools
**Q: What are some commonly used Python libraries?**  
- Data Analysis: `Pandas`, `NumPy`  
- Machine Learning: `scikit-learn`, `TensorFlow`  
- Web Development: `Django`, `Flask`  
- Messaging: `Kafka-Python`, `AIOKafka`

**Q: How do you manage dependencies in Python?**  
A: Use `pip` for installing packages and `requirements.txt` or tools like `pipenv` or `poetry` for managing dependencies.

## Coding Exercises
**Q: Write a function to find the factorial of a number.**  
```python
def factorial(n):
    return 1 if n == 0 else n * factorial(n - 1)
```

**Q: How do you check for an anagram?**  
```python
def is_anagram(s1, s2):
    return sorted(s1) == sorted(s2)
```

**Q: Find the second largest element in an array.**  
```python
def second_largest(arr):
    unique = list(set(arr))
    unique.sort()
    return unique[-2]
```

---
**Note**: This cheatsheet is a quick reference. For detailed explanations, practice problem-solving regularly.
