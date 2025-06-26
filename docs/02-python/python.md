# Introduction to Python

  * Python was created by Guido van Rossum, a Dutch programmer, in the late 1980s.

  * Guido started working on Python as a hobby project during Christmas 1989. He wanted to create a language that was easy to read and write and capable of handling complex tasks (as a successor to the ABC language).

  * The first public version of Python (0.9.0) was released in 1991.

**Python is a multi-paradigm programming language**: This means that Python supports several programming styles or "paradigms." A paradigm is a way of thinking about and structuring code. Python is not limited to a single style, allowing developers to choose the best paradigm for each situation.

**Object-Oriented Programming (OOP)**: Python allows the creation of classes and objects, encapsulation, inheritance, and polymorphism.

```python
class Animal:
    def __init__(self, nome):
        self.nome = nome
    def falar(self):
        pass
```

**Structured Programming**: Python supports control structures like loops `(for, while)` and conditionals `(if, else)`, which are characteristics of structured programming.

```python
# Welcome program
def main():
    # Data input
    nome = input("Enter your name: ")
    idade = int(input("Enter your age: "))

    # Conditional to check age
    if idade >= 18:
        mensagem = f"Hello, {nome}! You are an adult."
    else:
        mensagem = f"Hello, {nome}! You are a minor."

    # Data output
    print(mensagem)

# Call the main function
main()
```

```
Enter your name: Joao
Enter your age: 21


Hello, Joao! You are an adult.
```

**Functional Programming**: Python supports first-class functions (functions that can be passed as arguments), anonymous functions (`lambda`), and operations like `map`, `filter`, and `reduce`. Example:

```python
lista = [1, 2, 3, 4]
dobrado = list(map(lambda x: x * 2, lista))  # [2, 4, 6, 8]
```

Python is known for its ability to "glue" different systems or components together. For example, you can call C/C++ code using ctypes or Cython, or integrate Python with Java using Jython. This makes Python ideal for systems that combine various technologies.

It uses dynamic name resolution (late binding), which links method and variable names during program execution. That is, variable and method names are resolved at runtime, not at compile time. This allows greater flexibility, such as the dynamic creation of attributes or methods. Example:

```python
class Exemplo:
    pass

obj = Exemplo()
obj.novo_atributo = 42  # Attribute created dynamically
```
### Basic Syntax

Python is a high-level, interpreted programming language with a simple and intuitive syntax. It's widely used in data science, automation, artificial intelligence, and scientific programming.

Let's start with the classic "Hello, world\!".

```python
print("Hello, world!")
```

### Command Line

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

### Jupyter Notebook

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

### Indentation

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

### Comments

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

### References
 
* {cite:p}`matthes2015python`
* {cite:p}`ramalho2015fluent`