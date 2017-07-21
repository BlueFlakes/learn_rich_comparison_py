## Rich Comparison Operators
#### `__le__ means ,,lower or equal"`
#### `x<=y calls x.__le__(y)`

```
def __le__(self, other):
    return self.attribute <= other.attribute
```
