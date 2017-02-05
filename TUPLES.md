## Tuples

Tuples are like lists, but **immutable**. They can contain **heterogeneous** sequences of data, and you can perform many of the same operations as lists:

```python
>>> my_tuple = (2, True, 4.96)
>>> my_tuple
(2, True, 4.96)
```

```python
>>> len(my_tuple)
3
```

```python
>>> my_tuple[0]
2
```

```python
>>> my_tuple * 3
(2, True, 4.96, 2, True, 4.96, 2, True, 4.96)
```

```python
>>> my_tuple[0:2]
(2, True)
```

But you can't change the values of the tuple:

```python
>>> my_tuple[1] = False
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```
