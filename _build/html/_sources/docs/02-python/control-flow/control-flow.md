# Conditionals and Loops

## Introduction to Conditionals (if, else)

Conditionals are fundamental control flow blocks in Python. They allow your program to make decisions and execute different code blocks based on certain conditions.

### What are Conditionals?

Think of conditionals as questions your program asks. If the answer is "yes" (true), it does one thing; if the answer is "no" (false), it might do something else.

### The `if` Structure

The `if` is the most basic statement. It executes a block of code only if the specified condition is **true**.

**Syntax:**

```python
if condition:
    # Code to be executed if the condition is true
    pass
```

**Example:**

```python
age = 18

if age >= 18:
    print("You are of legal age and can drive.")
```

```
You are of legal age and can drive.
```

In this example, since `age` is 18, the condition `age >= 18` is true, and the message is printed.

### The `if-else` Structure

The `else` allows you to define a block of code to be executed when the `if` condition is **false**.

**Syntax:**

```python
if condition:
    # Code to be executed if the condition is true
else:
    # Code to be executed if the condition is false
```

**Example:**

```python
temperature = 25

if temperature > 30:
    print("It's very hot! Drink plenty of water.")
else:
    print("The temperature is pleasant.")
```

```
The temperature is pleasant.
```

Here, `temperature > 30` is false, so the `else` message is displayed.

### The `if-elif-else` Structure

For multiple decision paths, we use `elif` (short for "else if"). It allows you to check several conditions in sequence.

**Syntax:**

```python
if first_condition:
    # Code if the first condition is true
elif second_condition:
    # Code if the second condition is true (and the first is false)
else:
    # Code if none of the previous conditions are true
```

**Example:**

```python
grade = 75

if grade >= 90:
    print("Concept A - Excellent!")
elif grade >= 70:
    print("Concept B - Good!")
elif grade >= 50:
    print("Concept C - Sufficient.")
else:
    print("Concept D - Failed.")
```

```
Concept B - Good!
```

In this case, the `grade` fits the second condition (`grade >= 70`), displaying "Concept B - Good\!".

## Repetition Structures (Loops)

Loops are used to execute a block of code repeatedly. This is extremely useful when you need to process a list of items, repeat an action until a condition is met, and much more.

### What are Loops?

Imagine you have a task to do several times. Instead of writing the same code repeatedly, you use a loop to automate that repetition.

### The `for` Loop

The `for` loop is used to iterate over a sequence (such as a list, tuple, string, or a range of numbers).

**Syntax:**

```python
for item in sequence:
    # Code to be executed for each item in the sequence
    pass
```

**Example with list:**

```python
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(f"I like {fruit}.")

squares = [x**2 for x in range(5)]
```

**Example with `range()`:**

The `range()` function generates a sequence of numbers.

```python
# Count from 0 to 4 (exclusive of 5)
for i in range(5):
    print(i)

print("-" * 20)

# Count from 1 to 5 (inclusive of 1, exclusive of 6)
for i in range(1, 6):
    print(i)

print("-" * 20)

# Count from 0 to 10, stepping by 2
for i in range(0, 11, 2):
    print(i)
```

### The `while` Loop

The `while` loop executes a block of code as long as a specified condition is **true**. It continues repeating until the condition becomes false.

**Syntax:**

```python
while condition:
    # Code to be executed as long as the condition is true
    pass
```

**Example:**

```python
counter = 0

while counter < 5:
    print(f"Counter: {counter}")
    counter += 1 # It's crucial to update the condition to avoid an infinite loop!
```

In this example, the loop will continue as long as `counter` is less than 5. In each iteration, `counter` is incremented by 1.

## Loop Control: `break` and `continue`

Sometimes, within a loop, you need more refined control over when to stop the iteration or skip to the next one. This is where `break` and `continue` come in.

### `break`

The `break` statement is used to **completely terminate** the execution of the current loop. Program control jumps to the statement immediately after the loop.

**Example:**

```python
for number in range(10):
    if number == 5:
        print("Found 5! Stopping the loop.")
        break
    print(number)
```

In this case, the loop will print numbers from 0 to 4, and when `number` is 5, it prints the message and exits the loop immediately, without printing 5 or any subsequent number.

### `continue`

The `continue` statement is used to **skip the current iteration** of the loop and proceed to the next iteration. The rest of the code within the loop for the current iteration is not executed.

**Example:**

```python
for i in range(10):
    if i % 2 == 0:  # Checks if the number is even
        print(f"Skipping even number: {i}")
        continue
    print(f"Odd number: {i}")
```

Here, if `i` is even, the message "Skipping even number..." is printed, and `continue` causes the loop to skip the rest of the code for that iteration and move to the next. Only odd numbers will have the "Odd number:" message printed.

### The `match-case` Statement

Starting from Python 3.10, the `match-case` statement provides a new way to control program flow by matching a subject against a series of patterns. It's a more elegant and powerful switch/case statement.

The `match` statement takes an expression and compares its value against successive patterns given as `case` blocks.

**Basic Syntax**

```python
match subject_expression:
    case pattern_1:
        # Code to execute if pattern_1 matches
    case pattern_2:
        # Code to execute if pattern_2 matches
    case _:
        # Optional: Code to execute if no pattern matches (the wildcard)
```

The `_` is a **wildcard pattern** that matches anything and is often used as a final, catch-all `case` to handle unexpected values.

#### Example 1: Simple `if-elif-else` Replacement

Let's see how `match-case` can clean up a common conditional structure, such as handling different HTTP status codes.

```python
def handle_http_status(status_code):
    """Handles an HTTP status code using a match statement."""
    match status_code:
        case 200:
            return "OK: Request was successful."
        case 404:
            return "Error: Resource not found."
        case 500:
            return "Error: Internal server error."
        case _: # The wildcard case, like a final 'else'
            return f"Unknown status code: {status_code}"

# Test the function with different values
print(handle_http_status(200))
print(handle_http_status(404))
print(handle_http_status(503))
```

**Output:**

```
OK: Request was successful.
Error: Resource not found.
Unknown status code: 503
```

This is much more readable than a series of `if status_code == 200: ... elif status_code == 404: ...` statements.

#### Pattern Matching within a `for` Loop

This is where `match-case` truly shines, allowing you to elegantly handle items with different structures while iterating over a collection. Let's process a list containing tuples, dictionaries, and lists.

```python
# A list of heterogeneous data structures
mixed_data = [
    (1, 2),
    {'name': 'Alice', 'age': 30},
    [10, 20, 30],
    (42,),
    {'city': 'London'},
    ('a', 'b', 'c'),
    (5, 5)
]

print("--- Processing mixed data structures ---")

# Iterate through the list and use match to handle each item's structure
for item in mixed_data:
    print(f"\nProcessing item: {item}")
    match item:
        # Match a tuple with exactly two elements
        case (x, y):
            print(f"  -> Found a tuple with two elements: x={x}, y={y}")

        # Match a tuple with two equal elements (using a "guard")
        case (x, y) if x == y:
            print(f"  -> Found a tuple with two IDENTICAL elements: {x} and {y}")

        # Match a dictionary with specific keys
        case {'name': name, 'age': age}:
            print(f"  -> Found a person dictionary: {name} is {age} years old.")

        # Match a list with exactly three elements
        case [a, b, c]:
            print(f"  -> Found a list with three elements: {a}, {b}, {c}")

        # Match a tuple with a single element
        case (value,):
            print(f"  -> Found a tuple with a single value: {value}")

        # The wildcard case for any other type or structure
        case _:
            print(f"  -> Found a structure that doesn't match any pattern.")
```

**Output:**

```
--- Processing mixed data structures ---

Processing item: (1, 2)
  -> Found a tuple with two elements: x=1, y=2

Processing item: {'name': 'Alice', 'age': 30}
  -> Found a person dictionary: Alice is 30 years old.

Processing item: [10, 20, 30]
  -> Found a list with three elements: 10, 20, 30

Processing item: (42,)
  -> Found a tuple with a single value: 42

Processing item: {'city': 'London'}
  -> Found a structure that doesn't match any pattern.

Processing item: ('a', 'b', 'c')
  -> Found a structure that doesn't match any pattern.

Processing item: (5, 5)
  -> Found a tuple with two IDENTICAL elements: 5 and 5
```

#### Key Concepts in Pattern Matching

  * **Capture Patterns:** Variables like `x`, `y`, `name`, `age`, `a`, `b`, and `c` in the `case` statements are called **capture patterns**. They "capture" the values from the corresponding positions in the matched structure.
  * **Literals and Wildcards:** You can match against specific literal values (`case 200:`) or use the wildcard `_` to match any value you don't care about (e.g., `case (x, _):` would match any 2-element tuple and capture only the first element).
  * **Guards (`if`):** A guard is an optional `if` condition added to a `case` statement. The pattern must match **and** the condition must be true for the block to execute. This allows for more granular control.

The `match-case` statement makes code for complex logic more explicit, readable, and less prone to errors compared to deeply nested `if-elif-else` blocks, especially when dealing with data that has a well-defined structure.

## Summary and Next Steps

In this outline, we've covered the pillars of conditionals (`if`, `else`, `elif`) and repetition structures (`for`, `while`), as well as the important loop control tools (`break`, `continue`, `match`).

I recommend the following activities:

  * **Conditionals:**
      * Create a program that asks for the user's age and tells them if they are a child, teenager, or adult.
      * Write a program that asks for three grades and calculates the average, informing whether the student passed (average \>= 7), is in recovery (average \>= 5), or failed.
  * **Loops:**
      * Print numbers from 1 to 10 using `for` and `while`.
      * Create a loop that asks the user for numbers until they type 0. Finally, sum all the entered numbers.
      * Use `break` to exit a loop when a specific condition is met (e.g., finding a name in a list).
      * Use `continue` to skip printing numbers that are multiples of 3 in a loop from 1 to 20.