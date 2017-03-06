## Flask notes

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
