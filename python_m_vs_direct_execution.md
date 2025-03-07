# `python something.py` vs `python -m somepackage.something`

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