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

Your `sum_numbers` example is perfect for this\!

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