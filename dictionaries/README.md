# ![Python Data Structures - Dictionaries](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to unnderstand the concept of dictionaries in Python, differentiate them from other data structures, and demonstrate how to create and manipulate dictionaries.

## Purpose

**Dictionaries** are to Python as **objects** are to JS.

A **dictionary** provides a container for `key: value` pairs.

In Python, we commonly refer to `key: value` pairs as **items** vs. **properties** as in JS.

*Dictionaries* have a class (type) of `dict`.

### Basic syntax

As with objects in JS, a dictionary is created literally using curly braces:

```python
student = {
  'name': 'Maria',
  'course': 'SEI',
  'current_week': 7
}
```

Unlike in JS, when strings are used as keys, they must be quoted.

## Features

Dictionaries are mutable:

- The values assigned to a key can be changed
- Additional items can be added
- Existing items can be deleted

Any immutable type can be used as a key, including *numbers* and *tuples* (which we’ll cover in a bit), for example:

```python
some_key = 3

d = {
  some_key: 'three'
}
```

The above dictionary, `d`, has 1 item with a key of `3` that holds the value of `'three'`.

> ⚠️ Only since version 3.6 does Python track the insertion order of items in a dictionary - so beware if you’re relying on the order items are iterated upon.

## Getting and setting values

We use square brackets to get and set an item’s value:

```python
name = student['name']
print(name)
> Maria
student['name'] = 'Mariana'
print(student['name'])
> Mariana
```

Unlike JS, we can’t access items in a Python dictionary using dot notation (dots are used to invoke methods on the dictionary).

## The `get` method

When accessing a key that does not exist in a dictionary, a `KeyError` will be raised.

> ❓ What happens when we access a property that does not exist in a JS object?

One option to avoid this error is to use the `get` method:

```python
skills = student['skills']
> KeyError: 'skills'
print( student.get('skills') )
> None
# Provide a default value if key not in dictionary
print( student.get('skills', {'HTML': 5, 'JAVASCRIPT': 4}) )
> {'HTML': 5, 'JAVASCRIPT': 4}
```

## The `in` operator

Another way to avoid the `KeyError` is to use the `in` operator to check if the dictionary includes a key:

```python
if 'course' in student:
  print( f"{student['name']} is enrolled in {student['course']}")
else:
  print( f"{student['name']} is not enrolled in a course")
```

## Adding items

Simply assigning to a *key* that does not exist will create a new item in the dictionary.

Let’s add an item to `student`:

```python
student['age'] = 21
```

> ❓ If an `'age'` item already existed, what would happen?

## Deleting items

The `del` statement is used to delete an item from a dictionary:

```python
del student['age']
# Verify that item was deleted
'age' in student
> False
```

## Number of items

Use the built-in `len` function to retrieve the number of items in a dictionary:

```python
print( student )
> {'name': 'Tina', 'course': 'SEI'}
len(student)
> 2
len({})
> 0
```

## Dictionaries - iterating items

`for` loops are used to iterate over the items in a dictionary.

However, accessing the value of an item as follows is considered to be a Python [**anti-pattern**](https://en.wikipedia.org/wiki/Anti-pattern):

```python
for key in student:
  print( f"{key} = {student[key]}" )
```

The preferred approach is to use the `items()` method to obtain a [**dictionary view object**](https://docs.python.org/3/library/stdtypes.html#dictionary-view-objects).

`student.items()` returns a wrapped set of (key, value) tuples:

```python
student.items()
> dict_items([('name', 'Tina'), ('course', 'SEI')])
```

Then use a `for in` loop to iterate over the view object:

```python
for key, val in student.items():
  print( f"{key} = {val}" )
```

The `for` statement “unpacks” the tuples by assigning its values to multiple variables like with `key, val` above.


## 🧠 You Do (10 minutes) 

1. Define a Python dictionary named `where_my_things_are` containing a few items where:
    - the `keys` are things you have, and
    - the `values` are the locations you keep those things.
2. Write a `for` loop that iterates over the items in the dictionary and prints each one as
    
    ***My [thing] is kept [location]***

### Dictionary review questions ❓

1. What are dictionaries similar to in JS?
2. Why might the following code not work?
  ```python
  menu = {
    hamburger: 4.99,
    french_fries: 1.99,
    taco: 2.99
  }
  ```
3. What operator can we use to remove an item from a dictionary?
4. Assuming this dictionary:
  ```python
  fruit = {
  'apples': 'red',
  'bananas': 'yellow',
  'oranges': 'orange'
  }
  ```
Identify the problem with this statement:
  ```python
  color_of_bananas = fruit.bananas
  ```
