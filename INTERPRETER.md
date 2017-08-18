## Re-import modules in the interpreter

You are in a Python session and have imported a module you've been working on. You make changes to the module and want the changes to reflect in your session. If you try using `import my_module` again you'll just get another copy of the original version you imported initially. Instead use `importlib.reload(my_module)`:

```
>>> import importlib
>>> importlib.reload(my_module)
```

The above works with **Python 3.4+**. For earlier versions use:

**Python 2.x**: `reload(my_module)`

**For Python 3.x**: `imp.reload(my_module)`

## Load a module directly into the interpreter

`python -i filename.py`
