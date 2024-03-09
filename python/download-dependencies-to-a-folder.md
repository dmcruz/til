# download dependencies to a folder

## Problem 

Download dependencies to a folder so that in can be installed later in a computer that does not have access to the internet

## Solution

### Pre-requisite

- [Create requirements.txt first](create-dependency-requirements-file.md)

### Option 1: Use pip wheel

```
python -m pip wheel -r requirements.txt -w .\outputwheel
```

### Option 2: Use pip download

```
python -m pip download -r requirements.txt -d .\outputwheel
```