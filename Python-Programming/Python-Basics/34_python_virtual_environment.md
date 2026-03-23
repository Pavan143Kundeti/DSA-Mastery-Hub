# Python Virtual Environment

## What is a Virtual Environment?

**Definition:** A virtual environment is an isolated Python environment for each project.

**Think of it as:** A separate container for each Python project.

---

## Why Use Virtual Environments?

| Problem | Solution |
|---------|----------|
| Package version conflicts | Each project has its own packages |
| System Python pollution | Keep system Python clean |
| Project portability | Easy to share and reproduce |
| Different Python versions | Test with multiple versions |

### Example Problem
```
Project A needs Django 3.2
Project B needs Django 4.0
Without virtual environments: CONFLICT!
```

---

## Creating Virtual Environment

Use Python's built-in `venv` module.

### Command
```bash
python -m venv project_name
```

### Example
```bash
python -m venv myproject
```

**Result:** Creates folder structure:
```
myproject/
├── Include/
├── Lib/
├── Scripts/          # Windows
├── bin/              # Mac/Linux
├── .gitignore
└── pyvenv.cfg
```

---

## Activating Virtual Environment

### Windows
```bash
myproject\Scripts\activate
```

### Mac/Linux
```bash
source myproject/bin/activate
```

### After Activation
```bash
(myproject) C:\Users\Your Name>
```

**Note:** Prompt shows virtual environment name in parentheses.

---

## Installing Packages

Once activated, use `pip` to install packages.

```bash
(myproject) > pip install requests
(myproject) > pip install django==4.0
(myproject) > pip install numpy pandas
```

**Important:** Packages install only in the virtual environment.

---

## Using Packages

Create and run Python files normally.

### Example: test.py
```python
import requests

response = requests.get('https://api.github.com')
print(response.status_code)
```

### Run
```bash
(myproject) > python test.py
```

---

## Deactivating Virtual Environment

```bash
(myproject) > deactivate
```

**Result:** Returns to system Python.
```bash
C:\Users\Your Name>
```

**Note:** Virtual environment still exists, just not active.

---

## Virtual Environment Commands

| Command | Purpose |
|---------|---------|
| `python -m venv name` | Create virtual environment |
| `activate` | Activate environment |
| `deactivate` | Deactivate environment |
| `pip list` | Show installed packages |
| `pip freeze` | List packages with versions |

---

## Managing Dependencies

### Create Requirements File
```bash
(myproject) > pip freeze > requirements.txt
```

### requirements.txt Example
```
requests==2.28.1
django==4.0.6
numpy==1.23.2
pandas==1.4.3
```

### Install from Requirements
```bash
(myproject) > pip install -r requirements.txt
```

---

## Project Workflow

### 1. Create Project
```bash
mkdir myproject
cd myproject
python -m venv venv
```

### 2. Activate Environment
```bash
# Windows
venv\Scripts\activate

# Mac/Linux
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install package_name
```

### 4. Work on Project
```python
# Write your Python code
```

### 5. Save Dependencies
```bash
pip freeze > requirements.txt
```

### 6. Deactivate When Done
```bash
deactivate
```

---

## Best Practices

### Naming Conventions
```bash
python -m venv venv          # Common
python -m venv .venv         # Hidden folder
python -m venv project_env   # Descriptive
```

### Project Structure
```
myproject/
├── venv/                    # Virtual environment
├── src/                     # Source code
├── tests/                   # Test files
├── requirements.txt         # Dependencies
├── README.md               # Documentation
└── .gitignore              # Git ignore file
```

### .gitignore for Virtual Environments
```
# Virtual environments
venv/
.venv/
env/
ENV/
```

---

## Common Commands

### Check Active Environment
```bash
which python    # Mac/Linux
where python    # Windows
```

### List Installed Packages
```bash
pip list
pip freeze
```

### Upgrade Package
```bash
pip install --upgrade package_name
```

### Uninstall Package
```bash
pip uninstall package_name
```

---

## Deleting Virtual Environment

Simply delete the folder:

### Command Line
```bash
# Windows
rmdir /s /q myproject

# Mac/Linux
rm -rf myproject
```

### File Explorer
Delete the virtual environment folder manually.

**Note:** No other projects are affected.

---

## Multiple Python Versions

### Specify Python Version
```bash
python3.9 -m venv myproject39
python3.10 -m venv myproject310
```

### Check Python Version in Environment
```bash
(myproject) > python --version
```

---

## Virtual Environment Tools

### Alternative Tools
| Tool | Description |
|------|-------------|
| `venv` | Built-in (recommended) |
| `virtualenv` | Third-party, more features |
| `conda` | Anaconda package manager |
| `pipenv` | Combines pip and virtualenv |
| `poetry` | Modern dependency management |

### Using virtualenv
```bash
pip install virtualenv
virtualenv myproject
```

### Using conda
```bash
conda create --name myproject python=3.9
conda activate myproject
```

---

## Troubleshooting

### Environment Not Activating
```bash
# Try full path
C:\path\to\myproject\Scripts\activate

# Check if Scripts folder exists
dir myproject
```

### Package Not Found
```bash
# Make sure environment is activated
# Check with:
pip list

# Reinstall if needed
pip install package_name
```

### Permission Errors
```bash
# Run as administrator (Windows)
# Use sudo (Mac/Linux) - not recommended
# Or install with --user flag
pip install --user package_name
```

---

## Real-World Example

### Django Project Setup
```bash
# Create project directory
mkdir django_blog
cd django_blog

# Create virtual environment
python -m venv venv

# Activate
source venv/bin/activate  # Mac/Linux
# venv\Scripts\activate   # Windows

# Install Django
pip install django

# Create Django project
django-admin startproject blog .

# Save dependencies
pip freeze > requirements.txt

# Work on project...

# Deactivate when done
deactivate
```

---

## Quick Reference

### Essential Commands
```bash
# Create
python -m venv project_name

# Activate (Windows)
project_name\Scripts\activate

# Activate (Mac/Linux)
source project_name/bin/activate

# Install packages
pip install package_name

# Save dependencies
pip freeze > requirements.txt

# Install from requirements
pip install -r requirements.txt

# Deactivate
deactivate

# Delete
rm -rf project_name
```

---

## Key Takeaways

### ✅ Remember
- **Virtual environments** isolate project dependencies
- **venv** is Python's built-in tool
- **Activate** before installing packages
- **requirements.txt** saves dependencies
- **Deactivate** when switching projects
- **Delete** by removing folder
- **Always use** for Python projects

### 🎯 Interview Important
- Purpose of virtual environments
- How to create and activate environments
- Difference between system Python and virtual environment
- Managing project dependencies
- Best practices for project structure
- Alternative tools (virtualenv, conda, pipenv)
- Why virtual environments prevent conflicts

---

**Use virtual environments for every Python project to avoid dependency conflicts!**