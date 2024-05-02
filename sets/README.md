# ![Python for JavaScript Developers - Python Data Structures - Sets](./assets/hero.png)

**Learning objective:** By the end of this lesson, learners will be able to understand the concept of sets in Python, differentiate them from other data structures, and demonstrate how to create and manipulate sets.

## Introduction to sets in Python

n Python, a set is an unordered collection of unique elements. Unlike lists and tuples, sets do not allow duplicate elements. Sets are commonly used when dealing with mathematical operations like union, intersection, and difference.

## Creating sets

To create a set in Python, you can use curly braces `{}` or the built-in `set()` function. 

Here's how to create a set:

```python
# Using curly braces
my_set = {1, 2, 3, 4, 5}

# Using the set() function
another_set = set([5, 6, 7, 8, 9])
```

## Operations on sets

Sets support various operations such as adding elements, removing elements, and performing set operations like union, intersection, and difference.

### Adding elements

In Python, you can add elements to a set using the `add()` method. In JavaScript, you can add elements to a Set using the `add()` method as well.

```python
# Adding elements to a set
my_set.add(6)
```

### Removing elements

To remove elements from a set in Python, you can use the `remove()` method. In JavaScript, you can use the `delete()` method.

```python
# Removing elements from a set
my_set.remove(3)
```

### Set intersection

To find the intersection of two sets (i.e., the set of all elements present in both sets), you can use the `&` operator in Python. 

```python
# Set intersection
intersection_set = my_set & another_set
```

### Set difference

To find the set difference (i.e., the set of elements that are present in the first set but not in the second set), you can use the `-` operator in Python.

```python
# Set difference
difference_set = my_set - another_set
```

## You Do 🧠

Create a set named colors containing the following colors: "red", "green", "blue", "yellow". Then, add the color "orange" to the set. Finally, print the updated set to see the result.