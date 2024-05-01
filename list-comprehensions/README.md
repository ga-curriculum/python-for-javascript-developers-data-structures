# ![Python for JavaScript Developers - Python Data Structures - List Comprehensions](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create and work with lists using list comprehensions.

## Purpose

*List comprehensions* are a powerful feature in Python.

They provide a concise way to create and work with lists.

They will seem confusing as first, but they certainly are a favorite of *Python fans* and you will probably come across them when googling.

## Numerical Example

Say we needed to square all of the numbers in a list and put them into a new list, we might use a for loop like this:

```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
	
# I want 'n * n' for each 'n' in nums 
squares = []
for n in nums:
  squares.append(n * n)
print(squares)
> [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

>❓ What method in JS could we use in this scenario?

A list comprehension can reduce this code:

```python
squares = []
for n in nums:
  squares.append(n * n)
```

To this:

```python
squares = [n * n for n in nums]
```

## Basic syntax

Here’s the basic syntax of a list comprehension:

```python
# [<expression> for <item> in <list>]
# This reads as: I want <expression> for each <item> in <list>
```

As you can see, a list comprehension is basically a modified `for` loop within square brackets which, as we know, returns a new list.

## Filtering the Items

We just saw how list comprehensions are a nice way to map a list, but they can be used for **filtering** too.

Again, let’s start with a non-comprehension approach by using a `for` loop to map and filter `nums`:

```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
	
# I want 'n * n' for each 'n' in nums  if 'n * n' is even
even_squares = []
for n in nums:
  square = n * n 
  if square % 2 == 0:
    even_squares.append(square)
print(even_squares)
> [4, 16, 36, 64, 100]
```

Again list comprehensions reduce the above from:

```python
even_squares = []
for n in nums:
  square = n * n 
  if square % 2 == 0:
    even_squares.append(square)
```

To this one-liner:

```python
even_squares = [n * n for n in nums if (n * n) % 2 == 0]
```

Talk about less is more!

### List Comprehensions - Review Questions ❓

1. What characters start and end a list comprehension
2. True or False: A list comprehension creates a new list?