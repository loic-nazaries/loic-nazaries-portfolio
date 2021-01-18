# Create a Virtual Environment with Python

The present gist is a hybrid between a 'go-to' **cheat sheet** and a **tutorial** when starting a new **Data Science Project**.

Its purpose is to create a **virtual environment** with Python using the '**venv**' module.

[TOC]

## System Settings

Settings at the time of writing this gist (12th of January 2021).

### Microsoft Windows Operating System

Edition: Windows 10 Home
Version: 1909
OS build: 18363.1256
System type: 64-bits operating, x64-based processor

### Microsoft Visual Studio Code

Version: 1.52.1 (user setup)
Commit: ea3859d4ba2f3e577a159bc91e3074c5d85c0523
Date: 2020-12-16T16:34:46.910Z
Electron: 9.3.5
Chrome: 83.0.4103.122
Node.js: 12.14.1
V8: 8.3.110.13-electron.0
OS: Windows_NT x64 10.0.18363

### Python 3.9.1

NOTE: this gist does not explain how to install Python.

## Steps to creating a 'venv'

### Create a folder for the project

There are 2 options:

1. Create a repository on [GitHub.com](https://github.com/) BEFORE creating the project folder on the local machine.

   Once the repository is created, clone it onto the local machine.

   <u>This procedure will not be covered here but it will be in a future Gist.</u>

OR

2. Create the project folder locally (see below gist)

- First, open a **Terminal Prompt within VS Code**.

- Then, go to the folder where the new project is to be created, *i.e.* go to the 'working folder'.

  For example, if the main folder is called '**python_projects**', go to
  
  ```powershell
  C:\python_projects
  ```
  
  Hence, for the **relative path**, type:
  
  ```powershell
  cd /python_projects
  ```

- Create a folder for the project called '**project_name**' and check if it is present in the working folder

    ```powershell
    mkdir project_name && dir
    ```

- 'cd' into this folder

    ```powershell
    cd project_name
    ```

- Open the project folder 'project_name' from the menu in VS Code

### Create a virtual environment for the project

- Create a '**.py**' python file into 'project_name' and 'cd' into it

    ```powershell
    echo >> python_script.py
    ```

    Alternatively, create the .py file from VS Code menu.

- Open 'python_script.py' file

    NOTE: it is important to <u>create</u> AND <u>open</u> a .py file BEFORE creating and activating the venv, as it helps with its activation

- Create a virtual environment called '**venv_name**'

  The command below will create a new folder called 'venv_name'

  ```powershell
  python -m venv venv_name
  ```

  NOTE: the virtual environment name can be anything (like 'banana').
  However, it is common practice to use just '**venv**'. This is handy when copying/pasting code snippets.

  Hence, use the following command:

  ```powershell
  python -m venv venv
  ```

  NOTE: a message will appear (bottom right) asking to use the new environment, click 'Yes'.

  Alternatively, choose from the list of environments (bottom left). The Python version should be listed with 'venv' in parentheses, *e.g.*

  ```powershell
  Python 3.9.1 64-bit ('venv')
  ```

### Activate the new virtual environment 'venv'

If using the default command prompt (cmd), type:

```powershell
.\venv\Scripts\activate
```

If using Windows PowerShell (PS), type:

```powershell
.\venv\Scripts\Activate.ps1
```

IMPORTANT: if no changes seem to occur, open a new terminal prompt to activate the environment.

The active path should now be preceded by '**(venv)**' or '(banana)' if a specific venv name was chosen.

### Create 'default' folders and files

These will be needed for the project, *e.g.*:

```powershell
mkdir data, docs, tests, sources, backup, figures
```

```powershell
echo >> __init__.py
echo >> main.py
echo >> requirements.txt
```

OPTION: if the project is to be hosting on GitHub, the following '.md' files can be created, or done automatically when creating a repository.

```powershell
echo >> README.md
echo >> LICENSE
echo >> .gitignore
```

### Record the dependencies for the project

- First, update the '**pip**' library

    ```powershell
    python -m pip install --upgrade pip
    ```

- Then, create the dependencies file named '**requirements.txt**'

    ```powershell
    pip list > requirements.txt
    ```

### Install a Python library

```powershell
pip install package_name
```

If installing more than one package, type:

```powershell
pip install package_name_1 package_name_2
```

If installing a specific version of a package, type:

```powershell
pip install package_name=1.6
```

### Save the new dependencies

It is better to use '**pip freeze**' instead of '**pip list**' as it allows to pin the dependencies version.

```powershell
pip freeze > requirements.txt
```

NOTE: the 'requirements.txt' file can be used within a <u>new environment</u> to install dependencies cleanly with the following command:

```powershell
python -m pip install -r requirements.txt
```

IMPORTANT: this only works if 'requirements.txt' was produce with 'pip freeze' and NOT 'pip list'

### Check dependency clashes after installing all packages

```powershell
pip check
```

### Deactivate the virtual environment

```powershell
deactivate
```



NOTE: File prepared with Typora version 0.9.98 (beta)