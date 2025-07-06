# Basic Syntax

Python is a high-level, interpreted programming language with a simple and intuitive syntax. It's widely used in data science, automation, artificial intelligence, and scientific programming.

Let's start with the classic "Hello, world\!".

```python
print("Hello, world!")
```

## Command Line

It's possible to execute Python commands directly from the terminal.

In the terminal, type:

```bash
python3
```

You can also run a saved script:

```bash
python3 hello.py
```

Or start a Jupyter Notebook with:

```bash
jupyter-notebook
```

## Jupyter Notebook

Jupyter Notebook is a powerful tool for data analysis, as it allows you to write code and explanatory text in a single interactive environment.

Each cell can contain **code** (Python) or **text** (Markdown).

To run a cell: `Shift + Enter`

  * **Run cell and go to the next**:
    `Shift` + `Enter`

  * **Run cell and stay there**:
    `Ctrl` + `Enter` (or `Cmd` + `Enter` on Mac)

  * **Insert new cell below**:
    `Esc`, then press `B`

  * **Insert new cell above**:
    `Esc`, then press `A`

  * **Change cell to Markdown**:
    `Esc`, then press `M`

  * **Change cell to Code**:
    `Esc`, then press `Y`

These shortcuts greatly help speed up writing and editing your notebook\!

## Indentation

Indentation defines code blocks in Python. Indentation errors are common when starting out.

Use 4 spaces or `Tab`.

Example:

```python
# Correct
if True:
    print("Correctly indented!")

# Incorrect
if True:
print("Indentation error!") # This causes an error
```

## Comments

Comments are text snippets ignored by the Python interpreter. They serve to explain what the code does.

There are two main types:

  * Single-line comment (`#`)
  * Multi-line comment (with `"""` or `'''`, although this is more commonly used for docstrings)

**Tip**: Write clear and direct comments, especially when the code is complex.

  * **Comment selected line(s)**:
      * `Ctrl` + `/` (Windows/Linux)(US keyboard layout)
      * `Ctrl` + `;` (Windows/Linux)(ABNT keyboard layout)
      * `Cmd` + `/` (Mac)

<!-- end list -->

```python
"""
This is a multi-line
comment block. It can be used
to document larger sections.
"""
print("Block commented above.")
```

```
Block commented above.
```