[Home](../index.md) > Python > [Lists](./python_lists.md)

# Python | Lists

**list** - built-in data structure that is used to store mutable sequences of items of various types.

## Basics

```python

# Create
names = list()
ages = []

# Create + Init
grades = ["A", "B", "C"]
mess = ["Alex", 25, 10.5, True, "apple", [1, 3, 5], None]
zero_list = [0] * 5
interval = list(range(10))
index_list = [i for i, flag in enumerate([False, True, True, False]) if flag]

# Add items
names.append("James")
names.append("Julia")

ages.extend([25, 18])
names += ["Japinder", "Jasmine"]
ages = ages + [30, 27]

names.insert(2, "琪夏")
ages.insert(2, 22)

'''
['James', 'Julia', '琪夏', 'Japinder', 'Jasmine']
[25, 18, 22, 30, 27]
'''

# Update items
names[1] = "Angie"

names[3:] = ["Arjun", "Shruthi", "Bill"]
ages[-2:] = [32, 2, 68]

names.pop(0) # Or names.remove("James")
names.insert(0, "Alejandro")

'''
['Alejandro', 'Angie', '琪夏', 'Arjun', 'Shruthi', 'Bill']
[25, 18, 22, 32, 29, 68]
'''

# Get items
qixia_age = ages[2] # 22
last_age = ages[-1] # 68

indian_names = names[3:5] # ['Arjun', 'Shruthi']

# Delete items
last_name, last_age = names.pop(), ages.pop()
angie_name, angie_age = names.pop(1), ages.pop(1)

names.remove("Arjun")
ages.remove(32)

del names[1]
del ages[1]

names[-1:] = []
ages[-1:] = []

names.clear()
ages.clear()

```

## Methods and functions

```python
# len - list length.
len(["A", "B"]) # 2

# Check if item is in the list
None in [3, None, "abc"] # True
2.0 not in [0, 2, 1] # False

# append - adds element to the end.
[2, -1].append(7) # [2, -1, 7]

# extend - adds list of elements to the end.
["orange", "apple"].extend(["banana", "lemon"]) # ["orange", "apple", "banana", "lemon"]

# copy - creates a shallow copy of the list.
clones_copy = ["Dolly", "Ralph", "Alexis"].copy()

# insert - adds element at specified position
[2.71, 3.14].insert(0, 1.61) # [1.61, 2.71, 3.14]

# remove - removes the first occurrence of a specific value.
[True, None, False, None].remove(None) # [True, False, None]

# del - deletes some specific range from the list
items = [True, False, False]
del items[1:] # [True]

# pop - removes and returns an element at a specific index.
[("A", 4), ("B", 7), ("C", 1)].pop(1) # [("A", 4), ("C", 1)]
[("A", 4), ("B", 7), ("C", 1)].pop() # [("A", 4)]

# count - returns the number of occurrences of a specific value.
[1, 0, 0, 1, 0].count(0) # 3

# sort - sorts the list in-place in ascending order.
[2, 1, 3, 1].sort() # [1, 1, 2, 3]

# sorted - returns new sorted list from original one.
ages = [11, 24, 5]
sorted_ages = sorted(ages)
'''
ages: [11, 24, 5]
sorted_ages: [5, 11, 24]
'''

# reverse - reverses the elements of the list in-place.
["Eva", "Alex", "Peter"].reverse() # ["Peter", "Alex", "Eva"]

# max, min, sum
max([2, 8, 11]) # 11
min([2, 8, 11]) # 2
sum([1, 2, 3]) # 6

# filter - filters the elements based on a condition function. Returns iterator.
even_numbers = list(filter(lambda x: x % 2 == 0, [2, 4, 7, 11, 9])) # [2, 4]

# join - returns string with list items separated by delimiter.
' | '.join(["Home", "Articles", "About"]) # 'Home | Articles | About'

```

## Iterate

```python

# Loop
scores = [23.5, 7.0, 11.0]
for i in range(len(scores)):
  print(scores[i])

# Loop through values
for bit in [0, 0, 1, 0]:
    print(bit)

# Loop with index
for i, name in enumerate(["Alice", "Jane", "Uta"]):
    print(f"i: {i}, name: {name}")

# While loop
tasks, i = [34234, 434, 2123], 0
while i < len(tasks):
    print(tasks[i])
    i += 1

# List comprehension
squares = [x * x for x in [3, 5, 1, 4, 2] if x % 2 != 0]

# Iterate with map
my_list = [1, 2, 3, 4, 5]
squared_list = list(map(lambda x: x**2, my_list))

# Iterate with zip
grades = ['A', 'B', 'C']
scores = [1, 2, 3]
for g, s in zip(grades, scores):
    print(f"{g}: {s}")

# Using iter() and next()
fruits = ["apple", "lemon", "cherry"]
fruits_iter = iter(fruits)
while True:
  try:
    item = next(fruits_iter)
    print(item)
  except StopIteration:
    break

```
