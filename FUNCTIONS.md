## \*args and \*\*kwargs

### \*\*kwargs

Use \*\*kwargs in your function definition to pass in a dictionary of key-value pairs. Then use kwargs['key'] to extract the associated value in your function body. This is very useful for passing a large amount of arguments to a function. You can call \*\*kwargs whatever you want, such as \*\*data, but using \*\*kwargs is consisdered idiomatic Python by convention. The important part is the double \*\*asterisk.

```python
def my_function(**kwargs):
    value1 = kwargs['key1']
    value2 = kwargs['key2']
    value3 = kwargs['key3']
    
    print(value1, value2, value3)

my_dict = {'key1': 'foo', 'key2': 'bar', 'key3': 'fizz'}

my_function(**my_dict)
foo bar fizz
```

