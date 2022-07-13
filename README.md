Hello team, most of you already know some of these things but we've seen a pattern of bad code which mixes up different coding styles and most of it does not belong to the style convention of the language.
Example (pep_8) in python. So here is a small python guide.


Python Guide:
1. Use 4 spaces per indentation level.
2. Variables and Function names should be lowercase, with words separated by underscores as necessary to improve readability. (snake case)
3. Imports should usually be on separate lines
```py
# Correct:
import os
import sys

# Wrong
import sys, os

# Correct:
from subprocess import Popen, PIPE
``` 
3. Use type hints when ever you can.

> Note: The Python runtime does not enforce function and variable type
> annotations. They can be used by third party tools such as type
> checkers, IDEs, linters, etc.
> In other words variable "x" of type string can be assigned to a int value because Python's typing is for code readability there's not type checking in the language.

```py
greeting = "Hello, {}, you're {} years old"

def greet(user, age):
    return greeting.format(user, age)

name = input("Your name?")
age = int(input("How old are you?"))

print(greet(name, age))
```

```py
greeting = "Hello, {}, you're {} years old"

def greet(user:str, age:int) -> str:
    return greeting.format(user, age)

name:str = input("Your name?")
age:int = int(input("How old are you?"))

print(greet(name, age))
```

```py
from typing import Dict, List

dict_of_users: Dict[int,str] = {
    1: "Jerome",
    2: "Lewis"
}

list_of_users: List[str] = [
    "Jerome", "Lewis"
]
```

4. [Avoid using pip freeze > requirements.txt,](https://medium.com/@tomagee/pip-freeze-requirements-txt-considered-harmful-f0bce66cf895) instead at the time of installing a new module write it into requirements.txt file with exact version and commit it immediately. 
5. Avoid coupling of code, For example a Django app named (accounts) if we want to make it portable and reusable it should be decoupled which means it should not have imports from anywhere except itself.
