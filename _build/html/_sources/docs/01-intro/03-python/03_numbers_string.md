# Numbers and Strings in Python

## Fundamental Numeric Types

Python handles numbers very flexibly, allowing operations with different types and conversions between them. Let's explore the main numeric types and how to perform these conversions. In Python, the most common numeric types are:

  * **Integers (`int`):** Represent whole numbers (positive, negative, or zero) without decimal places. Examples: `10`, `-5`, `0`, `1000000`.
  * **Floats (`float`):** Represent numbers with decimal places. They are used for non-integer values. Examples: `3.14`, `-0.5`, `10.0` (even if it's a whole number, the presence of `.0` classifies it as `float`).

### Example of Basic Operations with Numbers

```python
# Defining variables with different numeric types
a = 10  # Type: int
b = 3.5 # Type: float

print(f"Value of 'a': {a}, Type of 'a': {type(a)}")
print(f"Value of 'b': {b}, Type of 'b': {type(b)}")

print("\n--- Arithmetic Operations ---")
print(f"Sum (a + b): {a + b}")         # Result: float (type promotion)
print(f"Exponentiation (a ** 2): {a ** 2}") # Result: int
print(f"Integer Division (a // 3): {a // 3}") # Result: int (discards the fractional part)
print(f"Remainder of Division (a % 3): {a % 3}")   # Result: int
print(f"Division (a / 3): {a / 3}")         # Result: float (division always returns float)
```

**Important Notes:**

  * **Type Promotion:** When you perform operations between an `int` and a `float`, Python "promotes" the `int` to a `float` before the operation, and the result will always be a `float`. This prevents loss of precision.
  * **Division (`/`):** In Python 3+, division with the `/` operator always returns a `float`, even if the result is a whole number (e.g., `10 / 2` returns `5.0`).
  * **Integer Division (`//`):** To get only the integer part of a division, use the `//` operator. It truncates the decimal part, it does not round.
  * **Modulo (`%`):** The `%` operator returns the remainder of the division. Very useful for checking if a number is even/odd or if it's a multiple of another.

## Type Casting

Python allows you to explicitly convert one data type to another using conversion functions.

### Main Numeric Conversion Functions:

  * **`int()`:** Converts a value to an integer.
      * Truncates floats (discards the decimal part).
      * Can convert strings that represent whole numbers.
  * **`float()`:** Converts a value to a floating-point number.
      * Adds `.0` if the number is an integer.
      * Can convert strings that represent numbers (integers or decimals).
  * **`str()`:** Converts a value to a string (text).

### Conversion Examples:

```python
print("\n--- Conversion Examples ---")

# From float to int (truncation)
print(f"int(3.9): {int(3.9)}")   # Output: 3 (truncates the decimal part)
print(f"int(3.1): {int(3.1)}")   # Output: 3

# From int to float
print(f"float(10): {float(10)}") # Output: 10.0 (adds .0 to be float)
print(f"float(5): {float(5)}")   # Output: 5.0

# From number to string
print(f"str(42): '{str(42)}'")    # Output: '42' (now it's text)
print(f"str(3.14): '{str(3.14)}'") # Output: '3.14'

# From string to int
print(f"int('7'): {int('7')}")     # Output: 7
# print(int('7.5')) # This would cause an error! The string must be a valid integer representation
# print(int('abc')) # This would also cause an error!

# From string to float
print(f"float('7.5'): {float('7.5')}") # Output: 7.5
print(f"float('10'): {float('10')}")   # Output: 10.0
# print(float('abc')) # This would cause an error!
```

**Cautions in String Conversion:**

  * When converting a `string` to an `int`, the string must contain only characters that represent a valid whole number (no decimal point or other non-numeric characters, unless they are `+` or `-` signs at the beginning).
  * When converting a `string` to a `float`, the string can contain a decimal point.

## Strings in Python

Strings are immutable sequences of characters (lists of bytes, at a more technical level). Python offers a wide range of useful operations and methods to manipulate text, making them one of the most versatile data types.

### Creating Strings

Strings can be created using single quotes (`'...'`), double quotes (`"..."`), or triple quotes (`'''...'''` or `"""..."""`) for strings that span multiple lines.

```python
minha_string1 = 'Hello, world!'
minha_string2 = "Python is fun."
minha_string3 = """This is a string
that can span multiple lines."""

print(minha_string1)
print(minha_string2)
print(minha_string3)
```

### Main String Operations and Methods

Python has various built-in methods that facilitate string manipulation. Remember that strings are **immutable**, meaning no method alters the original string; they always return a **new** string with the result of the operation.

```python
mensagem = "Hello, world!"

print(f"\nOriginal string: '{mensagem}'")

print("\n--- Common String Methods ---")

# 1. Changing case (uppercase/lowercase)
print(f"Uppercase (upper()): {mensagem.upper()}") # Returns a new string in uppercase
print(f"Lowercase (lower()): {mensagem.lower()}") # Returns a new string in lowercase
print(f"Capitalize first letter (capitalize()): {mensagem.capitalize()}") # First letter of the string in uppercase

# 2. Text Replacement
# replace(old, new): Replaces all occurrences of a substring with another.
print(f"Replacing 'world' with 'Python': {mensagem.replace('world', 'Python')}")
print(f"Replacing 'o' with 'X': {mensagem.replace('o', 'X')}")

# 3. Accessing Characters and Substrings (Indexing and Slicing)
# Strings are indexed starting from 0.
print(f"First letter (mensagem[0]): {mensagem[0]}") # Output: 'H'
print(f"Last letter (mensagem[-1]): {mensagem[-1]}") # Output: '!'
print(f"Slicing (mensagem[0:3]): {mensagem[0:3]}") # Output: 'Hel' (from index 0 up to 2, 3 is exclusive)
print(f"Slicing from start to 5 (mensagem[:6]): {mensagem[:6]}") # Output: 'Hello,'
print(f"Slicing from 7 to end (mensagem[7:]): {mensagem[7:]}") # Output: 'world!'

# 4. String Length
# len(string): Returns the number of characters in the string.
print(f"String length (len(mensagem)): {len(mensagem)}")

# 5. Checking String Start/End
# startswith(prefix): Checks if the string starts with the given prefix.
# endswith(suffix): Checks if the string ends with the given suffix.
print(f"Starts with 'Hello'? {mensagem.startswith('Hello')}") # Output: True
print(f"Ends with 'world!'? {mensagem.endswith('world!')}") # Output: True

# 6. Checking Content
# in (operator): Checks if a substring is present in the string.
print(f"'world' in message? {'world' in mensagem}") # Output: True
print(f"'Python' in message? {'Python' in mensagem}") # Output: False

# 7. Remove Whitespace (Trim)
# strip(): Removes whitespace from the beginning and end of the string.
# lstrip(): Removes whitespace from the left.
# rstrip(): Removes whitespace from the right.
texto_com_espacos = "   Hello World!   "
print(f"'{texto_com_espacos.strip()}'") # Output: 'Hello World!'
```

### String Formatting with f-strings (Formatted String Literals)

f-strings (introduced in Python 3.6) are the most modern and recommended way to embed variables and expressions within strings. They make the code more readable and concise.

To create an f-string, simply prefix the string with the letter `f` (or `F`) and place variables or expressions inside curly braces `{}`.

```python
nome = "João"
idade = 20
cidade = "São Paulo"
hobby = "programming"

# Basic f-string example
print(f"My name is {nome} and I am {idade} years old.")

# Embedding expressions and calculations
print(f"In 5 years, {nome} will be {idade + 5} years old.")

# Number formatting
pi = 3.14159265
print(f"The value of Pi with 2 decimal places is: {pi:.2f}") # :.2f formats to 2 decimal places

# Text alignment
produto = "T-shirt"
preco = 29.99
print(f"Product: {produto:<10} Price: R$ {preco:>8.2f}") # <10 left-aligns in 10 characters, >8.2f right-aligns in 8 characters with 2 decimal places
```

### Other String Formatting (for reference)

While f-strings are preferred in most cases, it's good to know other formatting methods:

  * **`format()` method:** Older than f-strings, but still useful.

    ```python
    print("My name is {} and I am {} years old.".format(nome, idade))
    print("Product: {prod} Price: R$ {prc:.2f}".format(prod="Book", prc=45.50))
    ```

  * **`%` operator (Legacy Formatting):** A "C-style" formatting, less common in new code.

    ```python
    print("My name is %s and I am %d years old." % (nome, idade))
    ```