# Essential Built-in Functions in Python

Python offers a series of "built-in" functions that are always available for use, without the need to import modules. They are fundamental for common operations and manipulating different data types.

## `print()`

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

## `type()`

The `type()` function is used to return the type of an object. It is useful for debugging and understanding what kind of data you are working with.

  * **Syntax:** `type(object)`
  * **`object`:** The item whose type you want to determine.
  * **Return:** The type of the object.

<!-- end list -->

```python
print(type("Hello"))
```

## `len()`

The `len()` function returns the number of items (the "length") of an object. It works for sequences like strings, lists, tuples, dictionaries, and sets.

  * **Syntax:** `len(s)`
  * **`s`:** The object whose item count you want to get.
  * **Return:** An integer representing the number of items.

<!-- end list -->

```python
print(len("Python"))
```

## `int()`

The `int()` function is used to convert a value to an integer type. It can convert floating-point numbers (by truncating the decimal part) or strings that represent whole numbers.

  * **Syntax:** `int(x, base=10)`
  * **`x`:** The value to be converted. It can be a number, or a string that represents a number.
  * **`base` (optional):** If `x` is a string, the numeric base (e.g., 2 for binary, 16 for hexadecimal). The default is 10.
  * **Return:** An integer value. If the conversion is not possible, it raises a `ValueError`.

<!-- end list -->

```python
print(int("123"))
```

## `str()`

The `str()` function is used to convert a value to its string representation.

  * **Syntax:** `str(object)`
  * **`object`:** The item to be converted to a string.
  * **Return:** The string representation of the object.

<!-- end list -->

```python
print(str(123))
```

## `float()`

The `float()` function is used to convert a value to a floating-point number type (decimal number). It can convert integers or strings that represent decimal numbers.

  * **Syntax:** `float(x)`
  * **`x`:** The value to be converted. It can be an integer, or a string that represents a number.
  * **Return:** A floating-point value. If the conversion is not possible, it raises a `ValueError`.

<!-- end list -->

```python
print(float("3.14"))
```

## `abs()`

The `abs()` function returns the absolute value of a number.

  * **Syntax:** `abs(x)`
  * **`x`:** A number (integer, float, or complex).
  * **Return:** The absolute value of `x`.

<!-- end list -->

```python
print(abs(-10))
```

## `max()`

The `max()` function returns the largest item in an iterable or the largest of two or more arguments.

  * **Syntax:** `max(iterable, *[, key, default])` or `max(arg1, arg2, *args[, key])`
  * **`iterable`:** A collection of items (list, tuple, etc.).
  * **`arg1`, `arg2`, `*args`:** Individual arguments.
  * **Return:** The largest item.

<!-- end list -->

```python
print(max(1, 5, 10))
```

## `min()`

The `min()` function returns the smallest item in an iterable or the smallest of two or more arguments.

  * **Syntax:** `min(iterable, *[, key, default])` or `min(arg1, arg2, *args[, key])`
  * **`iterable`:** A collection of items (list, tuple, etc.).
  * **`arg1`, `arg2`, `*args`:** Individual arguments.
  * **Return:** The smallest item.

<!-- end list -->

```python
print(min(1, 5, 10))
```

## `sum()`

The `sum()` function returns the sum of all items in an iterable.

  * **Syntax:** `sum(iterable, /[, start])`
  * **`iterable`:** A collection of numeric items (list, tuple, etc.).
  * **`start` (optional):** A number that is added to the sum of the items. The default is 0.
  * **Return:** The sum of the items, plus the `start` value.

<!-- end list -->

```python
print(sum([1, 2, 3]))
```

## `range()`

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