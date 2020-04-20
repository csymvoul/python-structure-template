# A template to structure your Python application
A python project to use as a template when developing a Python application.

## In order to create a Python project with a similar structure you need to do the following: 
### The structure of the project should be as follows: 
```
├── README.md
├── example
│   ├── __init__.py
│   ├── package_1
│   │   ├── __init__.py
│   │   ├── awesome_module.py
│   │   ├── ...
│   │   └── awesome_module_n.py
│   └── package_2
│       ├── __init__.py
│       └── module.py
├── setup.py
└── tests
    └── __init__.py
```
### (Optional) Create a Python environment: 
* For Python3 users: 
  * `pip install virtualenv`
  * `virtualenv venv_name`
  * `source path/to/venv_name activate`
* For Anaconda users: 
  * `conda create --name conda_env`
  * `conda activate conda_env`
  * `conda install pip`

### Next you need to create a `setup.py`  file in the root folder. It should be similar to the one presented below: 
```
from distutils.core import setup
from setuptools import setup, find_packages

setup(
    name='example',
    version='0.1dev0',
    author='Author Name', 
    author_email='author_email@mail.com',
    packages=find_packages(),
    long_description=open('README.md').read()
)
```
### You need to create an **`__init__.py`** file in the `/example` directory where you should **import the packages** (i.e. `package_1`, and `package_2`): 
```
# example/__init__.py
from . import package_1, package_2 
```

### After that, you need to run the `setup.py` as follows: 
#### `pip install -e .`
An `example.egg-info` directory should be included in the root directory. 
If everything when according to plan, you should be able to use the modules you developed in the `package_1` from the `package_2` directory. 
