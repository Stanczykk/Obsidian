## Extracting Data from Multidimensional Arrays

For a 2D NumPy array, use:

```python
array[rows, columns]
```

### Slicing

Slicing extracts a **range of values** using:

```python
array[start : stop : step]
```

For 2D arrays:

```python
array[rows, columns]
```

Examples:

```python
a[0:2, 1:3]   # Rows 0-1, columns 1-2
a[0, :]        # Entire row 0
a[:, 1]        # Entire column 1
a[:, :]        # Entire array
```

Remember:

- `start` is **inclusive**
    
- `stop` is **exclusive**
    
- `:` means **all**
    
- Slicing usually creates a **view**, which may share memory with the original array
    
- Use `.copy()` to create an independent array
    

```python
b = a[0:2, 1:3].copy()
```

### Indexing

Extract a **specific value** by providing its position:

```python
a[row, column]
```

Example:

```python
a[1, 2]   # Row 1, column 2
```

### Boolean Masking

Extract values that satisfy a **condition**:

```python
a[a > 50]
```

Returns all values greater than `50`.

Useful for filtering data based on conditions.

### Fancy Indexing

Extract **specific, non-contiguous indexes** by providing a list of indexes:

```python
a[[0, 2], :]      # Rows 0 and 2
a[:, [0, 2]]      # Columns 0 and 2
```

Unlike slicing, the selected indexes do not need to be next to each other.

### `np.where()`

Find the **positions** where a condition is true:

```python
np.where(a > 50)
```

Returns the row and column indexes of values greater than `50`.

### Extraction Mental Model

|What you need|Use|
|---|---|
|Specific value|Indexing|
|Range of values|Slicing|
|Whole row/column|`:`|
|Values matching a condition|Boolean masking|
|Specific non-contiguous indexes|Fancy indexing|
|Positions matching a condition|`np.where()`|