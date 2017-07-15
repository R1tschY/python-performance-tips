# python-performance-tips

First read this: https://wiki.python.org/moin/PythonSpeed/PerformanceTips

Here I have written same micro-optimizing tips for CPython.

## Use built-in functions written in C

### Consider using `operator` module instead of lambdas

```python
l = [(1, 2, 'def'), (2, -4, 'ghi'), (3, 6, 'abc')]

l.sort(key=lambda x: x[1])

# better
import operator
l.sort(key=operator.itemgetter(1))
```


### Consider using `itertools` module for operations on container

## Avoid loading of globals

Loading a global variable is slow. Consider using local variables or keyword arguments:

```python
def f(x, _float=float)
  _float(x)
# is faster than
def f(x)
  float(x)

while 1:
  ...
# is faster than
while True:
  ...

```
