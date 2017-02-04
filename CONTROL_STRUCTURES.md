## Iterators

Python provides two iteration structures: the `while` statement, and the `for` statement.

The while statement repeats a body of code as long as a condition is true:

```python
>>> counter = 1
>>> while counter <= 5:
...     print('Hello, world')
...     counter = counter + 1
... 
Hello, world
Hello, world
Hello, world
Hello, world
Hello, world
```

The for statement can be used to iterate over the members of a collection, so long as the collection is a sequence (lists, tuples, and strings):

```python
>>> for item in [1, 3, 6, 2, 5]:
...     print(item)
... 
1
3
6
2
5
```

```python
>>> for item in range(5):
...     print(item**3)
... 
0
1
8
27
64
```

```python
>>> wordlist = ['cat', 'dog', 'rabbit']
>>> letterlist = []
>>> for word in wordlist:
...     for letter in word:
...             letterlist.append(letter)
... 
>>> print(letterlist)
['c', 'a', 't', 'd', 'o', 'g', 'r', 'a', 'b', 'b', 'i', 't']
```

## Selection statements

Python provides the `if`, `elif`, `else` selection contructs:

```python
if n<0:
    print("Sorry, value is negative")
else:
    print(math.sqrt(n))
```

```python
if n<0:
   n = abs(n)
print(math.sqrt(n))
```

```python
if score >= 90:
    print('A')
elif score >=80:
    print('B')
elif score >= 70:
    print('C')
elif score >= 60:
    print('D')
else:
    print('F')
```
