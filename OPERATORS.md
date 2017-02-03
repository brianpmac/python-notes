## Boolean and logical operators

| **Operation name**    | **Operator** | **Explanation**                                                 |  
| --------------------- | ------------ | --------------------------------------------------------------- |  
| less than             | <            | Less than operator                                              |  
| greater than          | >            | Greater than operator                                           |  
| less than or equal    | <=           | Less than or equal to operator                                  |  
| greater than or equal | >=           | Greater than or equal to operator                               |  
| equal                 | ==           | Equality operator                                               |  
| not equal             | !=           | Not equal operator                                              |  
| logical and           | and          | Both operands True for result to be True                        |  
| logical or            | or           | One or the other operand is True for the result to be True      |  
| logical not           | not          | Negates the truth value, False becomes True, True becomes False |

```python
>>> True and False
False
>>> True and True
True
>>> False and True
False
>>> False or True
True
>>> False or False
False
>>> not True
False
>>> not False
True
```

## Operations on any sequence in Python

| **Operation name** | **Operator** | **Explanation**                         |  
| ------------------ | ------------ | --------------------------------------- |  
| indexing           | [ ]          | Access an element of a sequence         |  
| concatenation      | +            | Combine sequences together              |  
| repetition         | *            | Concatenate a repeated number of times  |  
| membership         | in           | Ask whether an item is in a sequence    |  
| length             | len          | Ask the number of items in the sequence |  
| slicing            | [ : ]        | Extract a part of a sequence            |

```python
>>> my_list = [0] * 6
>>> my_list
[0, 0, 0, 0, 0, 0]
>>> my_list = [1, 2, 3, 4]
>>> A = [my_list] * 3
>>> print(A)
[[1, 2, 3, 4], [1, 2, 3, 4], [1, 2, 3, 4]]
>>> my_list[2] = 45
>>> print(A)
[[1, 2, 45, 4], [1, 2, 45, 4], [1, 2, 45, 4]]
```
