```
a = np.array(["a", "b", "c", "d", "e", "f"])
```

|Slice|Meaning|Result|
|---|---|---|
|`a[1:3]`|index 1 through before 3|`b c`|
|`a[:3]`|beginning through before 3|`a b c`|
|`a[3:]`|index 3 onward|`d e f`|
|`a[:]`|everything|`a b c d e f`|
|`a[::2]`|every 2nd element|`a c e`|
|`a[1::2]`|every 2nd starting at 1|`b d f`|
|`a[-3:]`|last 3|`d e f`|
|`a[:-2]`|everything except last 2|`a b c d`|
|`a[::-1]`|reverse|`f e d c b a`|


Slicing follows the pattern:

```python
array[start : stop : step]
```

- `start` → where to begin
    
- `stop` → where to stop **(exclusive)**
    
- `step` → how many positions to move
    

```python
a[1:3]      # Index 1 up to, but not including, 3
a[:3]       # Beginning up to index 3
a[3:]       # Index 3 to the end
a[:]        # Entire array
a[::2]      # Every 2nd element
a[::-1]     # Reverse the array
a[-3:]      # Last 3 elements
```

For 2D arrays, slicing follows:

```python
array[rows, columns]
```

```python
data[0, 1]       # Row 0, column 1
data[0, :]       # Entire row 0
data[:, 1]       # Entire column 1
data[0:2, 1:3]   # Rows 0-1 and columns 1-2
```

### View vs Copy

A slice usually creates a **view**, meaning it may share memory with the original array:

```python
b = a[1:4]          # View
```

Changing `b` may also change `a`.

Use `.copy()` to create an independent array:

```python
b = a[1:4].copy()   # Copy
```

Changing `b` will not affect `a`.

You can check whether two arrays may share memory with:

```python
np.may_share_memory(a, b)
```

**Mental model:**

```text
Slice → View → May share memory
.copy() → Copy → Independent data
```