## Rich Comparison Operators
#### `__lt__ means lower than`
#### `x<y calls x.__lt__(y)`

```
def __lt__(self, other):
    return self.attribute < other.attribute
```
