# 🐼 Pandas Cheat Sheet — Fundamentals → LeetCode

## 1. The Big Picture

Pandas is mainly about working with **tabular data**.

The two objects you need to distinguish:

```
Series     → one-dimensional
DataFrame  → two-dimensional table
```

Think Excel:

```
DataFrame
┌────────┬────────┬────────┐
│ name   │ age    │ salary │
├────────┼────────┼────────┤
│ John   │ 25     │ 30000  │
│ Maria  │ 30     │ 40000  │
└────────┴────────┴────────┘
```

A column:

```
df["name"]
```

is a **Series**.

Multiple columns:

```
df[["name", "age"]]
```

is a **DataFrame**.

### ⭐ Critical distinction

```
df["name"]       # Series
df[["name"]]     # DataFrame
```

The extra brackets matter.

---

# 2. Creating / Loading Data

### CSV

```
df = pd.read_csv("file.csv")
```

### Excel

```
df = pd.read_excel("file.xlsx")
```

### Inspecting

```
df.head()
df.tail()
df.shape
df.columns
df.dtypes
df.info()
df.describe()
```

Mental model:

```
head()       → look at the beginning
tail()       → look at the end
shape        → rows × columns
columns      → column names
dtypes       → data types
info()       → structure + missing values
describe()   → statistics
```

---

# 3. Selecting Columns

### One column → Series

```
df["name"]
```

### Multiple columns → DataFrame

```
df[["name", "age", "salary"]]
```

### Mental model

```
["column"]              → Series
[["column1", "column2"]] → DataFrame
```

---

# 4. Filtering Rows

This is one of the most important Pandas skills.

```
df[df["age"] > 25]
```

Read it as:

> Give me rows where age is greater than 25.

### Multiple conditions

Use:

```
&
```

for **AND**

```
df[(df["age"] > 25) & (df["salary"] > 30000)]
```

Use:

```
|
```

for **OR**

```
df[(df["age"] > 25) | (df["salary"] > 30000)]
```

### NOT

```
~condition
```

Example:

```
df[~(df["city"] == "Manila")]
```

### ⚠️ Pandas uses `&` and `|`

Don't use:

```
and
or
```

for Series conditions.

Use:

```
&
|
~
```

---

# 5. `.loc`

`.loc` is extremely useful when you want to specify:

> **rows first, columns second**

```
df.loc[condition, ["name", "age"]]
```

Example:

```
df.loc[df["age"] > 25, ["name", "salary"]]
```

Meaning:

```
Rows:
    age > 25

Columns:
    name
    salary
```

This is a very clean pattern.

---

# 6. `loc` vs Normal Filtering

These are both valid:

```
df[df["age"] > 25]
```

and:

```
df.loc[df["age"] > 25]
```

But `.loc` becomes particularly useful when selecting columns at the same time:

```
df.loc[
    df["age"] > 25,
    ["name", "salary"]
]
```

---

# 7. Sorting

### DataFrame

```
df.sort_values(by="salary")
```

Descending:

```
df.sort_values(
    by="salary",
    ascending=False
)
```

Multiple columns:

```
df.sort_values(
    by=["department", "salary"],
    ascending=[True, False]
)
```

### Series

```
df["salary"].sort_values()
```

A Series doesn't need `by=` because there's only one thing being sorted.

---

# 8. Missing Values

### Detect missing values

```
df.isnull()
```

or:

```
df.isna()
```

They're essentially equivalent.

### Find rows where a column is missing

```
df[df["salary"].isnull()]
```

### Find rows where it isn't missing

```
df[df["salary"].notnull()]
```

or:

```
df[df["salary"].notna()]
```

### Drop missing values

```
df.dropna()
```

### Fill missing values

```
df["salary"].fillna(0)
```

---

# 9. Duplicates

Remove duplicate rows:

```
df.drop_duplicates()
```

Based on a particular column:

```
df.drop_duplicates(subset=["customer_id"])
```

### Important ordering lesson

If you want unique values **and then sort them**, usually:

```
df.drop_duplicates().sort_values(...)
```

rather than:

```
df.sort_values(...).drop_duplicates()
```

Why?

Because you're reducing the data first.

```
100,000 rows
      ↓
drop duplicates
      ↓
500 rows
      ↓
sort 500 rows
```

instead of:

```
100,000 rows
      ↓
sort 100,000 rows
      ↓
drop duplicates
```

---

# 10. Renaming Columns

```
df.rename(
    columns={
        "old_name": "new_name"
    }
)
```

Example:

```
df.rename(
    columns={
        "author_id": "id"
    }
)
```

You used this in the Article Views problem.

---

# 11. Selecting + Filtering + Sorting

A common Pandas pipeline:

```
result = (
    df.loc[
        df["age"] > 25,
        ["name", "age", "salary"]
    ]
    .sort_values(
        by="salary",
        ascending=False
    )
)
```

Think:

```
DataFrame
   ↓
filter rows
   ↓
select columns
   ↓
sort
   ↓
result
```

---

# 12. `groupby()`

This is where Pandas starts becoming a serious data-analysis tool.

Suppose:

|department|salary|
|---|---|
|IT|30000|
|IT|40000|
|HR|25000|
|HR|30000|

```
df.groupby("department")["salary"].mean()
```

Result conceptually:

|department|mean salary|
|---|---|
|HR|27500|
|IT|35000|

Mental model:

```
GROUP BY department
        ↓
split data into groups
        ↓
calculate something per group
```

---

# 13. Common Aggregations

```
.mean()
.sum()
.count()
.min()
.max()
.median()
.std()
```

Example:

```
df.groupby("department")["salary"].sum()
```

---

# 14. Multiple Aggregations

```
df.groupby("department")["salary"].agg(
    ["mean", "min", "max"]
)
```

Or:

```
df.groupby("department").agg(
    average_salary=("salary", "mean"),
    total_salary=("salary", "sum"),
    highest_salary=("salary", "max")
)
```

This second form is extremely useful in real analysis.

---

# 15. `transform()`

`groupby().agg()` **reduces** the data.

`transform()` generally **keeps the original number of rows**.

Example:

```
df["dept_avg"] = (
    df.groupby("department")["salary"]
      .transform("mean")
)
```

You might get:

|department|salary|dept_avg|
|---|---|---|
|IT|30000|35000|
|IT|40000|35000|
|HR|25000|27500|
|HR|30000|27500|

Mental model:

```
agg()
    ↓
one result per group

transform()
    ↓
result brought back to every original row
```

---

# 16. Combining DataFrames — `merge()`

### This is your primary joining tool.

```
pd.merge(
    df1,
    df2,
    on="customer_id"
)
```

If column names are different:

```
pd.merge(
    customers,
    orders,
    left_on="id",
    right_on="customerId"
)
```

Mental model:

```
customers.id
      ↕
orders.customerId
```

---

# 17. `how=` in `merge()`

### INNER

```
how="inner"
```

Only matching rows.

```
LEFT      RIGHT
  1
  2  ←→    2
  3  ←→    3
```

### LEFT

```
how="left"
```

Keep everything from the left DataFrame.

```
LEFT      RIGHT
  1        NaN
  2  ←→     2
  3  ←→     3
```

### RIGHT

```
how="right"
```

Keep everything from the right DataFrame.

### OUTER

```
how="outer"
```

Keep everything from both.

### Memorize:

```
INNER → matches
LEFT  → keep left
RIGHT → keep right
OUTER → keep both
```

---

# 18. `join()`

`.join()` is more **index-oriented**.

```
df1.join(df2)
```

Usually:

```
df1.index ↔ df2.index
```

Default:

```
how="left"
```

You can also:

```
df1.join(df2, how="inner")
```

or:

```
df1.join(df2, how="outer")
```

### `join(on=...)`

You can join a column from the left DataFrame to the **index** of the right DataFrame:

```
df1.join(
    df2,
    on="customer_id"
)
```

Mental model:

```
merge()
→ primarily think KEY COLUMNS

join()
→ primarily think INDEX
```

For your current learning:

> **Prioritize `merge()` over `join()`.**

---

# 19. `concat()`

`concat()` is different from `merge()`.

Think:

> **Stack things together.**

### Stack rows

```
pd.concat([jan, feb, mar])
```

Conceptually:

```
January
January
January
   ↓
February
February
   ↓
March
March
```

### Stack columns

```
pd.concat(
    [df1, df2],
    axis=1
)
```

Think:

```
axis=0 → rows
axis=1 → columns
```

---

# 20. The Operation-Ordering Principle

This is the **new lesson we just discovered**.

Don't think:

> "What Pandas function do I know next?"

Think:

> **"What data can I eliminate before doing expensive work?"**

A good default pipeline:

```
RAW DATA
   ↓
FILTER unwanted rows
   ↓
REMOVE unnecessary columns
   ↓
CLEAN / TRANSFORM
   ↓
MERGE if needed
   ↓
GROUP / AGGREGATE
   ↓
DROP DUPLICATES if appropriate
   ↓
SORT
   ↓
RENAME / FINAL FORMATTING
   ↓
RESULT
```

But this is a **guideline, not a law**.

The actual order depends on what information you need at each step.

---

# 21. Reduce → Compute → Arrange → Format

This is the mental model I'd especially like you to remember.

### ① Reduce

Get rid of things you don't need.

```
filter
drop_duplicates
select columns
```

### ② Compute

Do the actual analysis.

```
groupby
agg
transform
merge
calculations
```

### ③ Arrange

Put the result in the desired order.

```
sort_values
```

### ④ Format

Make the output look the way the user/problem expects.

```
rename
reset_index
column selection
```

So:

```
REDUCE
  ↓
COMPUTE
  ↓
ARRANGE
  ↓
FORMAT
```

This is **not an absolute rule**, but it's an excellent default.

---

# 22. Your LeetCode Lessons So Far

## Big Countries

You learned:

```
df[["name", "population", "area"]]
```

→ select multiple columns.

And:

```
(df["area"] >= 3000000) |
(df["population"] >= 25000000)
```

→ Boolean OR.

Important:

```
>   greater than
>=  greater than or equal
```

Tiny differences matter!

---

# 23. Find Products

You learned:

```
(df["low_fats"] == "Y") &
(df["recyclable"] == "Y")
```

→ Boolean AND.

Remember:

```
& → AND
| → OR
~ → NOT
```

And **wrap individual conditions in parentheses**.

---

# 24. Customers Who Never Order

You learned:

```
pd.merge(
    customers,
    orders,
    left_on="id",
    right_on="customerId",
    how="left"
)
```

Then:

```
df[df["customerId"].isnull()]
```

This is a classic pattern:

```
LEFT JOIN
    ↓
unmatched rows become NaN
    ↓
filter isnull()
```

This is a **very useful real-world technique**.

---

# 25. Article Views I

You learned:

```
views["author_id"] == views["viewer_id"]
```

Then:

```
.drop_duplicates()
.sort_values(...)
```

And the operation-order lesson:

```
❌ sort → drop duplicates

✅ drop duplicates → sort
```

when your goal is to sort the final unique results.

---

# 26. Common Errors You've Already Encountered

### Error 1

```
DataFrame.sort_values() missing 1 required positional argument: 'by'
```

Because:

```
df.sort_values(ascending=False)
```

doesn't tell Pandas which column.

Use:

```
df.sort_values(
    by="column",
    ascending=False
)
```

---

### Error 2

```
You need to return a Pandas DataFrame instead of Series
```

Because:

```
df["name"]
```

returns a Series.

Whereas:

```
df[["name"]]
```

returns a DataFrame.

---

# 27. Your "Pandas LEGO" Rule 😂

Before adding another operation, ask:

### **What shape is my data right now?**

Is it:

```
DataFrame?
Series?
Many rows?
Few rows?
Many columns?
One column?
```

Then ask:

### **What do I want the next operation to accomplish?**

For example:

```
"I need to eliminate irrelevant rows."
→ filter

"I need only these columns."
→ column selection

"I need to combine tables."
→ merge

"I need one result per category."
→ groupby + agg

"I need the group result attached to every row."
→ transform

"I need unique records."
→ drop_duplicates

"I need highest → lowest."
→ sort_values

"I need missing records."
→ isnull()

"I need to change the output name."
→ rename
```

---

# 🧠 The Cheat-Sheet You Should Actually Memorize

If you don't want to memorize the entire note, memorize **this**:

```
PANDAS CORE

DataFrame
→ df

Series
→ df["column"]

Multiple columns
→ df[["col1", "col2"]]

Filter
→ df[df["column"] > value]

AND
→ &

OR
→ |

NOT
→ ~

loc
→ df.loc[rows, columns]

Missing
→ isna() / isnull()

Duplicates
→ drop_duplicates()

Sort
→ sort_values(by="column")

Rename
→ rename(columns={...})

Group
→ groupby()

Aggregate
→ agg() / sum() / mean() / count()

Same group result for every row
→ transform()

Combine tables
→ pd.merge()

Match different column names
→ left_on= / right_on=

Join types
→ inner / left / right / outer

Index-based joining
→ join()

Stack tables
→ concat()

Pipeline principle
→ REDUCE → COMPUTE → ARRANGE → FORMAT
```