## Lists

A `list` is an ordered collection of zero or more references to Python data objects. Lists are written as comma-delimited values enclosed in square brackets. The empty list is simply `[ ]`. Lists are **heterogeneous**, meaning that the data objects need not all be from the same class and the collection can be assigned to a variable as below. The following fragment shows a variety of Python data objects in a list:

```python
>>> [1, 3, True, 6.5, 'Sally']
[1, 3, True, 6.5, 'Sally']
>>> my_list = [1, 3, True, 6.5, 'Sally']
>>> my_list
[1, 3, True, 6.5, 'Sally']
```

## List methods

| **Method name** | **Use**                | **Explanation**                                     |  
| --------------- | ---------------------- | --------------------------------------------------- |  
| `append`        | `alist.append(item)`   | Adds a new item to the end of a list                |  
| `insert`        | `alist.insert(i,item)` | Inserts an item at the ith position in a list       |  
| `pop`           | `alist.pop()`          | Removes and returns the last item in a list         |  
| `pop`           | `alist.pop(i)`         | Removes and returns the ith item in a list          |  
| `sort`          | `alist.sort()`         | Modifies a list to be sorted                        |  
| `reverse`       | `alist.reverse()`      | Modifies a list to be in reverse order              |  
| `del`           | `del alist[i]`         | Deletes the item in the ith position                |  
| `index`         | `alist.index(item)`    | Returns the index of the first occurrence of `item` |  
| `count`         | `alist.count(item)`    | Returns the number of occurrences of `item`         |  
| `remove`        | `alist.remove(item)`   | Removes the first occurrence of `item`              |

## Using `range` with lists

```python
>>> range(10)
range(0, 10)
>>> list(range(10))
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
>>> range(5,10)
range(5, 10)
>>> list(range(5,10))
[5, 6, 7, 8, 9]
>>> list(range(5,10,2))
[5, 7, 9]
>>> list(range(10,1,-1))
[10, 9, 8, 7, 6, 5, 4, 3, 2]
```

## List comprehensions

List comprehensions are used to construct lists in a very natural, easy way. Basic syntax of a list comprehension:

```python
[ expression for item in list if conditional ]
```

Suppose we want to find the first 10 perfect squares. We could use a `for` loop:

```python
>>> sqlist = []
>>> for x in range(1,11):
...     sqlist.append(x*x)
... 
>>> sqlist
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

But a list comprehension allows us to do this one step:

```python
>>> sqlist = [x*x for x in range(1,11)]
>>> sqlist
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

You can also add a selection criteria so that only certain items get added to the list:

```python
>>> sqlist = [x*x for x in range(1,11) if x%2 != 0]
>>> sqlist
[1, 9, 25, 49, 81]
```

Any sequence that supports iteration can be used within a list comprehension to construct a new list:

```python
>>> [char.upper() for char in 'comprehension' if char not in 'aeiou']
['C', 'M', 'P', 'R', 'H', 'N', 'S', 'N']
```

