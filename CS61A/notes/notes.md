# CS61A

## Lab 01

In Python, 0 is falsy, other numbers are all truthy.

Traceback message is organized with the **most recent call last**.

## Hw 02

### Q3: Make Repeater

```python
def make_repeater(func, n):
    """Return the function that computes the nth application of func."""
    return accumulate(compose1, func, n-1, lambda _: func) if n > 0 else lambda x: identity(x)
```

The optimal way to avoid the edge case when `n == 0` is to use `identity` function as the base of `accumulate`.

```python
def make_repeater(func, n):
    """Return the function that computes the nth application of func."""
    return accumulate(compose1, identity, n, lambda _: func)
```

### Q4: Church numerals
To really understand and absorb the power of abstraction. Don't use `accumulate` or `church_to_int` or `while`/`for` loop in this question.