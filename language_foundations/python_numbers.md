[Home](../index.md) > Python > [Basics](./python_numbers.md)

# Python | Numbers

## Number operators and methods.

```python
# Division
a = 3 / 2 # 1.5 : float
b = 3 // 2 # 1 : int
c = 3 % 2 # 1 mod operator

# Power
x, y = 2, 3
z = x ** y # 2 ^ 3 = 8

# min, max
min_num = min(2, -1, 7) # -1
max_num = max(4, 12, -33) # 12

# floor, round, ceil
math.floor(2.6) # 2
round(2.6) # 3
round(2.3) # 2
math.ceil(2.1) # 3

# Max values and infinities
import sys
max_word_size = sys.maxsize
positive_infinity = float("inf")
negative_infinity = float("-inf")

```
