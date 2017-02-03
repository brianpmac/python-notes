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
