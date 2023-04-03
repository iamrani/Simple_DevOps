# Simple_DevOps

A simple DevOps project with version control (Git), continuous integration, and continuous delivery (GitHub Actions) set up using Visual Studio Code on Windows.

hello.py - Python script that defines a function called hello() and then calls this function when the script is executed.

.gitignore - Patterns to be ignored; Git will ignore any files or folders that match the patterns specified in the .gitignore file.

main.yml - This workflow is triggered whenever you push changes to your GitHub repository. 
            It sets up a Python environment, installs flake8 (a Python linting tool), checks the code with flake8, and runs the script.
