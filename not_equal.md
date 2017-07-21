## Rich Comparison Operators
#### `__ne__ means ,,not equal"`
#### `x!=y calls x.__ne__(y)`

```
def __ne__(self, other):
    return self.attribute != other.attribute
```
