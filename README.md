# Project Setup

This project uses **uv** for Python environment and package management.

## Prerequisites

* Python installed on your system
* `uv` installed globally

---

## 1. Install `uv`

### Windows — PowerShell

Run:

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

After installation, add the uv installation directory to your `PATH` if it is not already available:

```powershell
$env:Path += ";$HOME\.local\bin"
```

Verify the installation:

```powershell
uv --version
```

### Linux / macOS

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Reload your shell:

```bash
source ~/.bashrc
```

or, for zsh:

```bash
source ~/.zshrc
```

Verify:

```bash
uv --version
```

---

## 2. Create the Virtual Environment

Navigate to the project directory:

```bash
cd <project-directory>
```

Create a virtual environment:

```bash
uv venv
```

This creates a `.venv` directory in the project.

---

## 3. Activate the Virtual Environment

### Windows — PowerShell

```powershell
.venv\Scripts\Activate.ps1
```

### Windows — Command Prompt

```cmd
.venv\Scripts\activate
```

### Linux / macOS

```bash
source .venv/bin/activate
```

After activation, your terminal should show something similar to:

```text
(.venv)
```

---

## 4. Install Project Dependencies

Make sure `requirements.txt` is present in the project directory.

Install all dependencies using:

```bash
uv pip install -r requirements.txt
```

Alternatively, if the virtual environment is not activated, you can explicitly install into the `.venv` environment:

```bash
uv pip install --python .venv/bin/python -r requirements.txt
```

For Windows:

```powershell
uv pip install --python .venv\Scripts\python.exe -r requirements.txt
```

---

## 5. Run the Application

Once the dependencies are installed, run:

```bash
python app.py
```

If your system uses `python3`:

```bash
python3 app.py
```

---

## Complete Setup — Windows PowerShell

For a fresh setup, the commands are:

```powershell
# Install uv
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"

# Add uv to PATH for the current session
$env:Path += ";$HOME\.local\bin"

# Verify uv
uv --version

# Go to project
cd <project-directory>

# Create virtual environment
uv venv

# Activate virtual environment
.venv\Scripts\Activate.ps1

# Install dependencies
uv pip install -r requirements.txt

# Run application
python app.py
```

## Complete Setup — Linux / macOS

```bash
# Install uv
curl -LsSf https://astral.sh/uv/install.sh | sh

# Reload shell
source ~/.bashrc

# Verify uv
uv --version

# Go to project
cd <project-directory>

# Create virtual environment
uv venv

# Activate virtual environment
source .venv/bin/activate

# Install dependencies
uv pip install -r requirements.txt

# Run application
python app.py
```

---

## Project Structure

A typical project structure should look like:

```text
project/
│
├── .venv/
├── app.py
├── requirements.txt
└── README.md
```

> **Note:** The `.venv` directory should generally not be committed to Git. Add it to `.gitignore`:

```text
.venv/
```
