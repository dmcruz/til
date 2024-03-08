# validate password with limited special characters

## Requirement

The password must have at least 1 upper case, at least 1 lower case, at least 1 number and at least 1 special character from this set:
`!@#$%^&*():;,.?-`

Minimum character length: 6

Maximum character length: 8

## Regex Solution

```
^(?=.*?[a-z])(?=.*?[A-Z])(?=.*?[0-9])(?=.*\W)[a-zA-Z0-9!@#$%^&+=\\/\(\):;,\.\?\-]{6,16}$
```

## Explanation

- `(?=.*?[a-z])` - Positive lookahead looks for any string with at least 1 lowercase alphabet character
- `(?=.*?[A-Z])` - Positive lookahead looks for any string with at least 1 uppercase alphabet character
- `(?=.*?[0-9])` - Positive lookahead looks for any string with at least 1 number
- `(?=.*\W)` - Positive lookahead looks for any string that is non-word character (not a-zA-Z0-9 and underscore _)
- `[a-zA-Z0-9!@#$%^&+=\\/\(\):;,\.\?\-]{6,16}` - Define a list of allowed characters with a minimum length of 6 and a maximum of 16 characters