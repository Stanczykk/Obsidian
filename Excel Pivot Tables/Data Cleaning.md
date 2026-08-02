# 🧹 Data Cleaning Checklist for a Junior Data Analyst

## 1. Check for Blank Values ⭐⭐⭐⭐⭐

**Problem**

- Missing City
- Missing Price
- Missing Customer Name

**How to Find**

- Filter → `(Blanks)`
- Go To Special → Blanks (`F5` → Special)

**Action**

- Delete row? ❌ Not immediately
- Fill value? ✅ If appropriate
- Leave blank? ✅ If missing is valid
- Escalate? ✅ If critical data is missing

---

## 2. Check for Duplicate Records ⭐⭐⭐⭐⭐

**Problem**

```
Transaction 105
Transaction 105
```

**How to Find**

- Data → Remove Duplicates
- Conditional Formatting → Duplicate Values

**Action**

- Remove only if they're true duplicates.
- Verify first.

---

## 3. Remove Extra Spaces ⭐⭐⭐⭐⭐

**Problem**

```
Burger
 Burger
Burger
Burger 
```

Pivot Table sees them as different values.

**Solution**

```
=TRIM(A2)
```

---

## 4. Standardize Text ⭐⭐⭐⭐☆

**Problem**

```
burger
BURGER
Burger
BuRgEr
```

**Solution**

```
=UPPER()
=LOWER()
=PROPER()
```

---

## 5. Check Data Types ⭐⭐⭐⭐⭐

**Problem**

```
100
250
"300"
```

Last one is text.

**How to Check**

```
ISNUMBER()
ISTEXT()
```

---

## 6. Validate Dates ⭐⭐⭐⭐⭐

**Problem**

```
01/02/24
```

Is it January 2?

Or February 1?

**Check**

- Is it recognized as a date?
- Is the format consistent?

---

## 7. Check Numeric Columns ⭐⭐⭐⭐⭐

Look for impossible values.

Example

```
Units = -5

Price = -200

Age = 250
```

Usually indicates bad data.

---

## 8. Standardize Categories ⭐⭐⭐⭐⭐

Problem

```
Drink
Drinks
DRINKS
drink
```

Should become

```
Drinks
```

---

## 9. Check Outliers ⭐⭐⭐⭐☆

Example

```
Burger

120
130
9999
125
```

Ask

> Is 9999 realistic?

Sort Largest to Smallest.

---

## 10. Convert to Excel Table ⭐⭐⭐⭐⭐

Shortcut

```
Ctrl + T
```

Benefits

- Expands automatically
- Better formulas
- Better Pivot Tables
- Easier filtering

---

# Before Every Analysis

This becomes your routine.

```
☐ Understand the data

☐ Convert to Table

☐ Check blanks

☐ Check duplicates

☐ Remove spaces

☐ Standardize text

☐ Validate data types

☐ Validate dates

☐ Check impossible values

☐ Check outliers

☐ Standardize categories
```

---

# Excel Tools Every Junior Analyst Should Know

|Tool|Purpose|
|---|---|
|Filter|Find blanks, unusual values|
|Sort|Find outliers and inconsistencies|
|Remove Duplicates|Remove duplicate records|
|Conditional Formatting|Highlight duplicates, blanks, outliers|
|TRIM|Remove extra spaces|
|PROPER / UPPER / LOWER|Standardize text|
|Find & Replace (`Ctrl + H`)|Bulk corrections|
|Text to Columns|Split combined data|
|Flash Fill (`Ctrl + E`)|Extract or reformat text|
|Excel Tables (`Ctrl + T`)|Organize data|
|Pivot Tables|Validate categories and summarize data|

---

# Shortcuts Worth Memorizing

|Shortcut|Function|
|---|---|
|Ctrl + T|Convert to Table|
|Ctrl + Shift + L|Toggle Filters|
|Ctrl + H|Replace|
|Ctrl + F|Find|
|Ctrl + E|Flash Fill|
|Ctrl + Arrow|Jump to edge of data|
|Ctrl + Shift + Arrow|Select data region|
|F5 → Special → Blanks|Select blank cells|
|Alt + A + M|Remove Duplicates|
|Ctrl + Z|Undo|