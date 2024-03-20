# print colored text in terminal

Text can be surrounded by colors using ANSI escape characters.

Source: https://sentry.io/answers/print-colored-text-to-terminal-with-python/

# Solution (without using 3rd party library)

This solution prints a text specifying foreground and background color codes.

print-color.py

``` python 

PALETTE = {
    'BLACK': '\x1b[30;40m',
    'RED':'\x1b[31;41m',
    'GREEN':'\x1b[32;42m',
    'YELLOW':'\x1b[33;43m', # orange on some systems
    'BLUE':'\x1b[34;44m',
    'MAGENTA':'\x1b[35;45m',
    'CYAN':'\x1b[36;46m',
    'LIGHT_GRAY':'\x1b[37;47m',
    'DARK_GRAY':'\x1b[90;100m',
    'BRIGHT_RED':'\x1b[91;101m',
    'BRIGHT_GREEN':'\x1b[92;102m',
    'BRIGHT_YELLOW':'\x1b[93;103m',
    'BRIGHT_BLUE':'\x1b[94;104m',
    'BRIGHT_MAGENTA':'\x1b[95;105m',
    'BRIGHT_CYAN':'\x1b[96;106m',
    'WHITE':'\x1b[97;107m'
}

RESET = '\x1b[0m'

for color in PALETTE:
    print(PALETTE[color] +  color.center(20) + RESET) 


```