# The Boolean Type (`bool`) in Python

The boolean type (`bool`) is one of the most fundamental data types in Python. It represents logical truth values, meaning something that can be **true** or **false**.

## Boolean Values

There are only two possible values for the boolean type:

  * **`True`**: Represents truth.
  * **`False`**: Represents falsehood.

**Important:** Note that `True` and `False` begin with a capital letter. In Python, this makes a difference\! `true` (with a lowercase 't') is not recognized as a boolean value.

### Basic Example:

```python
is_raining = True
has_sun = False

print(f"Is it raining? {is_raining}")
print(f"Is it sunny? {has_sun}")
print(f"Type of variable 'is_raining': {type(is_raining)}")
```

## Comparison (Relational) Operators

Comparison operators are used to compare two values and always return a boolean value (`True` or `False`). They form the basis for conditionals (`if`, `elif`, `else`).

| Operator | Description      | Example       | Result |
| :------- | :--------------- | :------------ | :----- |
| `==`     | Equal to         | `5 == 5`      | `True` |
| `!=`     | Not equal to     | `5 != 10`     | `True` |
| `>`      | Greater than     | `10 > 5`      | `True` |
| `<`      | Less than        | `5 < 10`      | `True` |
| `>=`     | Greater than or equal to | `10 >= 10`    | `True` |
| `<=`     | Less than or equal to    | `5 <= 5`      | `True` |

### Usage Examples:

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

## Logical (Boolean) Operators

Logical operators combine boolean values or comparison results to form more complex expressions.

| Operator | Description                                   | Example                  | Result  |
| :------- | :-------------------------------------------- | :----------------------- | :------ |
| `and`    | Returns `True` if **both** conditions are `True`. | `True and False`         | `False` |
| `or`     | Returns `True` if **at least one** condition is `True`. | `True or False`          | `True`  |
| `not`    | Inverts the boolean value (`True` becomes `False`, `False` becomes `True`). | `not True`               | `False` |

### Usage Examples:

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

## Using Booleans in Conditionals (`if`/`elif`/`else`)

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

## "Truthy" and "Falsy" Values (Boolean Evaluation of Other Types)

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

### "Truthy" and "Falsy" Examples:

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