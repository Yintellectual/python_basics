# `python something.py` vs `python -m somepackage.something`
---
## **What is a Module in Python?**
A module in Python is a unit of organization that groups related code (functions, classes, variables, etc.) into a reusable and importable unit. A module can be:

1. A Single .py File:
- This is the simplest form of a module.
- Example: math_utils.py containing functions like add() and multiply().

2. A Folder with an __init__.py File:
- A folder containing an __init__.py file is treated as a package, which is a special kind of module.
- The __init__.py file can be empty or contain initialization code for the package.
- Example: A folder my_package/ with __init__.py and other .py files (e.g., module1.py, module2.py).

3. A Collection of Submodules:
- A module can also include submodules (other .py files or subfolders with __init__.py).
- Example: A folder my_package/ containing __init__.py, module1.py, and a subfolder utils/ with its own __init__.py and helpers.py.
---
## **`python something.py`**
- Runs the script as a **standalone file**.
- **`__name__`**: Set to `"__main__"`.
- **Package Context**: None (not part of a package).
- **Relative Imports**: Fails (no parent package).
- **Use Case**: Standalone scripts.

## **`python -m somepackage.something`**
- Runs the script as a **module within a package**.
- **`__name__`**: Set to `"somepackage.something"`.
- **Package Context**: Established (part of a package).
- **Relative Imports**: Works (parent package is recognized).
- **Use Case**: Modules within a package.

---

## **Key Differences**
| Feature               | `python something.py`          | `python -m somepackage.something` |
|-----------------------|--------------------------------|-----------------------------------|
| **`__name__`**        | `"__main__"`                  | `"somepackage.something"`         |
| **`if __name__ = "__main__": ` block| triggered| triggered|
| **Package Context**   | No                            | Yes                               |
| **Relative Imports**  | Fails                         | Works                             |
| **Use Case**          | Standalone scripts            | Modules within a package          |

---

## **When to Use**
- Use `python something.py` for **standalone scripts**.
- Use `python -m somepackage.something` for **modules within a package** (recommended for packages).

## **In VSCode**
- use terminal
- Python Debugger: Debug using launch.json
