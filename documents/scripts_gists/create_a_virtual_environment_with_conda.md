# Create a Virtual Environment in Python with Conda

The present gist is a hybrid between a 'go-to' **cheat sheet** and a **tutorial** when starting a new **Data Science Project**.

Its purpose is to create a **virtual environment** for Python with the package manager Conda.

[TOC]

## System Settings

Settings at the time of writing this gist (14th of January 2021).

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

### Miniconda 3

Conda version: 4.9.2
Python version: 3.8.5

NOTE: Python is automatically installed when installing Miniconda.
This gist does not explain how to install Miniconda.

## Steps to creating a Conda virtual environment

### Create a folder for the project

There are 2 options:

1. Create a repository on [GitHub.com](https://github.com/) BEFORE creating the new project folder on the local machine.

    Once the repository is created, clone it onto the local machine.

    <u>This procedure will not be covered here but it will be in a future Gist.</u>

OR

2. Create the new project folder locally

- First, open a **Terminal Prompt within VS Code**.

- Then, go to the folder where the new project is to be created, *i.e.* go to the '**working folder**'.

    For example, if the main folder is called '**python_projects**', go to

    ```powershell
    C:\python_projects
    ```

    Hence, for the **relative path**, type:

    ```powershell
    cd /python_projects
    ```

- Create a folder for the project called '**project_name**' and check if it was created in the working folder

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

    NOTE: it is important to <u>create</u> AND <u>open</u> a .py file BEFORE creating and activating the venv, as it helps with venv activation
    
- Choose the Python instance from the list of environments (bottom left). The Python version should be listed with 'conda' in parentheses, *e.g.*

    ```powershell
    Python 3.8.5 64-bit (conda)
    ```

    NOTE:  the directory path to the project folder may be preceded by 'PS', which means the **default shell** is 'PowerShell'.
    However, Conda does not work with **PowerShell** in VS Code. Hence, the default shell must be changed to '**Command Prompt**' (**cmd**).

    

- Then, open a new terminal. 
    It should now show '**(base)**' BEFORE the directory path, *e.g.*

    ```
    (base) /Users/user_name
    ```

    NOTE: '**(base)**' represents an '**alias**' and is inside parentheses  This is important later on.

### Manage Conda

- Check Conda version and update

    ```
    conda info
    conda --version
    ```

- Update Conda from an environment named '**environment_name**'

    ```
    conda update --name environment_name conda
    ```

    IMPORTANT: like with Python base configuration, do NOT update the 'base' environment !! This is why virtual environments are for.

    

- Update Conda from inside the '**active**' environment

    ```
    conda update conda
    ```


### Manage environments

#### From the default environment folder

*i.e.* from '/miniconda3/envs'

- List all environments

    ```
    conda env list
    ```

    OR

    ```
    conda info --envs
    ```

    The output will look like this:

    ```
base             *  C:\miniconda3
    ```
    
    NOTE: when running 'conda env list', the (current) **active** environment in the environment list will have an asterisk * in front of the directory path (see example below).

    

- Create a new Conda virtual environment named '**environment_name**'

    The command below will create a new folder called '**environment_name**'.

    ```
    conda create --name environment_name
    ```

    The output will look like this:

    ```
    base             *  /miniconda3
    environment_name    /miniconda3/envs/environment_name
    ```

    NOTE 1: by default, new Conda environments are created in the '**envs**' folder where Miniconda is installed, *e.g.*

    ```
    /miniconda3/envs/environment_name
    ```

    NOTE 2: there should now be '**(environment_name)**' BEFORE the directory path. This is an '**alias**' as mentioned earlier, and it is inside parentheses  *e.g.*

    ```
    (environment_name) /Users/user_name
    ```

    IMPORTANT: in fact, the newly created environment will not be very useful unless a Python version is installed (see '<u>Manage Python</u>' section below)

    

- Clone the environment '**environment_name**' and create a new one called '**clone_environment**'

    ```
    conda create --name clone_environment --clone environment_name
    ```

    The output will look like this:

    ```
    base             * /miniconda3
    environment_name   /miniconda3/envs/environment_name
    clone_environment  /miniconda3/envs/clone_environment
    ```

- Activate the environment named '**environment_name**'

    ```
    conda activate environment_name
    ```

    The output will look like this:

    ```
    base               /miniconda3
    environment_name * /miniconda3/envs/environment_name
    clone_environment  /miniconda3/envs/clone_environment
    ```

- Deactivate current environment

    ```
    conda deactivate
    ```

    This means that the deactivated environment will lose its * when running 'conda env list'. Thus, the active environment will revert to 'base' environment.

    The output will look like this:

    ```
    base             * /miniconda3
    environment_name   /miniconda3/envs/environment_name
    clone_environment  /miniconda3/envs/clone_environment
    ```

- Delete an environment (and ALL its packages)
    This can be done only if the environment is NOT active.
    
    ```
    conda deactivate
    conda remove --name environment_name --all
    ```
    
    The output will look like this:
    
    ```
    base            *  /miniconda3
    clone_environment  /miniconda3/envs/clone_environment
    ```

- Delete unused packages from writable package caches

    ```
    conda clean --packages
    ```

- After deleting an environment, clear up Conda's cache to delete left-overs

    ```
    conda clean --all
    ```

#### From a specific location

*i.e.* not in Miniconda's 'envs' folder (see previous section)

- First, 'cd' into the project working directory, *e.g.*

    ```
    (base) /Users/user_name
    ```

    OR

    ```
    cd /python_projects
    ```

    Then, create a project folder named '**project_name**' and 'cd' into it, *e.g.*

    ```
    mkdir project_name && cd project_name
    ```

- Create a virtual environment called '**environment_name**'.
    However, the virtual environment name can be anything (like 'banana').
    For the sake of simplicity and reproducibility, let's just call it '**conda_env**'. This is because it is common practice to use just '**venv**' when a virtual environment is created with Python's 'venv' module. This is handy when copying/pasting code snippets.

    Then, use the **RELATIVE** path with the '**--prefix**' flag to create '**conda_env**'. It will be INSIDE the newly created project folder named '**project_name**'.

    Thus, from the Terminal Prompt, run the following code (no need to 'cd' into a specific folder):
    
    ```
    conda create --prefix ./conda_env
    conda activate ./conda_env
    ```

- Check the environment list.

    ```
    conda env list
    ```

    The output will look like this:

    ```
    base         C:\miniconda3  
              *  C:\python_projects\
              project_name_conda\conda_env
    ```

    IMPORTANT: before, the new 'environment_name' was stored within the 'base' configuration and it possessed an 'alias' in front of the directory path. This is not the case when using this way to creating Conda virtual environments. Thus, the **ABSOLUTE** path name is used as '**alias**' and is  inside parentheses BEFORE the **ABSOLUTE** path, *e.g.*

    ```
    (C:\python_projects\project_name\conda_env) C:\python_projects\project_name
    ```

    <u>**NOTE**:</u> it is possible to give an alias to the absolute directory path by modifying the '**.condarc**' file (see '<u>Manage packages</u>' section below for more).

- Delete this environment as shown earlier, *i.e.* run the following code:

    ```
    conda deactivate
    conda remove --prefix ./conda_env --all
    conda clean --packages
    conda clean --all
    ```

### Manage Python

- List versions of Python available to install

    ```
    conda search python
    ```

- Check the Python version installed

    ```
    python --version
    ```

- Create new Conda environment named '**conda_env**' with **Python** installed

    ```
    conda create --prefix ./conda_env python
    ```

    NOTE: if not specified, the 'default' Python version installed. Here, version 3.8.5.

- Create new Conda environment named 'conda_env' with a specific version of Python (*e.g.* version 3.9) and a package named '**package_name**'

    ```
    conda create --prefix ./conda_env python=3.9 package_name
    ```

    NOTE: see section '<u>Manage packages</u>' below for more.

- Update Python from inside the active environment to the latest version of a 3.x branch (*e.g.* version 3.4)

    ```
    conda update python
    ```

- Upgrade Python to another 3.x (*e.g.* version 3.6) by installing that version of Python

    ```
    conda install python=3.6
    ```

### Manage packages
- Search for package in Anaconda's library/repository

    ```
    conda search package_name
    ```

- Install a package named 'package_name' in the current environment

    ```
    conda install package_name
    ```

- Install several packages

    ```
    conda install package_name_1 package_name_2
    ```

- Install package from a specific source like a **URL address**

    ```
    conda install --channel url_address package_name
    ```

    IMPORTANT: it is advised to install all the packages at the same time to avoid dependency conflicts.

- Search and install a package not available in Anaconda's library. Look into **Conda-Forge repository**

    ```
    conda search --channel conda-forge package_name
    conda install --channel conda-forge package_name
    ```

- If the package is not in Conda-Forge either, try 'pip install' (***<u>LAST RESORT!!</u>***)

    ```
    pip install package_name
    ```

- Remove a package named 'package_name' from the current environment

    ```
    conda remove package_name
    ```

- List of all packages in the current environment

    ```
    conda list
    ```

- Save package list inside a "requirements.txt" file

    ```
    conda list > requirements.txt
    ```

    NOTE:  this is equivalent to the 'pip list' command when using 'venv'. Thus, it not appropriate when creating a new environment using the 'requirements.txt' file.

    The '**conda list > requirements.txt**' command lists the libraries installed manually (i.e. the packages installed via 'conda install') but also ALL the libraries installed with Conda.
    However, if the command '**pip list > requirements.txt**' is used then the default Conda libraries are not included.

    The following is equivalent to 'pip freeze':

    ```
    conda list --export > requirements.txt
    ```

    Save package URLs from Anaconda repository with the following command:

    ```
    conda list --explicit > requirements.txt
    ```

- Alternatively, save package list inside an '**environment.yaml**' file

    ```
    conda env export > environment.yaml
    ```

    NOTE: this is similar to a 'requirements.txt' file with 'conda/pip list/freeze'.

### Use a package list to create a NEW (identical) environment

#### From a 'requirements.txt' file

- Create a new environment called '**conda_env**' from the new project folder

    ```
    conda create --prefix ./conda_env --file requirements.txt
    conda activate ./conda_env
    ```

    IMPORTANT: the 'requirements.txt' file must be INSIDE the project folder path (*i.e.* /project_name)

- Alternatively, if 'conda_env' already exists, run the following code:

    ```
    conda install --file requirements.txt
    conda activate ./conda_env
    ```

    NOTE: also works with a requirement file created with the 'list --explicit' flag.

#### From an 'environment.yaml' file

- Create a new environment called '**conda_env**' from the new project folder

    ```
    conda env create --prefix ./conda_env --file environment.yaml
    conda activate ./conda_env
    ```

    IMPORTANT: the 'environment.yaml' file must be INSIDE the project folder path (*i.e.* /project_name)

    NOTE: if the purpose were to create a new environment inside Miniconda's default folder, one would run the code below. No need to be inside Miniconda's 'envs' folder.

    ```
    conda env create --file environment.yaml --name conda_env
    ```

#### Other options for managing Conda environments and packages

- Track (package) changes in current environment over time

    ```
    conda list --revisions
    ```

- Roll back the current environment to a previous (package) version

    ```
    conda install --revision revision_number
    ```

    NOTE: *e.g.* 'conda install --revision 2'.
    IMPORTANT: using revision '0' is not recommended.



NOTE: File prepared with Typora version 0.9.98 (beta)