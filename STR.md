# Pandas `.str` — String Operations

> [!summary] Mental Model
> `.str` gives Pandas access to **vectorized string operations** on a Series.
>
> Instead of looping through every string:
>
> ```python
> for value in df["column"]:
>     ...
> ```
>
> Pandas lets you operate on the entire column:
>
> ```python
> df["column"].str.method()
> ```

---

# 1. Inspect / Check

These methods return information or Boolean values about each string.

| Method | Purpose | Example |
|---|---|---|
| `.str.len()` | Get string length | `df["name"].str.len()` |
| `.str.isdigit()` | Contains only digits? | `df["id"].str.isdigit()` |
| `.str.isalpha()` | Contains only letters? | `df["name"].str.isalpha()` |
| `.str.isalnum()` | Contains only letters/numbers? | `df["code"].str.isalnum()` |

```python
df["name"].str.len()
````

```python
Jayson → 6
Alice  → 5
Mark   → 4
```

```python
df["value"].str.isdigit()
```

```python
"123"    → True
"456"    → True
"123abc" → False
```

```python
df["name"].str.isalpha()
```

```python
"Jayson" → True
"Mark1"  → False
"Mark!"  → False
```
# 2. Transform / Clean

These methods modify the strings.

|Method|Purpose|
|---|---|
|`.str.lower()`|Convert to lowercase|
|`.str.upper()`|Convert to uppercase|
|`.str.strip()`|Remove whitespace at beginning/end|
|`.str.replace()`|Replace text|

### Lowercase

```python
df["name"].str.lower()
```

```python
"JAYSON" → "jayson"
"Alice"  → "alice"
```

### Uppercase

```python
df["name"].str.upper()
```

### Remove surrounding whitespace

```python
df["name"].str.strip()
```

```python
"  Jayson  " → "Jayson"
```

> [!tip] Data Cleaning  
> `.str.strip()` is especially useful when cleaning imported Excel/CSV data because users often accidentally enter spaces.

### Replace

```python
df["phone"].str.replace("-", "")
```

```python
0917-123-4567
        ↓
09171234567
```

---

# 3. Search / Find

These are extremely important for filtering DataFrames.

## `.str.contains()`

Checks whether a string contains something **anywhere**.

```python
df["email"].str.contains("@")
```

Example:

```python
john@gmail.com → True
hello          → False
```

### Mental model

```python
"Does this exist ANYWHERE?"
```

---

## `.str.startswith()`

Checks whether a string starts with something.

```python
df["code"].str.startswith("JBL1")
```

```python
JBL123 → True
JBL1   → True
1JBL1  → False
ABCJBL1 → False
```

### Mental model

```python
"Does this BEGIN with this?"
```

---

## `.str.endswith()`

Checks whether a string ends with something.

```pythonpython
df["email"].str.endswith("@leetcode.com")
```

```pythonpython
john@leetcode.com → True
john@gmail.com     → False
```

### Mental model

```pythonpython
"Does this END with this?"
```

---

# 4. `contains` vs `startswith` vs `endswith`

This distinction is important.

```python
contains
    ↓
ANYWHERE
```

```python
df["column"].str.contains("JBL1")
```

---

```python
startswith
    ↓
BEGINNING
```

```python
df["column"].str.startswith("JBL1")
```

---

```python
endswith
    ↓
END
```

```python
df["column"].str.endswith("JBL1")
```

### Quick reference

|Question|Method|
|---|---|
|Does it appear anywhere?|`.str.contains()`|
|Does it start with...?|`.str.startswith()`|
|Does it end with...?|`.str.endswith()`|

---

# 5. Character Access

You can access characters using indexing.

## First character

```python
df["name"].str[0]
```

```python
Jayson → J
Alice  → A
Mark   → M
```

## Second character

```python
df["name"].str[1]
```

## First 3 characters

```python
df["name"].str[:3]
```

```python
Jayson → Jay
Alice  → Ali
```

---

# 6. Chaining `.str`

`.str` operations can be chained.

Example:

```python
users["mail"].str[0].str.isalpha()
```

Read this from left to right:

```python
users["mail"]
      ↓
get first character
      ↓
check if that character is a letter
```

Example:

```python
"alice@gmail.com" → "a" → True
"2bob@gmail.com"  → "2" → False
```

> [!important] Why `.str` appears twice  
> `.str[0]` extracts the first character but still returns a **Series**.
> 
> Since we're still working with a Series, we need `.str` again:
> 
> ```python
> .str[0].str.isalpha()
> ```

---

# 7. Splitting Strings

## `.str.split()`

Splits a string into pieces.

```python
df["name"].str.split()
```

```python
"John Smith"
      ↓
["John", "Smith"]
```

You can specify a separator:

```python
df["code"].str.split("-")
```

```python
"ABC-123-XYZ"
      ↓
["ABC", "123", "XYZ"]
```

# 11. `.str` + Boolean Filtering

`.str` becomes especially powerful when combined with `.loc`.

Example:

```python
df.loc[
    df["email"].str.endswith("@gmail.com")
]
```

Meaning:

```python
email column
    ↓
check every email
    ↓
True / False
    ↓
.loc filters the rows
```

---

# 12. Multiple String Conditions

Use:

```
&
```

for AND

and:

```
|
```

for OR.

Example:

```python
condition = (
    df["email"].str.endswith("@gmail.com")
    &
    df["email"].str.len().gt(10)
)
```

Then:

```python
df.loc[condition]
```

> [!warning] Parentheses  
> When combining Pandas Boolean conditions, put each condition in parentheses:
> 
> ```
> (condition1) & (condition2)
> ```
> 
> Not:
> 
> ```
> condition1 & condition2
> ```
> 
> when operator precedence could make the expression ambiguous.

---

# 13. Common LeetCode Patterns

## Find emails ending with a domain

```python
df.loc[
    df["mail"].str.endswith("@leetcode.com")
]
```

---

## Find names starting with M

```python
df.loc[
    df["name"].str.startswith("M")
]
```

---

## Find strings longer than 15 characters

```python
df.loc[
    df["content"].str.len() > 15
]
```

---

## Find values containing a word

```python
df.loc[
    df["description"].str.contains("Python")
]
```

---

## Find values whose first character is a letter

```python
df.loc[
    df["code"].str[0].str.isalpha()
]
```

---

# 14. `.str` Problem-Solving Workflow

When a LeetCode problem involves text, ask:

### Step 1 — What am I looking for?

```
A specific value?
A prefix?
A suffix?
Something anywhere?
A pattern?
A length?
A particular character?
```

### Step 2 — Pick the simplest `.str` method

```
Anywhere       → contains()
Beginning      → startswith()
End             → endswith()
Length          → len()
First character → str[0]
Letters only    → isalpha()
Digits only     → isdigit()
Clean spaces    → strip()
Change text     → replace()
```

### Step 3 — Only use regex when necessary

Don't immediately reach for:

```
.str.match(r"...")
```

Ask:

> "Can `.startswith()`, `.endswith()`, `.contains()`, etc. solve this?"

If yes, use the simpler method.

### Step 4 — Turn the result into a Boolean condition

```
condition = df["column"].str.startswith("ABC")
```

### Step 5 — Filter using `.loc`

```
df.loc[condition]
```

---

# 15. Quick `.str` Decision Tree

```
I need to work with text
        │
        ▼
What am I trying to do?
        │
        ├── Measure it
        │     └── .str.len()
        │
        ├── Clean/change it
        │     ├── .str.lower()
        │     ├── .str.upper()
        │     ├── .str.strip()
        │     └── .str.replace()
        │
        ├── Find something
        │     ├── Anywhere → .str.contains()
        │     ├── Beginning → .str.startswith()
        │     └── End → .str.endswith()
        │
        ├── Inspect characters
        │     ├── .str[0]
        │     ├── .str.isalpha()
        │     ├── .str.isdigit()
        │     └── .str.isalnum()
        │
        ├── Split it
        │     └── .str.split()
        │
        └── Complex pattern
              └── Regex
```

---

# ⭐ Most Important Things to Remember

If you're rushing through a LeetCode problem, remember these first:

```python
# Length
df["col"].str.len()

# Lowercase / uppercase
df["col"].str.lower()
df["col"].str.upper()

# Clean whitespace
df["col"].str.strip()

# Anywhere
df["col"].str.contains("text")

# Beginning
df["col"].str.startswith("text")

# End
df["col"].str.endswith("text")

# Character
df["col"].str[0]

# Letters?
df["col"].str.isalpha()

# Digits?
df["col"].str.isdigit()

# Letters/numbers?
df["col"].str.isalnum()

# Split
df["col"].str.split()

# Regex
df["col"].str.match(r"...")
df["col"].str.fullmatch(r"...")
```

> [!tip] The key mindset  
> Don't memorize `.str` methods as isolated functions.
> 
> Think about **what question you're asking about the text**:
> 
> **"How long?" → `len()`**
> 
> **"Does it contain?" → `contains()`**
> 
> **"Does it start?" → `startswith()`**
> 
> **"Does it end?" → `endswith()`**
> 
> **"What is the first character?" → `.str[0]`**
> 
> **"Is it a letter/digit?" → `isalpha()` / `isdigit()`**
> 
> **"Does it follow a complicated pattern?" → regex**