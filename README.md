# UCSB PSTAT Department Development Container Template

This template repository creates a starter [development container](https://computing.pstat.ucsb.edu/docs/devcontainer.html) setup suitable for use in the department research computing server.

## Prerequisite

To use this template, `copier` command-line utility is required and is available here: https://github.com/copier-org/copier.

## Generating from template

The template source can be instantiated directly the GitHub repository or a local copy in a directory (e.g., in Codespaces). If you are using Codespaces, start a terminal session.

- From GitHub repository:
    ```bash
    copier copy gh:UCSB-PSTAT/devcontainer-template starter-code 
    ```
- From a local directory named `devcontainer-template` (as in Codespaces):
    ```bash
    copier copy devcontainer-template starter-code 
    ```

The interactive process would look similar to the following:  
```
jovyan@jupyter-ucsb-2dpstat-2ddevcontainer-2dtemplate-2dfpo1c8gv:~$ copier copy gh:UCSB-PSTAT/devcontainer-template starter-code
🎤 What is the name of your project?
   some-project
🎤 What language(s) will you use in this project?
   R and Python
🎤 Do you want to install Visual Studio Code extensions for Jupyter notebooks, R and Python?
   Yes
🎤 Install Jupyter Lab? Jupyter Lab is optional if using VS Code and Python extensions for development.
   No
🎤 Install Rstudio? Rstudio is optional if using VS Code and R extensions for development.
   No
🎤 Install Quarto? Quarto is optional publishing system compatible with R and Python.
   Yes
🎤 Do you want to include example files?
   Yes

Copying from template version 1.0.0
    create  .
    create  .devcontainer
    create  .devcontainer/Dockerfile
    create  .devcontainer/devcontainer.json
    create  example.Rmd
    create  example-R.qmd
    create  example-python.qmd
```

## View generated files:

To view generated files, 
```bash
tree -a starter-code/
```  
The output would look similar to the follwing:  
```
jovyan@jupyter-ucsb-2dpstat-2ddevcontainer-2dtemplate-2dfpo1c8gv:~$ tree -a starter-code/
starter-code/
├── .devcontainer
│   ├── devcontainer.json
│   └── Dockerfile
└── example.Rmd

1 directory, 3 files
```

## Using generated files

Now that you have a development container starter setup, you start using it.

You can ...
- [Upload `starter-code` to a GitHub repository](#upload-to-github-repository) to start a new repository for your project.
- [Create and download a zip file](#download) to manually add `.devcontainer` directory and its contents to an existing project.

### Upload to GitHub Repository

1. Authenticate with your GitHub account using the [GitHub CLI](https://cli.github.com). In Codespaces, `gh` is available in `/opt/conda/bin/gh` :
    ```bash
    gh auth login
    ```
1. Convert generated files to a repository:
    ```bash
    cd starter-code
    git init
    git add *
    git commit -m "first commit"
    git branch -M main
    ```
1. Upload local repository to a new GitHub repository.  
    Be sure to choose, "**Push an existing local repository to GitHub**":
    ```bash
    # cd starter-code
    gh repo create 
    ```

### Download setup files

1. Create a zip file of `starter-code` contents:
    ```bash
    zip -r starter-code.zip starter-code
    ```
1. Right click `starter-code.zip` in file browser and select "Download..."
1. Once downloaded, unzip the contents and add the `.devcontainer` folder to the root of your project folder.