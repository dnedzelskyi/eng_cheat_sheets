[Home](../index.md) > Python > [Basics](./python_basics.md)

# Python | Basics

## Setup virtual environment

```text
# Install venv module
python -m pip install virtualenv

# Setup virtual env for new project
cd <project_folder>
python -m venv .venv

# Activate virtual environment (Linux - like OS)
source ./.venv/bin/activate

# Activate virtual environment (Windows)
.\.venv\Scripts\activate

# Deactivate virtual environment
deactivate

# Store installed packages into requirements.txt
python -m pip freeze > requirements.txt

# Install packages from requirements.txt
python -m pip install -r requirements.txt
```

## Basic / Primitive Types

In Python everything is an object with hell number of properties and methods.

### Primitive Types.

1. **Integers (`int`)** - Represents whole numbers without any decimal points.
1. **Floats (`float`)** - Represents decimal numbers.
1. **Booleans (`bool`)** - Represents either **True** or **False** (actually implemented as ints 1 and 0 respectively).
1. **Strings (`str`)** - Represents sequences of characters.
1. **NoneType (`None`)** - Represents the absence of a value or a null value.

## Variables.

```python
# Declaring variables of basic types
temperature = -22 # int
income = 220000.10 # float
name = "Albert" # str
is_active = True # bool
result = None # none, null

# Using constructor functions / conversion
age = int(26)
length = float("2.5")
index_text = str(5)

# Multiple assignments
age, name, ratio = 2, "Bla Bla", 4.5
is_active = is_ready = is_valid = True

# Constants
PI = 3.14
```

## Decision-making statements.

```python
# if
if a > 10:
  # some logic

# if-else
if isActive:
  print("Active")
else:
  print("Inactive")

# if-elif-else
if score >= 0 and score < 20:
  # do something
elif score >= 20 and score < 50 :
  # do something
elif score == 9999 or score == -1:
  # do something
else:
  # do something

# Conditional Expression
c = a if a > b else b

# Python does not have a built-in switch statement
# switch-like approach using dict and lambda
def switch_grade_dict(val):
    switch_dict = {
        'A': lambda: print("Grade A : [0 , 20)"),
        'B': lambda: print("Grade B : [20 , 50)"),
        'default': lambda: print("Invalid grade")
    }

    switch_dict.get(val, switch_dict['default'])()

# Usage
switch_grade_dict('B')
```

## Loop statements.

```python
# for loop
for i in range(5):
  print(i)
# Output: 0, 1, 2, 3, 4
for fruit in ["apple", "banana", "cherry"]:
  print(fruit)

# while loop
while not is_empty and step != 10:
  # do something

# continue, break, else - loop control statements
for i in range(10):
  if i < 5:
    continue
  if i > 5:
    break
  print(i)
# Output: 5

for j in range(3, 5):
  print(j)
else:
  print("The End")
# Output: 3, 4, 'The End'

# List comprehensions
squares = [x**2 for x in range(5)]
# Output: [0, 1, 4, 9, 16]
```

## Naming Convention.

**General:**

- Use descriptive names.
- Start with a letter or underscore.
- Consists of letters, numbers, and underscores.
- Case-sensitive (count and Count are different).

**Variables, Functions, Modules:**

- snake_case
- Lowercase letters

```python
total_count = 100
is_valid = True

def calculate_summary(order_list):
  # Function implementation

import math_module
from my_module import greet, pi
```

**Constants:**

- snake_case
- Uppercase letters

```python
MAX_SIZE = 50
SEARCH_URL = "https://google.com/"
```

**Classes:**

- CamelCase

```python
class UserPreferences:
  # Class definition
```

**Private Variables, Constants, Methods and Dunder Methods:**

```python
class Order:
  _NEW = "New"

  def __init__(self):
    self._status = self._NEW
    self._creation_date = datetime.now()

  def _is_new(self):
    return self._status == self._NEW
```

## REPL

**REPL** stands for **Read-Eval-Print Loop**.

Useful commands:

```python
# type() - to check variable type
num = 25
type(num) # Output: <class 'int'>

# dir() - prints list of methods and properties for type or var.
dir(num)
dir(str)

# help() - prints pydoc.help for the python object.
help(None)
help(11)
```
