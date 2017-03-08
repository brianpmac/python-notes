## Flask notes

### Starting the app

Using this at the bottom of the main file is deprecated as of version 0.12:

```python
if __name__ == "__main__":
    app.run(debug=True)
```

Instead, simply do not include the above in your file, and do this on the command line:

```bash
$ export FLASK_APP=/path/to/file.py
$ export FLASK_DEBUG=True
$ flask run
```

### Jinja2

Strip all leading and trailing whitespace from Jinja blocks:

```python
app.jinja_env.trim_blocks = True
app.jinja_env.lstrip_blocks = True
```

Use `+` and `-` to control whitespace on individual blocks. This overrides the global settings above:

```python
{%- if ... %} strips before
{% if ... +%} preserves after
{%+ if ... -%} preserves before and strips after
remember that `{% endif %}` is treated separately
```
