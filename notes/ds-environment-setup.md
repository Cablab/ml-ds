# Data Science Environment Setup

## Tools Intro

### Anaconda, Miniconda, Conda

**Anaconda**: hardware store
  - Data Science software distribution. Includes all of the Data Science packages and installs the most popular ones by default

**Miniconda**: workbench
  - Installs the minimum requirements to get started on Data Science problems, is much liter than full Anaconda
  - Comes with Conda
  
**Conda**: data science package manager
  - Helps setup the workbench, get new packages

## Conda Environments

- An environment is a collection of packages and/or tools
- Conda can create environments and install new packages to the environment
- Conda allows easy recreation of a given environment elsewhere so its easy to share workspaces
- List all environments with `conda env list`

### Installation Steps

- Download Miniconda
  - [Miniconda Download Page](https://docs.conda.io/en/latest/miniconda.html)
- Install
- Test via terminal
  - Installs a shortcut/program that can be searched with something like `Anaconda Prompt`
- Create project folder and change into it
- Create custom Conda environment in project folder
  - `conda create --prefix ./env <package names>`
  - Creates a conda environment, creates an `env` directory, installs the list of packages you mentioned
    - Common packages are `pandas numpy matplotlib scikit-learn jupyter`
- Activate new environment
  - `conda activate <path-to-project-directory>`
- Install Jupyter (**from inside the active environment**)
  - `conda install jupyter`
- Load up a Jupyter Notebook and check for needed tools
  - From inside the active environment, run `jupyter notebook`
  - This will open default browser with Jupyter environment. In the top right, click `New > Python 3` to open a new notebook inside the project directory
  - Try importing the necessary libraries and make sure that you don't get errors

  ```python
  import pandas as pd
  import numpy as np
  import matplotlib.pyplot as plt
  import sklearn as skl
  ```

  - Run `cells` in Jupyter Notebook with `Shift + Enter`
    - If there's an error, it'll be printed. If everything worked and there are no errors, the index number on the side (like `In [#]`) will go up with each command that's run/entered
- Stop Jupyter Notebook process with `Ctrl + C`
- Get out of the activated Conda environment with `conda deactivate`
- Export the environment as a YAML file if you need to share it with another computer
  - `conda env export --prefix <path/to/project/env > environment.yml`
- Create an environment from a YAML file
  - `conda env create --prefix ./env -f <path to file>`
  - Alternative?? `conda env create --file environment.yml --name env_from_file`

## Jupyter Notebook Walkthrough

- [Jupyter Notebook Tutorial](https://www.dataquest.io/blog/jupyter-notebook-tutorial/)
- [Jupyter Notebook Docs](https://jupyter-notebook.readthedocs.io/en/stable/)

Other helpful commands:

- Run cell with `Shift + Enter`
- Change cell from Edit to Command mode: `Esc`
- Change cell from Command to Edit mode: `Enter`
- Changing between `Code` and `Markdown` modes **while in Command mode**:
  - Code mode: `y`
  - Markdown mode: `m`
- Adding cells **while in Command mode**:
  - New cell above: `a`
  - New cell below: `b`
- Delete cell **while in Command mode**: `dd`
- You can run terminal commands straight in Jupyter Notebooks
  - Unix commands might work just with the command, like `ls`
  - Windows cmd commands may need an `!` in front, like `!dir`

## Upgrading Packages in Conda Environment

- Activate Conda environment
- Use `conda list` to see all installed packages
- Use `conda update <package-name>` 
- If you want to install a specific version, you can use `conda search <package-name>`
  - This will list all versions available for the specified package
  - You can also pass `--info` to see verbose info about each version
- Install a specific package version with `conda install <package-name>=<version-number>`
