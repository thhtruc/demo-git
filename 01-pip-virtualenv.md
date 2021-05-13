# Python Package Manager


## I. Getting started with pip

### 1. What is pip?
`pip` is the standard package manager for Python. We can use pip to install additional packages that are not available in the Python standard library (ex. numpy, opencv,...).

### 2. How to install pip?
`pip` comes pre-installed on the Python versions 3.4 or older. We can check if `pip` is installed by using the following command in the console:

```bash
pip --version
```
### 3. Difference between pip and pip3
- When the computer has multiple versions of python at the same time, pip3 can automatically determine to use python3 to install the library, in order to avoid conflicts with python2.
- If your computer only has python3 installed, using pip or pip3 is the same
- You can refer to this [link](https://stackoverflow.com/questions/40832533/pip-or-pip3-to-install-packages-for-python-3) to check where your `pip` and `pip3` real paths are

### 4. How to use pip?
#### Install a new package
- Most of these packages are officially hosted and published to the [Python Package Index(PyPI)](https://pypi.org/). `pip` allows us to download and install these packages.  
- pip is a command-line program. After its installation, a `pip` command is added which can be used with the command prompt:
  ```bash
  # Install a package with lastest verion
  pip install package_name
  ```
  or

  ```bash
  # Sometimes you want to install a packages with a specific version
  pip install package_name==0.1
  ```
#### List installed packages with pip
The `pip list` command can be used to list all the available packages in the current Python environment
```bash
pip list
```

#### Show package information with pip
The `pip show` command displays information about one or more installed packages.
```bash
pip show package_name
```

#### Uninstall a package with pip
We can uninstall a package by using pip with the `pip uninstall` command

```bash
pip uninstall package_name
```
#### Use a requirements.txt file
A file containing all the package names can also be used to install Python packages in batches

- Sample requirements.txt
  ```bash
  numpy==1.20.2
  requests==2.25.1
  ```
- Install pakages using requirements.txt file
  ```bash
  pip install -r requirements.txt
  ```
#### Export installed packages to requirements.txt file

You can also export installed packages to file and then restore them later

```bash
pip freeze > requirements.txt
```

## II. Python Virtual Environment
### Why do you need virtual environment?

Full docs: https://docs.python.org/3/tutorial/venv.html#introduction.  

- Python applications will often use packages and modules that don’t come as part of the standard library. Applications will sometimes need a specific version of a library, because the application may require that a particular bug has been fixed or the application may be written using an obsolete version of the library’s interface.

- This means it may not be possible for one Python installation to meet the requirements of every application. If application A needs version 1.0 of a particular module but application B needs version 2.0, then the requirements are in conflict and installing either version 1.0 or 2.0 will leave one application unable to run

- venv (for Python 3) and virtualenv (for Python 2) allow you to manage separate package installations for different projects. They essentially allow you to create a “virtual” isolated Python installation and install packages into that virtual installation. When you switch projects, you can simply create a new virtual environment and not have to worry about breaking the packages installed in the other environments. It is always recommended to use a virtual environment while developing Python applications.

### Using virtual environment
- To create a virtual environment, go to your project’s directory and run venv. If you are using Python 2, replace venv with virtualenv in the below commands
  ```bash
  python3 -m venv env
  ```
- Before you can start installing or using packages in your virtual environment you’ll need to activate it
  ```bash
  source env/bin/activate
  ```
- If you want to switch projects or otherwise leave your virtual environment, simply run
  ```bash
  deactivate
  ```

## III. Reference
1. https://www.programiz.com/python-programming/pip
2. https://stackoverflow.com/questions/40832533/pip-or-pip3-to-install-packages-for-python-3
3. https://docs.python.org/3/tutorial/venv.html#introduction
4. https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/
