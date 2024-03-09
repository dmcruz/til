# packaging python script to exe

## Problem

I developed a script to automate a user's workflow but due to company policy, the user is unable to install python in their machine.


## Solution

PyInstaller can bundle a Python application, python interpreter and all the required dependencies in one package. PyInstaller is not a cross-compiler which means to build a Windows application, the script must be built against a Windows operating system. In order to distribute to other OS, it must be build on a build machine with the same type of OS the application is targeted for.

## Steps

1. Install PyInstaller via pip

```
pip install -U PyInstaller
```

2. Package the app with PyInstaller

```
python -m PyInstaller --onefile --windowed your_python_script.py
```

3. Locate the executable in dist folder which can now be shipped to the users