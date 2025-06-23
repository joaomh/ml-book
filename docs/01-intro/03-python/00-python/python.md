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

# References
 
* {cite:p}`matthes2015python`
* {cite:p}`ramalho2015fluent`