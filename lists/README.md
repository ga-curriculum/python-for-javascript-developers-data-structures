# ![Python for JavaScript Developers - Python Data Structures - Lists](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create and manipulate lists in Python. 

## Purpose

**Lists** are to Python as **arrays** are to JS.

A **list** provides a container for zero or more items (*elements*).

**Lists** can contain items of different types, including dictionaries and nested lists.

**Lists** have a class (type) of `list`.

## Basic syntax
Like arrays in JS, a list can be created with a set of square brackets:

```python
colors = ['red', 'green', 'blue']
```

The number of items in a list is returned using the built-in `len()` function:

```python
len(colors)
> 3
```

## Features

Lists are considered to be a *sequence* type in Python. A *sequence* is a generic term used for an **ordered** collection. Other *sequence* types in Python include **strings** and **tuples**.

Lists are mutable:

- Items within a list can be replaced
- Items can be added and removed from a list

## Accessing items

Accessing the individual items of a list is much like accessing elements in a JS array, i.e., by using square brackets with an expression that evaluates to an integer:

```python
idx = 1
colors[idx + 1]
> blue
```

However, unlike in JS, we can use negative integers to index from the end of a list:

```python
colors[-1]
> blue
```

No need to write code like `colors[len(colors) - 1]` - yay!

## Assigning items

We also use square brackets to target an item of a list for assignment:

```python
colors[-1] = 'brown'
print(colors)
> ['red', 'green', 'brown']
```

Unlike with JS arrays, assigning to a non-existing index results in an error:

```python
colors[10] = 'yellow'
> IndexError: list assignment index out of range
```

## Adding an item

The equivalent to JS’s `push()` method is `append()`:

```python
colors.append('purple')
```

However, unlike JS’s `push()` method, `append()` can only add one item and does not return a value.

For adding multiple items, use the `extend()`:

```python
colors.extend(['orange', 'black'])
```

In Python, the `+` operator can be used to create a new list by combining them:

```python
odds = [1, 3, 5]
evens = [2, 4, 6]
nums = odds + evens
print(nums)
> [1, 3, 5, 2, 4, 6]
```

> ❓ How can we combine arrays in JavaScript into a new array?

## Inserting an item

To add an item anywhere within a list, use the `insert()` method:

```python
print(colors)
> ['red', 'green', 'brown', 'purple', 'orange', 'black']
colors.insert(1, 'yellow')
> ['red', 'yellow', 'green', 'brown', 'purple', 'orange', 'black']
```

## Removing an item

Yup, there’s a `pop()` method, but it’s more flexible in Python because you can specify the index of the item to remove and return:

```python
print(colors)
> ['red', 'yellow', 'green', 'brown', 'purple', 'orange', 'black']
green = colors.pop(2)
print(colors)
> ['red', 'yellow', 'brown', 'purple', 'orange', 'black']
```

If you don’t care about the value returned by `pop()`, you can also use the `del` operator to delete an item:

```python
print(colors)
> ['red', 'yellow', 'brown', 'purple', 'orange', 'black']
del colors[1]
print(colors)
> ['red', 'brown', 'purple', 'orange', 'black']
```

Also there’s a `remove()` method that removes the first item that matches what you pass in:

```python
print(colors)
> ['red', 'brown', 'purple', 'orange', 'black']
colors.remove('orange')
print(colors)
> ['red', 'brown', 'purple', 'black']
```

No value is returned by the `remove()` method.

## Clearing an entire list

The `clear()` method does just what you’d think:

```python
print(colors)
> ['red', 'brown', 'purple', 'black']
colors.clear()
print(colors)
> []
```

## Iterating over items in a list

The `for in` loop is used to iterate over the items in a list:

```python
colors = ['red', 'green', 'blue']
for color in colors:
  print(color)
> red
> green
> blue
```

If we need to access the index of the item while iterating over a list, we use the built-in `enumerate()` function to provide the index and the value to a `for` loop:

```python
for idx, color in enumerate(colors):
  print(idx, color)
> 0 red
> 1 green
> 2 blue
```

### List review questions❓

1. What are lists similar to in JS?
2. What is one way to add items to a list?
3. What operator can we use to remove an item from a list?

