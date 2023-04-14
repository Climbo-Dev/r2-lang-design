R2 is considered a strong typed language but provide native support for dynamic types.

In `Python`, type annotation is merely a hint:

```python
# Python
class X:
    def __str__(self):
        return 'X'

class Y:
    def __str__(self):
        return 'Y'

def foo(x: X) -> None:
    print(x)

foo(X())
foo(Y()) # OK!
```

In our opinion, explicit types should be enforced, unannotated types can be tolerated.

R2 supports two kinds of types:

* explicit type - variables with explicit type annotation, such as `def foo(x: X)`
* dynamic type - variables with no type annotation, such as `def foo(x)`

All dynamic typed variables are of type `R2Object` (simliar to `PyObject`):

* convert an explicit typed variable `x` to a dynamic typed variable: `x.wrap()`.
* convert a dynamic typed variable to an explicit typed variable: `x.unwrap()`.


