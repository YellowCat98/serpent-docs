# Printing to the console
- Normally you'd think of just using `print` from Python's standard library.
- But that makes a direct call to stdout, making it impossible to tell which mod is printing.
- Serpent introduces `script.info`, `script.debug`, `script.warn` and `script.error`, which you can use the same exact way, here's an example

```python
sigma = False
def MenuLayer_init(self, this):
    if not sigma:
        self.script.error("You are not sigma.")
    else:
        self.script.info("You are sigma!")
```
**Remember that using `input` does not work at all, at it makes a call to stdin and geode restricts stdin calls, it only allows stdout.**