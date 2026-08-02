# XLOOKUP - Merging Tables

> **Goal:** Learn how to merge two related tables using a common key.

---

# Mental Model

Imagine two friends.

👤 Sales Department
"I know what was sold."
👤 Product Department
"I know the details about every product."
Neither knows everything.

**XLOOKUP is the messenger that connects them.**

```text
Sales Table                    Product Table

Item Code ───────────────► Item Code
                               │
                               ├── Price
                               ├── Profit Margin
                               ├── Category
                               └── Supplier
```

Instead of manually copying information, XLOOKUP finds the matching Item Code and brings back the information you need.

---

# The Business Problem

Most companies separate their data.

Example
Sales Table

| Sale Date | Item Code | Units |
|-----------|-----------|------:|
| 01/05/13 | 11012 | 7 |
| 01/05/13 | 11042 | 6 |

Product Table

| Item Code | Price | Profit Margin |
|-----------|------:|--------------:|
|11012|10|2|
|11042|15|3|

The Sales table doesn't know the Price.
The Product table doesn't know how many units were sold.
XLOOKUP bridges both tables.

---

# Before Using XLOOKUP

Ask yourself these questions.

## 1. What am I looking for?

Usually an ID.

Examples

- Item Code
- Employee ID
- Customer ID
- Invoice Number

Example

```text
11012
```

---

## 2. Where should I look?

Which column contains that ID?

Example

```text
Products[Item Code]
```

---

## 3. What information do I want to return?

Examples

- Price
- Profit Margin
- Category
- Employee Name

Example

```text
Products[Price]
```

---

# Formula Structure

```excel
=XLOOKUP(
    Lookup Value,
    Lookup Array,
    Return Array,
    [If Not Found]
)
```

---

# Read It Like English

```excel
=XLOOKUP(
    [@[Item Code]],
    Products[Item Code],
    Products[Price],
    "Item Not Found"
)
```

Translation

> Find this row's Item Code inside the Products table and return the matching Price. If nothing matches, display "Item Not Found."

---

# The Three Questions XLOOKUP Answers

*Question 1*
"What am I looking for?"
↓
Item Code

---

*Question 2*
"Where should I search?"
↓
Products[Item Code]

---

*Question 3*
"What do I want back?"
↓
Products[Price]

---

# Why Use IDs?

Never use names if an ID exists.

Bad

```text
Burger
```

Good

```text
11024
```

Reason
Names can repeat. IDs should be unique.

---

# Professional Workflow

```text
Receive Sales File

↓

Receive Product Master

↓

Merge Tables (XLOOKUP)

↓

Clean Data

↓

Pivot Table

↓

Dashboard

↓

Business Report
```

Notice:
XLOOKUP happens BEFORE Pivot Tables.

---

# Why Professionals Prefer XLOOKUP

✅ Easier to read
✅ No column index numbers
✅ Can search left or right
✅ Doesn't break when columns are inserted
✅ Built-in "Not Found" message
✅ Works perfectly with Excel Tables

---

# VLOOKUP vs XLOOKUP

| VLOOKUP | XLOOKUP |
|---------|----------|
| Uses column numbers | Uses column names |
| Can only look right | Can look left or right |
| Easier to break | More reliable |
| #N/A by default | Custom error messages |
| Older function | Modern replacement |

---

# Real World Uses

Finance
Employee ID → Salary

---
Inventory
Item Code → Current Stock

---
Sales
Item Code → Price

---
HR
Employee ID → Department

---
Logistics
Tracking Number → Shipment Status

---

# Best Practices

✔ Always convert data into Excel Tables (Ctrl + T)
✔ Rename tables

Example

```text
Sales

Products

Employees
```

instead of

```text
Table1

Table2
```

✔ Use IDs instead of names
✔ Always include the "Not Found" argument

```excel
=XLOOKUP(
    [@[Item Code]],
    Products[Item Code],
    Products[Price],
    "Item Not Found"
)
```

---

# Common Mistakes

❌ Looking up Item Name instead of Item Code

❌ Forgetting the "Not Found" argument

❌ Using normal ranges instead of Excel Tables

❌ Using XLOOKUP when there is no unique key

---

# Key Takeaways

- XLOOKUP connects related tables.
- It uses a unique key (usually an ID).
- It answers three questions:
  1. What am I looking for?
  2. Where should I look?
  3. What information do I want back?
- Think of XLOOKUP as a bridge between two tables.
- Merging tables is usually done before Pivot Tables and dashboards.

---

# Interview Question

**Why would you use XLOOKUP?**

Answer:

> I use XLOOKUP to merge related datasets using a common key. It is more flexible and readable than VLOOKUP because it doesn't rely on column index numbers, supports searching in both directions, includes built-in error handling, and works well with Excel Tables.