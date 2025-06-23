# Arithmetic Operators in Python

Arithmetic operators are symbols that perform mathematical operations on values (numbers). They are essential for any type of calculation, from simple sums to more complex operations.

## The Main Arithmetic Operators

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

## Detailed Examples

Let's see each operator in action:

```python
# Defining some variables for the examples
num1 = 20
num2 = 7
num3 = 2.5
```

### Addition (`+`)

```python
result_addition = num1 + num2
print(f"Addition: {num1} + {num2} = {result_addition}") # 20 + 7 = 27

# Addition also works with floats
result_addition_float = num1 + num3
print(f"Addition with float: {num1} + {num3} = {result_addition_float}") # 20 + 2.5 = 22.5
```

### Subtraction (`-`)

```python
result_subtraction = num1 - num2
print(f"Subtraction: {num1} - {num2} = {result_subtraction}") # 20 - 7 = 13

result_subtraction_float = num2 - num3
print(f"Subtraction with float: {num2} - {num3} = {result_subtraction_float}") # 7 - 2.5 = 4.5
```

### Multiplication (`*`)

```python
result_multiplication = num1 * num2
print(f"Multiplication: {num1} * {num2} = {result_multiplication}") # 20 * 7 = 140

result_multiplication_float = num1 * num3
print(f"Multiplication with float: {num1} * {num3} = {result_multiplication_float}") # 20 * 2.5 = 50.0
```

### Division (`/`)

**Remember: Always returns a `float`\!**

```python
result_division = num1 / num2
print(f"Division: {num1} / {num2} = {result_division}") # 20 / 7 = 2.8571...

result_exact_division = 10 / 2
print(f"Exact Division: 10 / 2 = {result_exact_division}") # 10 / 2 = 5.0 (still a float)
```

### Integer Division (`//`) - Floor Division

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

### Modulo (`%`) - Remainder of Division

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

### Exponentiation (`**`)

```python
result_exp = num2 ** 2 # 7 raised to the power of 2 (7 squared)
print(f"Exponentiation: {num2} ** 2 = {result_exp}") # 7 ** 2 = 49

result_exp_cubed = 3 ** 3 # 3 raised to the power of 3 (3 cubed)
print(f"Exponentiation: 3 ** 3 = {result_exp_cubed}") # 3 ** 3 = 27

# With floats
result_exp_float = 2 ** num3 # 2 raised to the power of 2.5
print(f"Exponentiation with float: 2 ** {num3} = {result_exp_float}") # 2 ** 2.5 = 5.65685...
```

## Order of Precedence for Arithmetic Operators

Just like in mathematics, operators in Python follow an order of precedence to determine which operation is performed first in a complex expression.

1.  **Parentheses `()`**: Force a specific order of operations.
2.  **Exponentiation `**`**
3.  **Multiplication `*`**, **Division `/`**, **Floor Division `//`**, **Modulo `%`**: Evaluated from left to right.
4.  **Addition `+`**, **Subtraction `-`**: Evaluated from left to right.

**Tip:** When in doubt, or to ensure code clarity, use parentheses to group operations, even if the default precedence would already resolve them in the desired order.

### Precedence Example:

```python
calculation1 = 5 + 3 * 2 # 3 * 2 is done first (6), then 5 + 6
print(f"5 + 3 * 2 = {calculation1}") # Output: 11

calculation2 = (5 + 3) * 2 # Parentheses force 5 + 3 first (8), then 8 * 2
print(f"(5 + 3) * 2 = {calculation2}") # Output: 16

calculation3 = 20 / 2 ** 2 # 2 ** 2 is done first (4), then 20 / 4
print(f"20 / 2 ** 2 = {calculation3}") # Output: 5.0
```

Mastering arithmetic operators is fundamental, as they are the basis for any program involving calculations, from a simple currency converter to complex scientific algorithms.