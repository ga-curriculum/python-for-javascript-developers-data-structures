# ![Python Data Structures - Tuples](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create and manipulate tuples in Python.

## Purpose

**Tuples** in Python are very similar to Python **lists**.

Tuples have a class (type) of `tuple`.

You may come across tuple’s being “classified” based on how many items they contain, e.g., a **2-tuple** would be used to hold a `key` and its `value`.

## Basic syntax

Tuples can be defined in a few different ways. Most basically, they are defined like this:

```python
colors = ('red', 'green', 'blue')
print(colors)
> ('red', 'green', 'blue')
print( len(colors) )
> 3
```

The parentheses are actually optional (except when creating an empty tuple), however, the use of parens is popular.

Here’s how an empty tuple is created:

```python
things = ()
print( type(things) )
> <class 'tuple'>
```

If you need to create a 1-tuple (a tuple with one item), be aware that a comma is necessary:

```python
# Will not create a tuple
hello_tuple = ('Hello')
print( type(hello_tuple) )
>  <class 'str'>

hello_tuple = ('Hello',)
# or just the following (no parens required)
hello_tuple = 'Hello',
print( type(hello_tuple) )
> <class 'tuple'>
```

## Differences between tuples & lists

The main difference between tuples and lists is that tuples are immutable.

Since tuples can’t be changed after they are created, they are great for protecting data that you don’t want to be changed.

Python iterates over tuples faster than lists.

Because they are immutable, tuples can even be used as keys for dictionaries.

Generally, you’ll find that tuples are used to contain heterogeneous (different) data types and lists for homogeneous (similar) data types.

## Accessing items

Although tuples can’t be modified like lists, we can retrieve their items in the same way using square brackets:

```python
colors = ('red', 'green', 'blue')
green = colors[1]
print(green)
> green
```

Sequences (lists, tuples & strings) also have an `index()` method that returns the index of the first match:

```python
colors = ('red', 'green', 'blue')
blue_idx = colors.index('blue')
print(blue_idx)
> 2
```

## Iteration

The items in tuples are iterated over by using `for` loops as we saw previously with lists:

```python
colors = ('red', 'green', 'blue')
for idx, color in enumerate(colors):
  print(idx, color)
> 0 red
> 1 green
> 2 blue
```

## Unpacking tuples

Tuples (and other sequences such as lists & strings) have a convenient feature, called unpacking, for performing multiple variable assignments in a single line of code:

```python
colors = ('red', 'green', 'blue')
r, g, b = colors
print(r, g, b)
> red green blue
```

Comma separated variables on the left-side of the assignment operator and a sequence of values on the right is what it takes.

FYI, we were seeing unpacking in action within the `for in` loops above, for example:

```python
for key, val in student.items():
  print( f"{key} = {val}" )
```

## Sequences can be “sliced”

Slicing in Python is used to create “slices” (copies) of sequences.

However, instead of using a `slice` method like we did in JS, Python has a cool “slice” operator that uses this syntax:

```python
a_sequence[m:n]
```

Just like with indexing, slicing uses square brackets, but adds a colon:

```python
short_name = 'Alexandria'[0:4]
print(short_name)
> Alex
```

Note that the slice includes up to, but not including the index to the right of the colon.

> ❓ Is this the same as with the ending index in JS’s `slice` method?

If the first index is omitted, the slice copies the sequence starting at the beginning (index of `0`):

```python
colors = ('red', 'green', 'blue')
print( colors[:2] )
> ('red', 'green')
```

If the up to index is omitted, the slice copies the sequence all the way to the end:

```python
colors = ['red', 'green', 'blue']
print( colors[1:] )
> ['green', 'blue']
```

>❓ What would the value of `fruits` be?

```python
fruit = ('apples', 'bananas', 'oranges')
fruits = fruit[:]
```
