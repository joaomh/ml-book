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

## Summary and Next Steps

In this outline, we've covered the pillars of conditionals (`if`, `else`, `elif`) and repetition structures (`for`, `while`), as well as the important loop control tools (`break`, `continue`).

I recommend the following activities:

  * **Conditionals:**
      * Create a program that asks for the user's age and tells them if they are a child, teenager, or adult.
      * Write a program that asks for three grades and calculates the average, informing whether the student passed (average \>= 7), is in recovery (average \>= 5), or failed.
  * **Loops:**
      * Print numbers from 1 to 10 using `for` and `while`.
      * Create a loop that asks the user for numbers until they type 0. Finally, sum all the entered numbers.
      * Use `break` to exit a loop when a specific condition is met (e.g., finding a name in a list).
      * Use `continue` to skip printing numbers that are multiples of 3 in a loop from 1 to 20.