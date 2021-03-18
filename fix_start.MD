# Fix Start

Create a function called **fixStart**. It should take a single argument, a string, and return a version where all occurrances of its first character have been replaced with **\***, except for the first character itself. you can assume that the string is at least one character long. For example:

`fixStart('babble'): 'ba**le'`

`fixStart('turtle'): 'tur*tle'`

```
FUNCTION fixStart(in_string)
    out_string = ""
    first_character = ""
    FOR EACH character in in_string
        IF first_character == ""
            first_character = character
            APPEND character to out_string
        ELSE IF character == first_character
            APPEND '*' to out_string
        ELSE
            APPEND character to out_string
    
    RETURN out_string
```

**Tested solution in Python**

```
def fix_start(in_string):
    out_string = []
    first_character = ""
    for char in in_string:
        if first_character == "":
            first_character = char
            out_string.append(char)
        elif char == first_character:
            out_string.append('*')
        else:
            out_string.append(char)
    return ''.join(out_string)

print(fix_start('babble'))
print(fix_start('turtle'))

>>> ba**le
>>> tur*le
```