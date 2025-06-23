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