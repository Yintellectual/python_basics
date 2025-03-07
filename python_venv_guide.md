# Python Virtual Environment Best Practices

## What is a Python Virtual Environment?
A Python virtual environment is an **isolated environment** that allows you to manage dependencies for a specific project without affecting the global Python installation or other projects.

---

## Why Use a Virtual Environment?
- **Dependency Isolation**: Prevents conflicts between packages required by different projects.
- **Reproducibility**: Makes your project easier to share and run on different systems.
- **Clean Development**: Keeps your global Python installation clean and free from unnecessary packages.

---

## Best Practices for Using Virtual Environments

### 1. Create a Virtual Environment
Always create a virtual environment before running a Python project locally. Use the following command:

- terminal: 
```bash
python -m venv .venv
```
- vscode:
```Search
Python: Create Environment
Venv
[Select a python installation to create the virtual environment]
```

- By convention, the default name for a virtual environment is .venv (or venv).

- The .venv directory contains the Python interpreter, pip, and installed packages.
---
### 2. Activate the Virtual Environment
Activate the virtual environment before working on the project:

- Linux: 
```bash 
source .venv/bin/activate
```
- Windows:
```bash
.venv\Scripts\activate
```
- vscode:
```Search
Python: Select Interpreter 
[Select the interpreter under .venv]
```
---
### 3. Install Dependencies
Install the project's dependencies into the virtual environment using pip:
- If you have a requirements.txt file:
```bash
pip install -r requirements.txt
```
- If you have a pyproject.toml file (used by tools like poetry):
```bash
pip install .
```
---
### 4. Add .venv to .gitignore
Since the virtual environment is reproducible (can be recreated using requirements.txt or pyproject.toml), add .venv to your .gitignore file to avoid committing it to version control:
```gitignore
# Ignore virtual environment
.venv/
```
---
### 5. Recreate the Virtual Environment
If someone else clones your project, they can recreate the virtual environment by following steps 1 ~ 4

---
### Key Points to Remember
- A virtual environment is isolated and project-specific.

- Use .venv as the default name for the virtual environment.

- Add .venv to .gitignore because it can be recreated using dependency files (requirements.txt or pyproject.toml).

- Always activate the virtual environment before running the project.

- Document the setup process in your README.md to help collaborators.

---
### Additional Tips
- Use `pip freeze > requirements.txt` to generate a list of installed packages.

- Use tools like `poetry` or `pipenv` for more advanced dependency management.

- Automate virtual environment activation in VS Code by selecting the correct interpreter in the Command Palette (Search box) `(Ctrl + Shift + P > Python: Select Interpreter)`.

