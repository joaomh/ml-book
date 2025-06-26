# Creating Functions in Python

## What Are Functions?

In the world of programming, a **function** is an organized and reusable block of code designed to perform a specific task. Think of a function as a "machine" that receives some "inputs" (called parameters or arguments), processes these inputs, and then produces an "output" (the return value).

**Why use functions?**

  * **Code Reusability (DRY - Don't Repeat Yourself):** Avoids code duplication. If you need to perform the same task in multiple places in your program, just create a function and call it.
  * **Organization and Modularity:** Divides the program into smaller, more manageable parts, making the code easier to read, understand, and debug.
  * **Maintenance:** If there's a bug or a necessary change in a specific task, you only need to modify the corresponding function, and the change will be reflected everywhere the function is used.
  * **Abstraction:** Allows you to focus on "what" a function does, without worrying about "how" it does it (once it has been correctly implemented).

## Defining a Function: The `def` Keyword

In Python, functions are defined using the `def` keyword, followed by the function name, parentheses `()` which may contain parameters, and a colon `:`. The function body is indented.

**Basic Syntax:**

```python
def function_name(parameter1, parameter2, ...):
    """Docstring: Explains what the function does, its parameters, and what it returns."""
    # Function body: code to be executed
    # ...
    return return_value # Optional: returns a value
```

### Example 1: Simple Function (No Parameters and No Explicit Return)

```python
def greet():
    print("Hello! Welcome to my function!")
```

```python
# Calling the function to execute it
greet()
greet() # We can call the function as many times as we want
```

```
Hello! Welcome to my function!
Hello! Welcome to my function!
```

### Example 2: Function with Parameters and Return

```python
def sum_numbers(a, b):
    """
    This function sums two numbers and returns the result.
    """
    result = a + b
    return result
```

```python
# Calling the function and printing the returned value
total_sum = sum_numbers(3, 5)
print(f"The sum of 3 and 5 is: {total_sum}") # Output: The sum of 3 and 5 is: 8

print(f"The sum of 10 and 20 is: {sum_numbers(10, 20)}") # Output: The sum of 10 and 20 is: 30
```

```
The sum of 3 and 5 is: 8
The sum of 10 and 20 is: 30
```

**Explanation of components:**

  * **`def sum_numbers(a, b):`**:
      * `def`: Keyword to define a function.
      * `sum_numbers`: Function name. It should be descriptive and follow variable naming conventions (lowercase, `_` to separate words).
      * `(a, b)`: **Parameters** of the function. These are variables that the function expects to receive when called. `a` and `b` are placeholders for the values that will be passed.
      * `:`: Indicates the beginning of the function's code block.
  * **`result = a + b`**: The body of the function, where the logic is implemented.
  * **`return result`**: The `return` keyword is used to send a value back to the place where the function was called. When `return` is executed, the function immediately stops its execution. If a function does not have an explicit `return` statement, it implicitly returns `None`.

### Docstrings: Documenting Your Functions

A crucial aspect for professional and readable code is documentation. In Python, we use **Docstrings** (documentation strings) to explain the purpose of a function, its parameters, and what it returns. They are defined within triple quotes (`"""Docstring here"""`) right below the `def` line.

```python
def average(a, b):
    """
    Calculates the average of two numbers.

    Parameters:
    a (float/int): The first number.
    b (float/int): The second number.

    Returns:
    float: The average of the two numbers.
    """
    return (a + b) / 2
```

```python
# Calling the function and printing the returned value
print(f"The average of 10 and 20 is: {average(10, 20)}") # Output: The average of 10 and 20 is: 15.0
print(f"The average of 5.5 and 8.5 is: {average(5.5, 8.5)}") # Output: The average of 5.5 and 8.5 is: 7.0

# To access the docstring, we can use help() or the __doc__ attribute
print("\n--- Accessing the Docstring ---")
print(average.__doc__)
# help(average) # Uncomment to see the docstring formatted by help()
```

```
The average of 10 and 20 is: 15.0
The average of 5.5 and 8.5 is: 7.0

--- Accessing the Docstring ---

    Calculates the average of two numbers.

    Parameters:
    a (float/int): The first number.
    b (float/int): The second number.

    Returns:
    float: The average of the two numbers.
```

**Benefits of Docstrings:**

  * **Clarity:** Immediately explains the function's purpose.
  * **Development Tools:** IDEs and documentation tools can extract docstrings to provide help and generate automatic documentation.
  * **Collaboration:** Makes it easier for other developers (and for yourself in the future) to understand how to use your function without having to read all its internal code.

## Function Arguments (Parameters vs. Arguments)

It's important to differentiate:

  * **Parameters:** These are the names of the variables listed in the function definition (e.g., `a` and `b` in `def sum_numbers(a, b):`). They are placeholders.
  * **Arguments:** These are the actual values you pass to the function when you call it (e.g., `3` and `5` in `sum_numbers(3, 5)`).

### Types of Arguments:

#### Positional Arguments

Passed in the order in which the parameters are defined.

```python
def greet_person(name, greeting):
    print(f"{greeting}, {name}!")

greet_person("Maria", "Hello") # 'Hello' goes to 'greeting', 'Maria' goes to 'name'
```

```
Hello, Maria!
```

#### Keyword Arguments

Passed using the parameter name, which allows you to change the order.

```python
def greet_person(name, greeting):
    print(f"{greeting}, {name}!")

greet_person(greeting="Good morning", name="João") # The order doesn't matter here
```

```
Good morning, João!
```

#### Default Arguments

Allow a parameter to have a predefined value if no argument is provided for it.

```python
def greet_with_default(name, greeting="Hello"): # 'Hello' is the default value for 'greeting'
    print(f"{greeting}, {name}!")
```

```python
greet_with_default("Carlos")         # Output: Hello, Carlos!
greet_with_default("Ana", "Good morning") # Output: Good morning, Ana! (the default is overridden)
```

```
Hello, Carlos!
Good morning, Ana!
```

**Caution:** Parameters with default values must come **after** parameters without default values.

```python
# This would cause a SyntaxError!
# def invalid_function(greeting="Hello", name):
#     pass
```

#### Arbitrary Argument Lists

When defining functions, you often know exactly how many arguments they will take. However, sometimes you want a function to accept an **arbitrary (variable) number** of arguments. Python provides special syntax for this using `*args` and `**kwargs`.

#### Arbitrary Positional Arguments (`*args`)

The `*args` syntax allows a function to accept any number of **positional arguments**. Inside the function, `args` will be a `tuple` containing all the positional arguments passed after the explicitly defined parameters.

```python
def sum_all_numbers(*numbers):
    """
    Sums all the numbers passed as positional arguments.
    'numbers' will be a tuple of all arguments.
    """
    total = 0
    for num in numbers:
        total += num
    return total

print(f"Sum of (1, 2, 3): {sum_all_numbers(1, 2, 3)}")
print(f"Sum of (10, 20): {sum_all_numbers(10, 20)}")
print(f"Sum of (5,): {sum_all_numbers(5)}")
print(f"Sum of (): {sum_all_numbers()}") # No arguments passed
```

You can combine `*args` with regular positional arguments. `*args` must come after any regular positional parameters.

```python
def greet_people(greeting, *names):
    """
    Greets multiple people with a given greeting.
    """
    for name in names:
        print(f"{greeting}, {name}!")

greet_people("Hello", "Alice", "Bob", "Charlie")
# Output:
# Hello, Alice!
# Hello, Bob!
# Hello, Charlie!
```

#### Arbitrary Keyword Arguments (`**kwargs`)

The `**kwargs` syntax allows a function to accept any number of **keyword arguments**. Inside the function, `kwargs` will be a `dictionary` where keys are the argument names and values are their corresponding values.

```python
def show_user_info(**info):
    """
    Displays user information passed as keyword arguments.
    'info' will be a dictionary.
    """
    print("User Info:")
    for key, value in info.items():
        print(f"  {key.replace('_', ' ').capitalize()}: {value}")

show_user_info(name="David", age=28, city="Berlin")
print("\n---")
show_user_info(product="Laptop", price=1200, brand="TechCorp", release_year=2023)
```
#### Unpacking Argument Lists

The `*` and `**` operators are not just for *defining* functions with arbitrary arguments; they can also be used to **unpack** iterables (like lists and tuples) and dictionaries when *calling* a function.

#### Unpacking Iterables for Positional Arguments (`*`)

When you use `*` before an iterable (like a list or tuple) in a function call, Python "unpacks" its elements, passing them as individual positional arguments to the function.

```python
def multiply(x, y, z):
    """Multiplies three numbers."""
    return x * y * z

numbers_list = [2, 3, 4]
print(f"Multiplying {numbers_list} unpacked: {multiply(*numbers_list)}") # Same as multiply(2, 3, 4)

numbers_tuple = (5, 2, 1)
print(f"Multiplying {numbers_tuple} unpacked: {multiply(*numbers_tuple)}") # Same as multiply(5, 2, 1)

# This is also useful for functions that expect multiple arguments but you have them in a collection
print(f"Max of [10, 20, 5]: {max(*[10, 20, 5])}")
```

#### Unpacking Dictionaries for Keyword Arguments (`**`)

When you use `**` before a dictionary in a function call, Python "unpacks" its key-value pairs, passing them as individual keyword arguments to the function. The dictionary keys must match the parameter names in the function definition.

```python
def create_person(name, age, city):
    """Creates a string with person details."""
    return f"{name} is {age} years old and lives in {city}."

person_details = {
    "name": "Bob",
    "age": 40,
    "city": "Paris"
}

print(f"Creating person from dict: {create_person(**person_details)}") # Same as create_person(name="Bob", age=40, city="Paris")

# You can also combine with explicit keyword arguments (explicit ones take precedence)
other_details = {"age": 25, "occupation": "Artist"}
# print(create_person(name="Carla", **other_details)) # This would error as 'city' is missing
```

Unpacking arguments is a powerful feature for dynamic function calls and for making code more concise when dealing with collections of data that map directly to function parameters.


## Essential Built-in Functions in Python

Python offers a series of "built-in" functions that are always available for use, without the need to import modules. They are fundamental for common operations and manipulating different data types.

### `print()`

The `print()` function is one of the most basic and frequently used in Python. It serves to display information on the console or to standard output.

  * **Syntax:** `print(object(s), sep=' ', end='\n', file=sys.stdout, flush=False)`
  * **`object(s)`:** The item or items you want to print. It can be a string, a number, a list, etc.
  * **`sep` (separator):** An optional string to use as a separator between multiple objects. The default is a space.
  * **`end` (terminator):** An optional string that is added at the end of the output. The default is a newline character (`\n`).
  * **Return:** None (returns `None`).

<!-- end list -->

```python
print("Hello")
```

### `type()`

The `type()` function is used to return the type of an object. It is useful for debugging and understanding what kind of data you are working with.

  * **Syntax:** `type(object)`
  * **`object`:** The item whose type you want to determine.
  * **Return:** The type of the object.

<!-- end list -->

```python
print(type("Hello"))
```

### `len()`

The `len()` function returns the number of items (the "length") of an object. It works for sequences like strings, lists, tuples, dictionaries, and sets.

  * **Syntax:** `len(s)`
  * **`s`:** The object whose item count you want to get.
  * **Return:** An integer representing the number of items.

<!-- end list -->

```python
print(len("Python"))
```

### `int()`

The `int()` function is used to convert a value to an integer type. It can convert floating-point numbers (by truncating the decimal part) or strings that represent whole numbers.

  * **Syntax:** `int(x, base=10)`
  * **`x`:** The value to be converted. It can be a number, or a string that represents a number.
  * **`base` (optional):** If `x` is a string, the numeric base (e.g., 2 for binary, 16 for hexadecimal). The default is 10.
  * **Return:** An integer value. If the conversion is not possible, it raises a `ValueError`.

<!-- end list -->

```python
print(int("123"))
```

### `str()`

The `str()` function is used to convert a value to its string representation.

  * **Syntax:** `str(object)`
  * **`object`:** The item to be converted to a string.
  * **Return:** The string representation of the object.

<!-- end list -->

```python
print(str(123))
```

### `float()`

The `float()` function is used to convert a value to a floating-point number type (decimal number). It can convert integers or strings that represent decimal numbers.

  * **Syntax:** `float(x)`
  * **`x`:** The value to be converted. It can be an integer, or a string that represents a number.
  * **Return:** A floating-point value. If the conversion is not possible, it raises a `ValueError`.

<!-- end list -->

```python
print(float("3.14"))
```

### `abs()`

The `abs()` function returns the absolute value of a number.

  * **Syntax:** `abs(x)`
  * **`x`:** A number (integer, float, or complex).
  * **Return:** The absolute value of `x`.

<!-- end list -->

```python
print(abs(-10))
```

### `max()`

The `max()` function returns the largest item in an iterable or the largest of two or more arguments.

  * **Syntax:** `max(iterable, *[, key, default])` or `max(arg1, arg2, *args[, key])`
  * **`iterable`:** A collection of items (list, tuple, etc.).
  * **`arg1`, `arg2`, `*args`:** Individual arguments.
  * **Return:** The largest item.

<!-- end list -->

```python
print(max(1, 5, 10))
```

### `min()`

The `min()` function returns the smallest item in an iterable or the smallest of two or more arguments.

  * **Syntax:** `min(iterable, *[, key, default])` or `min(arg1, arg2, *args[, key])`
  * **`iterable`:** A collection of items (list, tuple, etc.).
  * **`arg1`, `arg2`, `*args`:** Individual arguments.
  * **Return:** The smallest item.

<!-- end list -->

```python
print(min(1, 5, 10))
```

### `sum()`

The `sum()` function returns the sum of all items in an iterable.

  * **Syntax:** `sum(iterable, /[, start])`
  * **`iterable`:** A collection of numeric items (list, tuple, etc.).
  * **`start` (optional):** A number that is added to the sum of the items. The default is 0.
  * **Return:** The sum of the items, plus the `start` value.

<!-- end list -->

```python
print(sum([1, 2, 3]))
```

### `range()`

The `range()` function is used to generate an immutable sequence of numbers. It is commonly used to iterate a certain number of times in `for` loops.

  * **Syntax:**

      * `range(stop)`: Generates numbers from 0 up to `stop-1`.
      * `range(start, stop)`: Generates numbers from `start` up to `stop-1`.
      * `range(start, stop, step)`: Generates numbers from `start` up to `stop-1`, incrementing (or decrementing) by `step`.

  * **Parameters:**

      * `start` (optional): The integer from where the sequence starts. The default is 0.
      * `stop`: The integer where the sequence stops (not included).
      * `step` (optional): The integer that determines the increment between each number in the sequence. The default is 1.

  * **Return:** A `range` object. To see the numbers, you can convert it to a list (e.g., `list(range(5))`).

<!-- end list -->

```python
# range(stop)
print(list(range(5)))
# Output: [0, 1, 2, 3, 4]

# range(start, stop)
print(list(range(2, 7)))
# Output: [2, 3, 4, 5, 6]

# range(start, stop, step)
print(list(range(1, 10, 2))) # Odd numbers
# Output: [1, 3, 5, 7, 9]

print(list(range(10, 0, -1))) # Countdown
# Output: [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
```

## Lambda Expressions

Lambda expressions (often called "lambda functions") are small, anonymous functions defined with the `lambda` keyword. They are typically used for simple, single-expression functions where a full `def` statement would be overkill.

  * **Characteristics:**

      * **Anonymous:** They don't have a name.
      * **Single Expression:** They can contain only one expression, which is implicitly returned.
      * **Concise:** Designed for quick, inline function definitions.
      * **Limitations:** Cannot contain multiple statements, loops, or complex control flow like `if-elif-else` (though conditional expressions like `x if condition else y` are allowed).

  * **Syntax:**
    `lambda arguments: expression`

<!-- end list -->

```python
# A regular function to add two numbers
def add_regular(x, y):
    return x + y

# The equivalent lambda expression
add_lambda = lambda x, y: x + y

print(f"Regular function (5, 3): {add_regular(5, 3)}")
print(f"Lambda function (5, 3): {add_lambda(5, 3)}")

# Lambda as a key for sorting (common use case)
students = [
    {'name': 'Alice', 'age': 20, 'grade': 'A'},
    {'name': 'Bob', 'age': 22, 'grade': 'C'},
    {'name': 'Charlie', 'age': 19, 'grade': 'B'}
]

# Sort students by age using a lambda function
sorted_by_age = sorted(students, key=lambda student: student['age'])
print("\nSorted students by age:")
for s in sorted_by_age:
    print(s)

# Filter a list using lambda
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
print(f"\nEven numbers from list: {even_numbers}")
```

**When to use Lambda:**

  * When a small, unnamed function is needed for a short period.
  * As arguments to higher-order functions (functions that take other functions as arguments), like `map()`, `filter()`, `sorted()`, `min()`, `max()`.


## Packages and Libraries in Python

### What are packages?

Packages (or libraries) are collections of modules with ready-to-use functions, classes, and tools—without needing to reinvent the wheel.

Famous examples:

  * `math`: mathematical operations
  * `random`: random number generation and selections
  * `pandas`: data analysis
  * `matplotlib`: graph visualization

### Installing Packages with `pip`

`pip` is Python's official package manager. It installs libraries available from **PyPI (Python Package Index)**.

#### How to install a package:

```bash
pip install package_name
```

#### How to upgrade a package version:

```bash
pip install --upgrade package_name
```

#### How to uninstall a package version:

```bash
pip uninstall package_name
```

`conda` is a package and environment manager that is part of **Anaconda/Miniconda**. It is widely used in Data Science because it facilitates the installation of packages with native dependencies (like NumPy, TensorFlow, etc.).

#### How to install a package using conda:

```bash
conda install numpy
```

```bash
conda install -c conda-forge package_name
```

| Criterion    | pip                           | conda                                  |
| :----------- | :---------------------------- | :------------------------------------- |
| Source       | PyPI                          | Conda repositories                     |
| Installation | Lighter and more direct       | More robust and complex                |
| Environments | Uses `venv`                   | Uses `conda env` (more comprehensive)  |
| Speed        | Fast                          | Slower (but manages dependencies)      |
| Popularity   | Universal (works with everything) | More used in data science              |

## Importing Libraries in Python

In Python, a **library** (or, more formally, a **module** or **package**) is a file or a collection of files containing Python code (functions, classes, variables) that can be reused in other programs. Think of them as toolboxes: you don't need to build a screwdriver every time you need one; you simply pick it from your toolbox.

### Why Import?

1.  **Code Reusability:** Prevents you from reinventing the wheel. Many common tasks (mathematics, string manipulation, web access, machine learning) have already been implemented efficiently.
2.  **Organization:** Helps organize large projects into smaller, manageable files.
3.  **Collaboration:** Facilitates the use of code written by other developers.
4.  **Specialized Functionality:** Provides access to functionalities that are not part of Python's "core" but are essential for specific tasks (like `numpy` for numerical arrays, `matplotlib` for plotting).

### How to Import Libraries

There are several ways to import modules in Python, depending on what you need and how you want to reference the imported items.

#### Standard Import: `import module_name`

This is the most common way. It imports the entire module, and you need to use the module name as a prefix to access its functions and variables.

  * **Advantage:** Avoids name conflicts if different modules have functions or variables with the same name.
  * **Disadvantage:** Can make the code slightly longer.

**Example:**

```python
import math # 'math' module for mathematical functions

radius = 5
area = math.pi * (radius ** 2) # Accessing 'pi' from the 'math' module
print(f"The area of the circle is: {area}")
# Output: The area of the circle is: 78.53981633974483
```

#### Import with Alias: `import module_name as alias`

Allows you to give a nickname (alias) to the module. This is useful for modules with long names or when there are widely accepted alias conventions.

  * **Advantage:** Makes the code more concise without losing clarity of the function's origin.
  * **Disadvantage:** If the alias is not intuitive, it can make the code harder to read.

**Example:**

```python
import numpy as np # 'np' is the conventional alias for NumPy

arr = np.array([1, 2, 3, 4, 5]) # Using the alias 'np' to access the 'array' function
print(f"NumPy Array: {arr}")
print(f"Sum of the array: {np.sum(arr)}")
# Output:
# NumPy Array: [1 2 3 4 5]
# Sum of the array: 15
```

#### Selective Import: `from module_name import item1, item2`

Allows you to import only specific functions, classes, or variables from a module. You can then use these items directly, without the module prefix.

  * **Advantage:** Cleaner and more concise code, as it eliminates the prefix.
  * **Disadvantage:** Increases the risk of name conflicts if you import items with the same name from different modules.

**Example:**

```python
from datetime import date # Importing only the 'date' class from the 'datetime' module

today = date(2025, 6, 22) # Using 'date' directly
print(f"Today's date: {today}")
# Output: Today's date: 2025-06-22
```

#### Import All: `from module_name import *`

This form imports all public items from a module directly into the current namespace.

  * **Advantage:** Extremely concise.
  * **Disadvantage:** **Strongly discouraged in most cases\!** It pollutes the current namespace with many names, dramatically increasing the risk of name conflicts and making it difficult to tell where a function or variable came from. Use only in very small scripts or for debugging.

**Example (for demonstration, but not recommended):**

```python
from math import * # NOT RECOMMENDED IN PRODUCTION CODE

radius = 5
area = pi * (radius ** 2) # 'pi' is accessed directly
print(f"The area of the circle is: {area}")
# Output: The area of the circle is: 78.53981633974483
```

### Where to Place Imports

By convention (and good practice), all `import` statements should be placed **at the top of the Python file**, after any file comments (docstrings) and before any other code. This makes the code more readable and helps to quickly identify the file's dependencies.