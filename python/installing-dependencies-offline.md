# installing dependencies offline

## Problem

Install pip dependencies in a machine that does not have access to internet

## Pre-requisite

- [Create requirements.txt first](create-dependency-requirements-file.md)
- [Download dependencies to a folder](create-dependencies-to-a-folder.md)

## Solution


```
python -m pip install --no-index --find-links="./outputwheel" -r requirements.txt
```