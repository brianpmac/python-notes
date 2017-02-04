## Sets

A set is an unordered collection of zero or more immutable Python data objects. Sets do not allow duplicates and are written as comma-delimited values enclosed in curly braces. The empty set is represented by set(). Sets are heterogeneous, and the collection can be assigned to a variable as below.

```python
>>> {3, 6, 'cat', 4.5, False}
{False, 'cat', 3, 4.5, 6}
>>> my_set = {3, 6, 'cat', 4.5, False}
>>> my_set
{False, 'cat', 3, 4.5, 6}
```

## Set operations

| **Operation name** | **Operator**       | **Explanation**                                                   |  
| ------------------ | ------------------ | ----------------------------------------------------------------- |  
| membership         | in                 | Set membership                                                    |  
| length             | len                | Returns the cardinality of the set                                |  
| `|`                | `aset | otherset`  | Returns a new set with all elements from both sets                |
| `&`                | `aset & otherset`  | Returns a new set with only those elements common to both sets    |  
| `-`                | `aset - otherset`  | Returns a new set with all items from the first set not in second |  
| `<=`               | `aset <= otherset` | Asks whether all elements of the first set are in the second      |

```python
>>> my_set
{False, 'cat', 3, 4.5, 6}
>>> len(my_set)
5
>>> False in my_set
True
>>> 'dog' in my_set
False
```

## Set methods

| **Method name** | **Use**                       | **Explanation**                                                |  
| --------------- | ----------------------------- | -------------------------------------------------------------- |  
| `union`         | `aset.union(otherset)`        | Returns a new set with all elements from both sets             |  
| `intersection`  | `aset.intersection(otherset)` | Returns a new set with only those elements common to both sets |  
| `difference`    | `aset.difference(otherset)`   | Returns a new set with all items from first set not in second  |  
| `issubset`      | `aset.issubset(otherset)`     | Asks whether all elements of one set are in the other          |  
| `add`           | `aset.add(item)`              | Adds item to the set                                           |  
| `remove`        | `aset.remove(item)`           | Removes item from the set                                      |  
| `pop`           | `aset.pop()`                  | Removes an arbitrary element from the set                      |  
| `clear`         | `aset.clear()`                | Removes all elements from the set                              |

```python
>>> my_set = {False, 'cat', 3, 4.5, 6}
>>> your_set = {99, 3, 100}
```

```python
>>> my_set.union(your_set)
{False, 3, 4.5, 99, 6, 100, 'cat'}
>>> my_set | your_set
{False, 3, 4.5, 99, 6, 100, 'cat'}
```

```python
>>> my_set.intersection(your_set)
{3}
>>> my_set & your_set
{3}
```

```python
>>> my_set.difference(your_set)
{False, 'cat', 4.5, 6}
>>> my_set - your_set
{False, 'cat', 4.5, 6}
```

```python
>>> {3, 100}.issubset(your_set)
True
>>> {3, 100} <= your_set
True
```

```python
>>> my_set.add('house')
>>> my_set
{False, 3, 4.5, 6, 'house', 'cat'}
```

```python
>>> my_set.remove(4.5)
>>> my_set
{False, 3, 6, 'house', 'cat'}
```

```python
>>> my_set.pop()
False
>>> my_set
{3, 6, 'house', 'cat'}
```

```python
>>> my_set.clear()
>>> my_set
set()
```
