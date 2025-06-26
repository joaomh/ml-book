# Built-in Data Types

In programming, understanding **data types** is fundamental. They determine what we can do with each stored value.

In Python, variables can store data of different types, and each type has its own behavior.

Python has the following built-in data types by default:

Text Type:

  - `str`

Numeric Types:

  - `int`, `float`, `complex`

Sequence Types:

  - `list`, `tuple`, `range`

Mapping Type:

  - `dict`

Set Types:

  - `set`, `frozenset`

Boolean Type:

  - `bool`

Binary Types:

  - `bytes`, `bytearray`, `memoryview`

Null Type:

  - `NoneType`

<!-- end list -->

```python
# Examples of variables
nome = "João"  # string (text)
idade = 25     # integer
altura = 1.75  # float (decimal number)
estudante = True  # boolean (True or False)

# Displaying the values
print("Name:", nome)
print("Age:", idade)
print("Height:", altura)
print("Is student?", estudante)
```

## Checking Types

```python
type(nome), type(idade), type(altura)
```

## Notes on Variable Naming

A variable can have a simple name (like `x` or `y`) or a more descriptive name (`age`, `name`, `total_volume`).

But there are some **important rules**:

  * ✅ A variable name must start with a **letter** or an **underscore** (`_`)
  * ❌ A variable name **cannot start with a number**
  * ✅ A variable name can only contain **letters, numbers, and underscores** (`A-Z`, `a-z`, `0-9`, `_`)
  * ⚠️ Names are **case-sensitive**: `idade`, `Idade`, and `IDADE` are three different variables

## Binary Types in Python

**Binary types** are used to store data in byte format—that is, in **binary format**. These types are useful when working with binary files, network communication, image manipulation, audio, and other low-level data.

Python has three main binary data types:

### 🔹 `bytes`

  * An **immutable** sequence of integer values (0 to 255).
  * Widely used for reading binary files.

### 🔹 `bytearray`

  * Similar to `bytes`, but it is **mutable**, meaning its values can be changed.

### 🔹 `memoryview`

  * Allows accessing and manipulating a binary structure (like `bytes` or `bytearray`) **without copying the data into memory**.


```python
# Bytes: immutable sequence
dados_bytes = bytes([10, 20, 30, 40])
print(dados_bytes)
print(type(dados_bytes))  # <class 'bytes'>

# Bytearray: mutable sequence
dados_mutaveis = bytearray([1, 2, 3, 4])
print(dados_mutaveis)
dados_mutaveis[0] = 100  # changing the first value
print(dados_mutaveis)
print(type(dados_mutaveis))  # <class 'bytearray'>

# Memoryview: efficient view of binary data
mem = memoryview(bytes([10, 20, 30, 40]))
print(mem[0])  # accesses the first byte
print(type(mem))  # <class 'memoryview'>
```
Here's the translated Markdown:

## Null Variable (None)

In Python, the `None` value is used to represent the absence of a value or a null value. It indicates that the variable has no data assigned to it. It is equivalent to `null` in other languages. The type of `None` is special and is called `NoneType`.

```python
# Declaring a variable without a value
variable = None
```

```python
print(variable)
print(type(variable))  # Output: <class 'NoneType'>
```

## Numbers and Strings in Python

### Fundamental Numeric Types

Python handles numbers very flexibly, allowing operations with different types and conversions between them. Let's explore the main numeric types and how to perform these conversions. In Python, the most common numeric types are:

  * **Integers (`int`):** Represent whole numbers (positive, negative, or zero) without decimal places. Examples: `10`, `-5`, `0`, `1000000`.
  * **Floats (`float`):** Represent numbers with decimal places. They are used for non-integer values. Examples: `3.14`, `-0.5`, `10.0` (even if it's a whole number, the presence of `.0` classifies it as `float`).

#### Example of Basic Operations with Numbers

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

### Type Casting

Python allows you to explicitly convert one data type to another using conversion functions.

#### Main Numeric Conversion Functions:

  * **`int()`:** Converts a value to an integer.
      * Truncates floats (discards the decimal part).
      * Can convert strings that represent whole numbers.
  * **`float()`:** Converts a value to a floating-point number.
      * Adds `.0` if the number is an integer.
      * Can convert strings that represent numbers (integers or decimals).
  * **`str()`:** Converts a value to a string (text).

#### Conversion Examples:

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

### Strings in Python

Strings are immutable sequences of characters (lists of bytes, at a more technical level). Python offers a wide range of useful operations and methods to manipulate text, making them one of the most versatile data types.

#### Creating Strings

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

#### Main String Operations and Methods

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

#### String Formatting with f-strings (Formatted String Literals)

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

#### Other String Formatting (for reference)

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

## Arithmetic Operators in Python

Arithmetic operators are symbols that perform mathematical operations on values (numbers). They are essential for any type of calculation, from simple sums to more complex operations.

### The Main Arithmetic Operators

Python supports the most common arithmetic operators. Here's a list and an explanation of each:

| Operator | Name                | Description                                                                                             | Example    |
| :------- | :------------------ | :------------------------------------------------------------------------------------------------------ | :--------- |
| `+`      | Addition            | Adds two values.                                                                                        | `a + b`    |
| `-`      | Subtraction         | Subtracts the right operand from the left operand.                                                      | `a - b`    |
| `*`      | Multiplication      | Multiplies two values.                                                                                  | `a * b`    |
| `/`      | Division            | Divides the left operand by the right operand. **Always returns a `float` in Python 3.** | `a / b`    |
| `//`     | Floor Division      | Divides and returns the integer part of the quotient (rounds down).                                     | `a // b`   |
| `%`      | Modulo (Remainder)  | Returns the remainder of the division of the left operand by the right operand.                       | `a % b`    |
| `**`     | Exponentiation      | Raises the left operand to the power of the right operand.                                              | `a ** b`   |

### Detailed Examples

Let's see each operator in action:

```python
# Defining some variables for the examples
num1 = 20
num2 = 7
num3 = 2.5
```

#### Addition (`+`)

```python
result_addition = num1 + num2
print(f"Addition: {num1} + {num2} = {result_addition}") # 20 + 7 = 27

# Addition also works with floats
result_addition_float = num1 + num3
print(f"Addition with float: {num1} + {num3} = {result_addition_float}") # 20 + 2.5 = 22.5
```

#### Subtraction (`-`)

```python
result_subtraction = num1 - num2
print(f"Subtraction: {num1} - {num2} = {result_subtraction}") # 20 - 7 = 13

result_subtraction_float = num2 - num3
print(f"Subtraction with float: {num2} - {num3} = {result_subtraction_float}") # 7 - 2.5 = 4.5
```

#### Multiplication (`*`)

```python
result_multiplication = num1 * num2
print(f"Multiplication: {num1} * {num2} = {result_multiplication}") # 20 * 7 = 140

result_multiplication_float = num1 * num3
print(f"Multiplication with float: {num1} * {num3} = {result_multiplication_float}") # 20 * 2.5 = 50.0
```

#### Division (`/`)

**Remember: Always returns a `float`\!**

```python
result_division = num1 / num2
print(f"Division: {num1} / {num2} = {result_division}") # 20 / 7 = 2.8571...

result_exact_division = 10 / 2
print(f"Exact Division: 10 / 2 = {result_exact_division}") # 10 / 2 = 5.0 (still a float)
```

#### Integer Division (`//`) - Floor Division

This operator truncates the result, discarding the decimal part. The result is always an `int` if both operands are `int`, or a `float` if one of the operands is `float`.

```python
result_integer_division = num1 // num2
print(f"Integer Division: {num1} // {num2} = {result_integer_division}") # 20 // 7 = 2

# With negative numbers, integer division rounds down to the nearest whole number (towards negative infinity)
print(f"Integer Division (negative): -10 // 3 = {-10 // 3}") # Output: -4
print(f"Integer Division (negative): 10 // -3 = {10 // -3}") # Output: -4

# With float, the result will also be float, but with the decimal part truncated
result_integer_division_float = num1 // num3
print(f"Integer Division with float: {num1} // {num3} = {result_integer_division_float}") # 20 // 2.5 = 8.0
```

#### Modulo (`%`) - Remainder of Division

Useful for checking parity, cycles, and other logic that depends on the remainder of a division.

```python
result_modulo = num1 % num2
print(f"Modulo: {num1} % {num2} = {result_modulo}") # 20 % 7 = 6 (because 20 = 2*7 + 6)

# Checking if a number is even or odd
even_number = 12
odd_number = 13
print(f"{even_number} is even? {even_number % 2 == 0}")   # True
print(f"{odd_number} is odd? {odd_number % 2 != 0}") # True
```

#### Exponentiation (`**`)

```python
result_exp = num2 ** 2 # 7 raised to the power of 2 (7 squared)
print(f"Exponentiation: {num2} ** 2 = {result_exp}") # 7 ** 2 = 49

result_exp_cubed = 3 ** 3 # 3 raised to the power of 3 (3 cubed)
print(f"Exponentiation: 3 ** 3 = {result_exp_cubed}") # 3 ** 3 = 27

# With floats
result_exp_float = 2 ** num3 # 2 raised to the power of 2.5
print(f"Exponentiation with float: 2 ** {num3} = {result_exp_float}") # 2 ** 2.5 = 5.65685...
```

### Order of Precedence for Arithmetic Operators

Just like in mathematics, operators in Python follow an order of precedence to determine which operation is performed first in a complex expression.

1.  **Parentheses `()`**: Force a specific order of operations.
2.  **Exponentiation `**`**
3.  **Multiplication `*`**, **Division `/`**, **Floor Division `//`**, **Modulo `%`**: Evaluated from left to right.
4.  **Addition `+`**, **Subtraction `-`**: Evaluated from left to right.

**Tip:** When in doubt, or to ensure code clarity, use parentheses to group operations, even if the default precedence would already resolve them in the desired order.

#### Precedence Example:

```python
calculation1 = 5 + 3 * 2 # 3 * 2 is done first (6), then 5 + 6
print(f"5 + 3 * 2 = {calculation1}") # Output: 11

calculation2 = (5 + 3) * 2 # Parentheses force 5 + 3 first (8), then 8 * 2
print(f"(5 + 3) * 2 = {calculation2}") # Output: 16

calculation3 = 20 / 2 ** 2 # 2 ** 2 is done first (4), then 20 / 4
print(f"20 / 2 ** 2 = {calculation3}") # Output: 5.0
```

Mastering arithmetic operators is fundamental, as they are the basis for any program involving calculations, from a simple currency converter to complex scientific algorithms.

## The Boolean Type (`bool`) in Python

The boolean type (`bool`) is one of the most fundamental data types in Python. It represents logical truth values, meaning something that can be **true** or **false**.

### Boolean Values

There are only two possible values for the boolean type:

  * **`True`**: Represents truth.
  * **`False`**: Represents falsehood.

**Important:** Note that `True` and `False` begin with a capital letter. In Python, this makes a difference\! `true` (with a lowercase 't') is not recognized as a boolean value.

#### Basic Example:

```python
is_raining = True
has_sun = False

print(f"Is it raining? {is_raining}")
print(f"Is it sunny? {has_sun}")
print(f"Type of variable 'is_raining': {type(is_raining)}")
```

### Comparison (Relational) Operators

Comparison operators are used to compare two values and always return a boolean value (`True` or `False`). They form the basis for conditionals (`if`, `elif`, `else`).

| Operator | Description      | Example       | Result |
| :------- | :--------------- | :------------ | :----- |
| `==`     | Equal to         | `5 == 5`      | `True` |
| `!=`     | Not equal to     | `5 != 10`     | `True` |
| `>`      | Greater than     | `10 > 5`      | `True` |
| `<`      | Less than        | `5 < 10`      | `True` |
| `>=`     | Greater than or equal to | `10 >= 10`    | `True` |
| `<=`     | Less than or equal to    | `5 <= 5`      | `True` |

#### Usage Examples:

```python
print("\n--- Comparison Operators ---")
x = 10
y = 5
z = 10

print(f"x == z: {x == z}")   # True (10 is equal to 10)
print(f"x != y: {x != y}")   # True (10 is not equal to 5)
print(f"x > y: {x > y}")     # True (10 is greater than 5)
print(f"y < x: {y < x}")     # True (5 is less than 10)
print(f"x >= z: {x >= z}")   # True (10 is greater than or equal to 10)
print(f"y <= z: {y <= z}")   # True (5 is less than or equal to 10)

# Comparing strings (case-sensitive)
name1 = "Alice"
name2 = "alice"
print(f"'{name1}' == '{name2}': {name1 == name2}") # False
```

### Logical (Boolean) Operators

Logical operators combine boolean values or comparison results to form more complex expressions.

| Operator | Description                                   | Example                  | Result  |
| :------- | :-------------------------------------------- | :----------------------- | :------ |
| `and`    | Returns `True` if **both** conditions are `True`. | `True and False`         | `False` |
| `or`     | Returns `True` if **at least one** condition is `True`. | `True or False`          | `True`  |
| `not`    | Inverts the boolean value (`True` becomes `False`, `False` becomes `True`). | `not True`               | `False` |

#### Usage Examples:

```python
print("\n--- Logical Operators ---")
age = 25
has_driver_license = True
has_passport = False

# Using 'and'
can_drive = (age >= 18) and has_driver_license
print(f"Can drive? (age >= 18 and has_driver_license): {can_drive}") # True and True -> True

# Using 'or'
can_travel = has_passport or (age >= 21) # Hypothetical travel condition
print(f"Can travel? (has_passport or age >= 21): {can_travel}") # False or True -> True

# Using 'not'
does_not_have_passport = not has_passport
print(f"Does not have passport? (not has_passport): {does_not_have_passport}") # not False -> True

# Combination of operators
complex_expression = (age > 30 and has_driver_license) or (not has_passport)
print(f"Complex expression: {complex_expression}") # (False and True) or True -> False or True -> True
```

### Using Booleans in Conditionals (`if`/`elif`/`else`)

Boolean values are the backbone of control flow structures.

```python
print("\n--- Booleans in Conditionals ---")
is_day = True
temperature = 28

if is_day and temperature > 25:
    print("It's a hot and sunny day!")
elif is_day and temperature <= 25:
    print("It's a pleasant day.")
else:
    print("It's night or the day was not defined.")

# Example with user input
answer = input("Do you like Python? (yes/no): ").lower()

if answer == "yes":
    print("That's great! Python is very versatile.")
elif answer == "no":
    print("Maybe you'll change your mind over time :)")
else:
    print("I didn't understand your answer. Please type 'yes' or 'no'.")
```

### "Truthy" and "Falsy" Values (Boolean Evaluation of Other Types)

In Python, many data types can be evaluated in a boolean context (like in an `if` condition) even without explicitly being `True` or `False`.

  * **"Falsy" values (evaluated as `False`):**
      * `False` (obviously)
      * `None`
      * `0` (the integer zero)
      * `0.0` (the float zero)
      * Empty strings (`""`, `''`)
      * Empty lists (`[]`)
      * Empty tuples (`()`)
      * Empty dictionaries (`{}`)
      * Empty sets (`set()`)
  * **"Truthy" values (evaluated as `True`):**
      * Anything that is **not** "falsy".
      * Examples: `True`, any non-zero number (`1`, `-5`, `3.14`), any non-empty string (`"Hello"`, `" "`), any non-empty list/tuple/dictionary/set.

#### "Truthy" and "Falsy" Examples:

```python
print("\n--- 'Truthy' and 'Falsy' Values ---")

if 0:
    print("0 is True") # Will not be printed
else:
    print("0 is False") # Will be printed

if 1:
    print("1 is True") # Will be printed

if "":
    print("Empty string is True") # Will not be printed
else:
    print("Empty string is False") # Will be printed

if "Hello":
    print("Non-empty string is True") # Will be printed

my_list = []
if my_list:
    print("Non-empty list is True") # Will not be printed
else:
    print("Empty list is False") # Will be printed

my_list.append(1)
if my_list:
    print("Non-empty list is True") # Will be printed
```