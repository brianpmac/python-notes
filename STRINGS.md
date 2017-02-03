## String methods

| **Method name** | **Use**                | **Explanation**                                           |  
| --------------- | ---------------------- | --------------------------------------------------------- |  
| `center`        | `astring.center(w)`    | Returns a string centered in a field of size `w`          |  
| `count`         | `astring.count(item)`  | Returns the number of occurrences of `item` in the string |  
| `ljust`         | `astring.ljust(w)`     | Returns a string left-justified in a field of size `w`    |  
| `lower`         | `astring.lower()`      | Returns a string in all lowercase                         |  
| `rjust`         | `astring.rjust(w)`     | Returns a string right-justified in a field of size `w`   |  
| `find`          | `astring.find(item)`   | Returns the index of the first occurrence of `item`       |  
| `split`         | `astring.split(schar)` | Splits a string into substrings at `schar`                |

```python
>>> 'Brian'
'Brian'
>>> my_name = 'Brian'
>>> my_name[3]
'a'
>>> my_name * 2
'BrianBrian'
>>> len(my_name)
5
>>> my_name
'Brian'
>>> my_name.upper()
'BRIAN'
>>> my_name.center(9)
'  Brian  '
>>> my_name.find('i')
2
>>> my_name.split('i')
['Br', 'an']
```

## Strings are immutable

While lists are mutable; strings are immutable. You can change an item in a list by using indexing and assignment:

```python
>>> my_list
[1, 3, True, 6.5]
>>> my_list[0]=2**10
>>> my_list
[1024, 3, True, 6.5]
```

But not in a string:

```python
>>> my_name
'Brian'
>>> my_name[0]='X'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment
```
