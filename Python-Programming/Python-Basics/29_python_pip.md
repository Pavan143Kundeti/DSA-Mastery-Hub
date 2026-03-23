# Python PIP

## What is PIP?

**Definition:** PIP is a package manager for Python packages/modules.

**Included:** Python 3.4+ includes PIP by default.

---

## What is a Package?

**Package:** Contains all files needed for a module.
**Module:** Python code library you can include in your project.

---

## Check if PIP is Installed

```bash
pip --version
```

**Output Example:**
```
pip 21.0.1 from /usr/local/lib/python3.9/site-packages/pip (python 3.9)
```

---

## Install PIP

If PIP is not installed, download from: https://pypi.org/project/pip/

---

## PIP Commands

| Command | Purpose | Example |
|---------|---------|---------|
| `pip install` | Install package | `pip install requests` |
| `pip uninstall` | Remove package | `pip uninstall requests` |
| `pip list` | List installed packages | `pip list` |
| `pip show` | Show package info | `pip show requests` |
| `pip freeze` | List with versions | `pip freeze` |
| `pip upgrade` | Update package | `pip install --upgrade requests` |

---

## Download a Package

```bash
pip install camelcase
```

**What happens:**
1. Downloads package from PyPI
2. Installs package and dependencies
3. Makes package available for import

---

## Using a Package

After installation, import and use the package:

```python
import camelcase

c = camelcase.CamelCase()
txt = "hello world"
print(c.hump(txt))  # Output: Hello World
```

---

## Find Packages

**PyPI (Python Package Index):** https://pypi.org/

Popular packages:
- `requests` - HTTP library
- `numpy` - Numerical computing
- `pandas` - Data analysis
- `matplotlib` - Plotting
- `flask` - Web framework
- `django` - Web framework

---

## Remove a Package

```bash
pip uninstall camelcase
```

**Confirmation prompt:**
```
Uninstalling camelcase-0.2:
  Would remove:
    /path/to/camelcase/
Proceed (y/n)?
```

Type `y` to confirm removal.

---

## List Packages

```bash
pip list
```

**Output Example:**
```
Package         Version
--------------- -------
camelcase       0.2
pip             21.0.1
requests        2.25.1
setuptools      56.0.0
```

---

## Show Package Information

```bash
pip show requests
```

**Output Example:**
```
Name: requests
Version: 2.25.1
Summary: Python HTTP for Humans.
Location: /usr/local/lib/python3.9/site-packages
Requires: certifi, chardet, idna, urllib3
```

---

## Freeze Requirements

Create requirements file with all installed packages:

```bash
pip freeze > requirements.txt
```

**requirements.txt content:**
```
camelcase==0.2
requests==2.25.1
numpy==1.21.0
```

### Install from Requirements

```bash
pip install -r requirements.txt
```

---

## Upgrade Packages

### Upgrade Specific Package
```bash
pip install --upgrade requests
```

### Upgrade PIP Itself
```bash
pip install --upgrade pip
```

---

## Install Specific Version

```bash
pip install requests==2.25.1    # Exact version
pip install requests>=2.25.0    # Minimum version
pip install requests~=2.25.0    # Compatible version
```

---

## Virtual Environments

**Best Practice:** Use virtual environments to avoid conflicts.

```bash
# Create virtual environment
python -m venv myenv

# Activate (Windows)
myenv\Scripts\activate

# Activate (Mac/Linux)
source myenv/bin/activate

# Install packages
pip install requests

# Deactivate
deactivate
```

---

## Common PIP Operations

### Install Multiple Packages
```bash
pip install requests numpy pandas
```

### Install from Git Repository
```bash
pip install git+https://github.com/user/repo.git
```

### Install Local Package
```bash
pip install .
pip install -e .  # Editable install
```

### Search Packages (deprecated)
```bash
# Use PyPI website instead
# pip search was removed
```

---

## Troubleshooting

### Permission Errors
```bash
# Use --user flag
pip install --user requests

# Or use sudo (Linux/Mac)
sudo pip install requests
```

### Upgrade Issues
```bash
# Force reinstall
pip install --force-reinstall requests

# Ignore installed
pip install --ignore-installed requests
```

### Cache Issues
```bash
# Clear cache
pip cache purge

# Install without cache
pip install --no-cache-dir requests
```

---

## PIP Configuration

### pip.conf (Linux/Mac)
```
~/.pip/pip.conf
```

### pip.ini (Windows)
```
%APPDATA%\pip\pip.ini
```

**Example config:**
```ini
[global]
timeout = 60
index-url = https://pypi.org/simple/
```

---

## Quick Reference

### Essential Commands
```bash
pip install package_name     # Install
pip uninstall package_name   # Remove
pip list                     # List installed
pip show package_name        # Package info
pip freeze                   # List with versions
pip install --upgrade pip    # Update PIP
```

### Requirements File
```bash
pip freeze > requirements.txt    # Create
pip install -r requirements.txt  # Install from file
```

---

## Key Takeaways

### ✅ Remember
- **PIP** is Python's package manager
- **Included** with Python 3.4+
- **PyPI** is the package repository
- **pip install** downloads and installs packages
- **pip list** shows installed packages
- **pip freeze** creates requirements file
- **Virtual environments** prevent conflicts
- **requirements.txt** for project dependencies

### 🎯 Interview Important
- What is PIP and its purpose
- How to install/uninstall packages
- Virtual environments importance
- Requirements file usage
- Common PIP commands
- Package version management
- PyPI as package source

---

**Use PIP to easily manage Python packages and dependencies!**