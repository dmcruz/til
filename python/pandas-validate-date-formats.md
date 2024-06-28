# Pandas Validate Date Formats

## Problem

The dataframe has a date column, but we need to check that the values are in expected formats.

Let's say the dates only accept this formats:

mm/dd/YYYY
mm/dd/YY
YYYY/mm/dd
YYYYmmdd

How can we flag the rows that have unexpected dates?


## Solution

```python

import pandas as pd
import datetime

def is_date_format(date_str, fmt):
    try:
        result = bool(datetime.datetime.strptime(date_str, fmt))
    except ValueError:
        result = False
    return result
        
def is_date_format_valid(date_str):
    return is_date_format(date_str, '%Y/%m/%d') or \
            is_date_format(date_str, '%Y%m%d') or \
            is_date_format(date_str, '%m/%d/%Y') or \
            is_date_format(date_str, '%m/%d/%y')

def test():
    df = pd.DataFrame({
        "date1": [
            "2010/02/01",
            "02/01/2025",
            "02/14/26",
            "20240601",
            "29/01/2024",
        ]
    })

    print('Test data')
    print(df)

    dt1 = is_date_format_valid("02/01/2025")
    print(dt1)
    dt1 = is_date_format_valid("20240601")
    print(dt1)
    dt1 = is_date_format_valid("29/01/2024")
    print(dt1)

    df['is_date_valid'] = df.apply(lambda row: is_date_format_valid(row['date1']), axis=1)

    print('Flag valid dates')
    print(df)

test()

```

## Test data

## Output

```
Test data
        date1
0  2010/02/01
1  02/01/2025
2    02/14/26
3    20240601
4  29/01/2024

True
True
False

Flag valid dates
        date1  is_date_valid
0  2010/02/01           True
1  02/01/2025           True
2    02/14/26           True
3    20240601           True
4  29/01/2024          False
```