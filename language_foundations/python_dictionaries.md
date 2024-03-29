[Home](../index.md) > Python > [Dictionaries](./python_dictionaries.md)

# Python | Dictionaries

**dict** - built-in mutable data type used to store, unordered collections of key-value pair items.

Features:

- Each key is unique and associated with some value.
- Use Primitive Types for keys. Mutable object either directly or indirectly, cannot be used as a key.
- Error will be raised when trying to extract a value for non-existent key.
- Dictionaries preserve insertion order of an items.

## Basics

```python
# Create
empty_dict_one = dict()
empty_dict_two = {}

# Create & Init
grade_score = {"A": (500, "Greate"), "B": (300, "Average"), "C": 100}
states = dict(ordered=True, shipped=True, delivered=False)
year_budget = dict([(2019, 56), (2020, 0), (2021, 77)])
student_age = dict(zip(["Alice Johnson", "Betty Fisherman", "Rodrigo Bentancur"], [21, 24, 26]))
items = dict.fromkeys(["Item 1", "Item 2"], "Some Default Value")

"""
grade_score = {'A': (500, 'Greate'), 'B': (300, 'Average'), 'C': 100}
states = {'ordered': True, 'shipped': True, 'delivered': False}
year_budget = {2019: 56, 2020: 0, 2021: 77}
student_age = {'Alice Johnson': 21, 'Betty Fisherman': 24, 'Rodrigo Bentancur': 26}
items = {'Item 1': 'Some Default Value', 'Item 2': 'Some Default Value'}
"""

# Add
grades = {"A": 1, "B": 2}
grades["C"] = 3
grades.setdefault("E", 5)

"""
grades = {'A': 1, 'B': 2, 'C': 3, 'E': 5}
"""

# Update
pairs = {"key1": 1, "key2": 1}
pairs["key2"] = 2
pairs.update([("key1", 0), ("key2", 1)])
pairs.update({"key3": 2})
pairs.pop("key2") # retrieves and removes an value by key.

"""
pairs = {'key1': 0, 'key3': 2}
"""

# Get
regions = {"NA": "North America", "APAC": "Asia, Pacific", "EMEA": "Europe, Middle East, Africa"}
na_text = regions["NA"]
apac_text = regions.get("APAC")
eu_text = regions.get("EU", "No Key")
emea_key, emea_text = regions.popitem() # retrieves and removes last item.

"""
na_text = "North America"
apac_text = "Asia, Pacific"
eu_text = "No Key"
emea_text = "Europe, Middle East, Africa"
"""

# Delete
category_products = {
  "fruits": ["apple", "banana"],
  "vegetables": ["potato"],
  "spices": ["salt", "pepper"],
  "drinks": ["pepsi", "water"],
  "sweets": ["chocolate", "candies"]
}

del category_products["spices"]
category_products.pop("fruits")
category_products.popitem()
category_products.clear()

"""
{'fruits': ['apple', 'banana'], 'vegetables': ['potato'], 'drinks': ['pepsi', 'water'], 'sweets': ['chocolate', 'candies']}
{'vegetables': ['potato'], 'drinks': ['pepsi', 'water'], 'sweets': ['chocolate', 'candies']}
{'vegetables': ['potato'], 'drinks': ['pepsi', 'water']}
{}
"""

```

## Methods and functions

```python
# Get items count.
len({"duck": 5, "cat": 2}) # 2

# Check if key exists.
2030 in {1990: "Italy", 1998: "France", 2006: "Germany"} # False

# Make shallow copy.
tech_dict = {1: ['Angular', 'React'], 2: ["Spring", ".NET", "NodeJS"]}
tech_dict_copy = tech_dict.copy()
tech_dict[2].append("Django")
print(tech_dict_copy)
# {1: ['Angular', 'React'], 2: ['Spring', '.NET', 'NodeJS', 'Django']}

# Create fromkeys
dict.fromkeys([(0, 0), (0, 1), (1, 0), (1, 1)], 0)
# {(0, 0): 0, (0, 1): 0, (1, 0): 0, (1, 1): 0}

# View objects for keys, values and items. (changes to dict will be automatically reflected in views)
colors = {"red": "#FF0000", "green": "#00FF00", "blue": "#0000FF"}
colors.keys() # dict_keys(['red', 'green', 'blue'])
colors.values() #dict_values(['#FF0000', '#00FF00', '#0000FF'])
colors.items() # dict_items([('red', '#FF0000'), ('green', '#00FF00'), ('blue', '#0000FF')])

# Convert to list of keys
list(colors) # ['red', 'green', 'blue']
list(colors.values()) # ['#FF0000', '#00FF00', '#0000FF']

```
