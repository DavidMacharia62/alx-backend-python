# Type Annotations in Python 3

## Overview

Type annotations in Python 3 provide a way to add hints about the types of variables and function parameters in your code. While Python remains dynamically typed, these annotations allow you to declare the expected types for variables and function signatures. This enhances code readability, helps catch potential bugs early, and makes it easier for tools like mypy to analyze and validate your code.

## Table of Contents

1. [Basic Type Annotations](#basic-type-annotations)
2. [Function Signatures](#function-signatures)
3. [Duck Typing](#duck-typing)
4. [Validating Code with mypy](#validating-code-with-mypy)

## 1. Basic Type Annotations <a name="basic-type-annotations"></a>

You can use type hints to specify the expected type of a variable. This is done by adding a colon after the variable name, followed by the desired type. For example:

```python
# Variable annotation
age: int = 25

# Function argument annotation
def greet(name: str) -> str:
    return f"Hello, {name}!"
```

Here, `age` is annotated as an integer, and the `greet` function takes a string argument and returns a string.

## 2. Function Signatures <a name="function-signatures"></a>

Type annotations can also be applied to function signatures to specify the types of parameters and return values. For instance:

```python
def add_numbers(a: int, b: int) -> int:
    return a + b
```

In this example, `add_numbers` is a function that takes two integer parameters (`a` and `b`) and returns an integer.

## 3. Duck Typing <a name="duck-typing"></a>

Python follows the philosophy of "duck typing," which means that the type of an object is determined by its behavior rather than its explicit type. Type annotations in Python embrace this philosophy by allowing you to focus on what the code does rather than the specific types involved. For instance:

```python
def get_length(obj: typing.Sequence) -> int:
    return len(obj)
```

In this example, `get_length` takes any object that implements the `Sequence` protocol (like lists or tuples) and returns the length. The actual type is determined by the object's behavior.

## 4. Validating Code with mypy <a name="validating-code-with-mypy"></a>

[mypy](http://mypy-lang.org/) is a third-party static type checker for Python that uses the type annotations in your code to catch potential errors before runtime. To use mypy, install it using:

```bash
pip install mypy
```

After adding type annotations to your code, run mypy from the terminal:

```bash
mypy your_script.py
```

Mypy will analyze your code and report any type-related issues it finds.

Remember, type annotations in Python are optional, and the interpreter doesn't enforce them at runtime. They are primarily for documentation and static analysis by tools like mypy. Using type annotations can significantly improve code quality and maintainability, especially in larger projects.
