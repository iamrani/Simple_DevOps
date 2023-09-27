# Simple_DevOps

**Overview**

This project demonstrates the setup of a simple DevOps pipeline for a Python application using Git for version control and GitHub Actions for continuous integration and continuous delivery (CI/CD). 
The project's goal is to automate the process of checking code style and running a Python script whenever changes are pushed to a GitHub repository.

**Files**
1. hello.py - Python script that defines a function called hello() and then calls this function when the script is 
   executed.
2. .gitignore - Patterns to be ignored; Git will ignore any files or folders that match the patterns specified in the 
   .gitignore file.
3. main.yml - This workflow is triggered whenever you push changes to your GitHub repository. It sets up a Python 
   environment, installs flake8 (a Python linting tool), checks the code with flake8, and runs the script.


**Workflow Configuration (main.yml)**

This file defines a GitHub Actions workflow that sets up a Python environment, installs dependencies, checks the code for style issues, and runs the hello.py script.

**Workflow Name**

`name: CI/CD Pipeline`

**Trigger Event**

The workflow is triggered whenever changes are pushed to the GitHub repository.

`on: [push]`

**Job Definition**

Defines a job named 'build' that runs on an Ubuntu latest version runner.

`jobs:`
  `build:`
     `runs-on: ubuntu-latest`

    
**Job Steps**

Defines the steps to be executed within the 'build' job.

**Step 1: Check out the repository**

Uses the `actions/checkout` action to fetch the repository's code.
    - name: Check out repository
      uses: actions/checkout@v2

**Step 2: Set up Python**
Uses the `actions/setup-python` action to set up the Python environment with version 3.9.

    - name: Set up Python
      uses: actions/setup-python@v2
      with:
        python-version: 3.9

**Step 3: Install dependencies**

Upgrades `pip` package manager and installs the `flake8` Python linting tool.

    - name: Install dependencies
      run: |
        python -m pip install --upgrade pip
        pip install flake8

**Step 4: Lint with flake8**

Runs the flake8 linter on hello.py to check the code for style issues and errors.

    - name: Lint with flake8
      run: |
        flake8 hello.py

**Step 5: Run script**

Executes the hello.py script.

    - name: Run script
      run: |
        python hello.py

**Git Configuration (.gitignore)**
Specifies files and directories to be ignored by Git.

``__pycache__/``

 ``  *.pyc``
 
 ``  *.pyo``
 
 ``  *.pyd``

**Python Script (hello.py)**

Contains a Python script with two functions and a main block that demonstrates their usage.

<code>def hello():
   return "Hello, DevOps!"</code>
   
<code>def personalized_hello(name):
   return f"Hello, {name}! Welcome to DevOps." </code>
   
</code> 
if __name__ == "__main__":
    print(hello())
    print(personalized_hello("Ranishka Fernando"))\
    </code>

