[Home](../index.md) > Python > [Basics](./python_strings.md)

# Python | Strings

## Basics

```python
# Double quotes
name = "Jordan"

# Single quotes
last_name = 'Michael'

# Multiline
json_text = '''{
  "id": 1,
  "email": "em@il.com"
}'''
tale = """Once upon a time,
there was a kid who had a dream."""

# String Literals / F-strings
score, total_score = 3, "5"
message = f"Your score is {score} out of {total_score}"

# Raw strings (It won't escape special characters like \n or \t.)
path = r"C:\Users\Username\Documents"

# format() method
output = "{0} little ducks went swimming one day ...".format(5)
```

## Operations & Methods

```python
# Length
l = len("bla bla")

# Concatenation
name = "Tony" + " " + "Stark"

# Slice (returns new string)
s = "abcdef"
s[0] # 'a'
s[2:] # 'cdef'
s[1:4] # 'bcd'
s[2:-2] # 'cd'
s[-2:] # 'ef'
s[-3:-1] # 'de'

# Replace
s.replace("f", "a") # 'abcdea'

# Split
"create|update|delete".split("|") # ['create', 'update', 'delete']
str(547).split() # ['547']

# Create from list
",".join(['a', 'b']).join("[]")  # '[a,b]'

# Find -> start index or -1 (use index to for not found ValueError)
"[a,b]".find(",") # 2
"Some text".find("bla") # -1
"python is ...".find("...") # 10

# Count
"011101101".count("0") # 3
"1010".count("10") # 2
"abc".count("cba") # 0

# Lower, upper, title
name = "heNry"
name.lower() # 'henry'
name.upper() # 'HENRY'
name.title() # 'Henry'

# Strip (Trim)
input_message = "   omg*** "
input_message.strip() # 'omg***'
input_message.strip().strip("*") # 'omg'
input_message.lstrip() # 'omg*** '
input_message.rstrip("*** ") # '   omg'

# startswith, endswith
"Chapter #1".startswith("Cha") # True
"SC_782_01".endswith("02") # False

```

## Escape character

- `\n` Newline
- `\t` Tab
- `\\` Backslash
- `\'` Single quote
- `\"` Double quote
