## Read from files

`open()` Opens a file in Python. This won't contain the content of the file, it just points to it in memory.

`.read()` Reads the entire contents of the file object it's called on.

`.close()` Closes the file object it's called on. This clears the file out of Python's memory.

`r'string'` A raw string that makes writing regular expressions easier.

`re.match(pattern, text, flags)` Tries to match a pattern against the beginning of the text.

`re.search(pattern, text, flags)` Tries to match a pattern anywhere in the text. Returns the first match.

If you don't know the size of a file, it's better to read it a chunk at a time and close it automatically. The following snippet does that. The with causes the file to automatically close once the action inside of it finishes. And the action inside, the `.read()`, will finish when there are no more bytes to read from the file:
```python
with open("some_file.txt") as open_file:
    data = open_file.read()
```

## Escape characters

`\w` matches an Unicode word character. That's any letter, uppercase or lowercase, numbers, and the underscore character. In "new-releases-204", \w would match each of the letters in "new" and "releases" and the numbers 2, 0, and 4. It wouldn't match the hyphens.

`\W` is the opposite to \w and matches anything that isn't an Unicode word character. In "new-releases-204", \W would only match the hyphens.

`\s` matches whitespace, so spaces, tabs, newlines, etc.

`\S` matches everything that isn't whitespace.

`\d` is how we match any number from 0 to 9

`\D` matches anything that isn't a number.

`\b` matches word boundaries. What's a word boundary? It's the edges of word, defined by white space or the edges of the string.

`\B` matches anything that isn't the edges of a word.

## Counts

`\w{3}` matches any three word characters in a row.

`\w{,3}` matches 0, 1, 2, or 3 word characters in a row.

`\w{3,}` matches 3 or more word characters in a row. There's no upper limit.

`\w{3, 5}` matches 3, 4, or 5 word characters in a row.

`\w?` matches 0 or 1 word characters.

`\w*` matches 0 or more word characters. Since there is no upper limit, this is, effectively, infinite word characters.

`\w+` matches 1 or more word characters. Like *, it has no upper limit, but it has to occur at least once.

`.findall(pattern, text, flags)` finds all non-overlapping occurrences of the pattern in the text.
