# Input and Output in Python

Effective interaction with a program involves receiving data from the user (input) and displaying results or information back to them (output). Python provides simple yet powerful built-in functions for these fundamental tasks: `input()` for reading data and `print()` for displaying it.

## Getting Input: The `input()` Function

The `input()` function is Python's standard way to get user input from the console.

```python
# Basic usage of input()
user_name = input("Please enter your name: ")
print("Hello,", user_name)
```

### Key Characteristics of `input()`:

  * **Always Returns a String:** This is the most crucial point. No matter what the user types (even if it looks like a number, `True`, or `False`), `input()` will always return it as a string.

    ```python
    # User types '123'
    num_str = input("Enter a number: ")
    print(f"You entered: {num_str}")
    print(f"Type of num_str: {type(num_str)}") # Output: <class 'str'>
    ```

  * **Prompting the User:** The string argument passed to `input()` is displayed to the user as a prompt. This is vital for making your programs user-friendly, guiding them on what to enter.

    ```python
    favorite_color = input("What's your favorite color? ")
    print(f"Your favorite color is {favorite_color}.")
    ```

### Handling Numerical Input: Type Conversion is a Must\!

Since `input()` returns a string, you **must** explicitly convert the input to a numeric type (`int` or `float`) if you intend to perform mathematical operations.

```python
# Correctly converting input to an integer
age_str = input("Enter your age: ") # age_str is "25" (string)
age_int = int(age_str)              # age_int is 25 (integer)
print("In 10 years, you will be", age_int + 10, "years old.")

# Combining input and conversion
temperature = float(input("Enter today's temperature in Celsius: "))
print(f"Today's temperature in Fahrenheit is: {(temperature * 9/5) + 32:.2f}°F")
```

**Important:** If the user enters text that cannot be converted to the target numeric type (e.g., typing "hello" when `int()` is expected), a `ValueError` will occur. We'll learn how to handle such errors with `try-except` blocks later, but for now, emphasize valid input.

## Displaying Output: The `print()` Function

The `print()` function is Python's versatile tool for displaying information on the console.

```python
# Basic print statements
print("Hello, Python!")
variable_value = 42
print("The value is:", variable_value)
```

### Key Parameters of `print()`:

The `print()` function has several useful optional parameters that give you control over the output formatting:

1.  **`objects` (required, positional):** These are the items you want to print. You can pass multiple objects separated by commas.

      * When multiple objects are passed, `print()` automatically places a separator between them (by default, a single space).


    ```python
    city = "São Carlos"
    state = "SP"
    country = "Brazil"
    print("Your location:", city, state, country) # Output: Your location: São Carlos SP Brazil
    ```

2.  **`sep` (separator):** Specifies the string to be used between multiple objects. The default is a single space (`' '`).

    ```python
    print("Year", "Month", "Day", sep="-") # Output: Year-Month-Day
    print("email", "example", "com", sep="@.") # Output: email@example.com
    ```

3.  **`end` (end string):** Specifies what to print at the end of the output. The default is a newline character (`'\n'`), which makes each `print()` call start on a new line.

    ```python
    print("This is the first line.")
    print("This is the second line.")

    # Using end to prevent newline
    print("Starting a sentence...", end="")
    print(" ...and continuing it on the same line.")
    # Output:
    # Starting a sentence... ...and continuing it on the same line.

    # Custom end character
    print("Processing file 1", end="...")
    print(" Done!") # Output: Processing file 1... Done!
    ```

4.  **`file`:** Specifies a file-like object (stream) where the output will be sent. By default, it's `sys.stdout` (the console). This is useful for writing output directly to files.

    ```python
    # Example (will be covered more in file I/O)
    # with open("output.txt", "w") as f:
    #     print("This text goes into the file.", file=f)
    ```

5.  **`flush`:** A boolean parameter (default `False`). If `True`, the stream is forcibly flushed. This is usually only necessary in specific scenarios like long-running processes or network communication where immediate output is critical.

### Advanced Output Formatting (Revisiting for `print()` context):

While `print()` can simply concatenate items with spaces, using **f-strings** (formatted string literals) or the **`.format()` method** offers superior control and readability for complex output.

  * **f-strings (Recommended for Python 3.6+):**

      * Embed expressions directly within string literals, prefixed with `f`.
      * Allow for powerful formatting options (e.g., decimal precision, alignment).

    <!-- end list -->

    ```python
    item = "Laptop"
    price = 1200.75
    stock = 50

    print(f"Product: {item:<15} | Price: ${price:.2f} | In Stock: {stock:3d}")
    # Output: Product: Laptop          | Price: $1200.75 | In Stock:  50
    ```

  * **`.format()` Method:**

      * Uses curly braces `{}` as placeholders that are filled by arguments passed to the `.format()` method.
      * Offers similar formatting capabilities to f-strings.

    <!-- end list -->

    ```python
    print("Report Date: {}-{:02d}-{:02d}".format(2025, 6, 22)) # :02d pads with leading zero
    # Output: Report Date: 2025-06-22
    ```

### Escape Sequences in `print()`:

Special characters can be inserted into strings using escape sequences, which begin with a backslash (`\`).

  * `\n`: Newline (moves to the next line).
  * `\t`: Tab (inserts a tab space).
  * `\\`: Backslash.
  * `\"` or `\'`: Literal quote (useful when you need to embed quotes within a string that uses the same type of quotes).


```python
print("This is line 1.\nThis is line 2.")
print("Column1\tColumn2\tColumn3")
print("He said, \"Hello!\"")
```

## Best Practices for Input/Output

  * **Clear Prompts:** Always provide clear and concise prompts for `input()` to guide the user.
  * **Handle Types:** Anticipate the data type of user input and perform necessary conversions.
  * **Informative Output:** Make your `print()` statements descriptive and easy to understand.
  * **Formatting for Readability:** Utilize f-strings or `.format()` for well-structured and readable output, especially when mixing text and variables.
  * **Use `sep` and `end`:** Leverage these parameters to control the layout of your output effectively.

By mastering `input()` and `print()`, students will gain the ability to create interactive programs that communicate effectively with the user.