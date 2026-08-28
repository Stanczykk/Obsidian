## dtype

`dtype` tells you **what data type the elements in a NumPy- array have**.

```
arr = np.array([1, 2, 3])

arr.dtype
# dtype('int64')
```

You can also specify the type when creating the array:

```
arr = np.array([1, 2.2, 3], dtype=np.float32)
```

Common types:

```
int      → Whole numbers
float    → Decimal numbers
bool     → True / False
str      → Text=
```

## astype()

`astype()` **converts an array to another data type**.

```
arr = np.array([1, 2, 3])

new_arr = arr.astype(np.float32)
```

```
arr.dtype       # int64
new_arr.dtype   # float32
```

By default, `astype()` returns a **new array** and does not change the original.

### 🧠 Mental Model

```
dtype     → "What type am I?"
astype()  → "Convert me to this type."
```

### Quick Comparison

| ``            | dtype()         | astype()                |
| ------------- | --------------- | ----------------------- |
| Purpose       | Check data type | Convert data type       |
| Type          | Attribute       | Method                  |
| Changes data? | No              | Creates converted array |
