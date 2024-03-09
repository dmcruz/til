# create dependency requirements file

## Problem

Get a list of dependencies of a python project

## Solution

1. Install pipreqs

```
python -m pip install pipreqs
```

2. Open terminal and browse to the folder of your python project
3. Generate requirements.txt

```
python -m pipreqs.pipreqs .
```

4. Requirements file should be saved in requirements.txt