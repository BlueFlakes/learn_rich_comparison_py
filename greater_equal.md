## Rich Comparison Operators
#### `__ge__ means ,,greater or equal"`
#### `x>=y calls x.__ge__(y)`

```
def __ge__(self, other):
    return self.attribute >= other.attribute
```
