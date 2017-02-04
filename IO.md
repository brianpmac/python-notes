## Print function

The print function takes zero or more parameters and displays them with a single blank space as the default separator. You can change the default separator with the `sep` argument. Each print ends with a newline character by default. You can change it with the `end` argument.

```python
>>> print('Hello')
Hello
>>> print('Hello', 'World')
Hello World
>>> print('Hello', 'World', sep='^')
Hello^World
>>> print('Hello', 'World', end=' :)')
Hello World :)>>>
```

Use string formatting to write `print(aName, "is", age, "years old.")` as `print("%s is %d years old." % (aName, age))`. The `%` operator is a string operator called the format operator. The format string may contain one or more conversion specifications. A conversion character tells the format operator what type of value is going to be inserted into that position in the string. In the example above, the `%s` specifies a string, while the `%d` specifies an integer. Other possible type specifications include `i`, `u`, `f`, `e`, `g`, `c`, or `%`. 

| **Character** | **Output format**                                                                                |  
| ------------- | ------------------------------------------------------------------------------------------------ |  
| `d`, `i`      | Integer                                                                                          |  
| `u`           | Unsigned integer                                                                                 |  
| `f`           | Floating point as m.ddddd                                                                        |  
| `e`           | Floating point as m.ddddde+/-xx                                                                  |  
| `E`           | Floating point as m.dddddE+/-xx                                                                  |  
| `g`           | Use `%e` for exponents less than (-4) or greater than (+5), otherwise use `%f`                   |  
| `c`           | Single character                                                                                 |  
| `s`           | String, or any Python data object that can be converted to a string by using the `str` function. |  
| `%`           | Insert a literal % character                                                                     |

In addition to the format character, you can also include a format modifier between the `%` and the format character. Format modifiers may be used to left-justify or right-justifiy the value with a specified field width. Modifiers can also be used to specify the field width along with a number of digits after the decimal point.

| **Modifier** | **Example** | **Description**                                                                                  |  
| ------------ | ----------- | ------------------------------------------------------------------------------------------------ |  
| number       | `%20d`      | Put the value in a field width of 20                                                             |  
| `-`          | `%-20d`     | Put the value in a field 20 characters wide, left-justified                                      |  
| `+`          | `%+20d`     | Put the value in a field 20 characters wide, right-justified                                     |  
| `0`          | `%020d`     | Put the value in a field 20 characters wide, fill in with leading zeros.                         |  
| `.`          | `%20.2f`    | Put the value in a field 20 characters wide with 2 characters to the right of the decimal point. |  
| `(name)`     | `%(name)d`  | Get the value from the supplied dictionary using `name` as the key.                              |

```python
>>> city = 'London'
>>> year_founded = 50
>>> print('The city of %s was founded in the year %d.' % (city, year_founded))
The city of London was founded in the year 50.
>>> print('The city of %s was founded in the year %04d.' % (city, year_founded)) 
The city of London was founded in the year 0050.
```

