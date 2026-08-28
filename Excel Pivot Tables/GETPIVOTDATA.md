# Pivot Table - GETPIVOTDATA

> **Goal:** Retrieve a specific result from a Pivot Table and use it somewhere else in the workbook.

## What is GETPIVOTDATA?

**GETPIVOTDATA** extracts a specific value from a Pivot Table based on its **fields and items**.

When you type:

```excel
=
```

and click a value inside a Pivot Table, Excel can automatically create a `GETPIVOTDATA` formula.

Example:

```excel
=GETPIVOTDATA("Sales",$A$3,"City","Bangalore")
```

This essentially means:

> **"Give me the Sales value for Bangalore from this Pivot Table."**

---

# Why Not Just Use a Cell Reference?

Normal reference:

```excel
=C5
```

Means:

> "Give me whatever is currently in cell C5."

GETPIVOTDATA:

```excel
=GETPIVOTDATA("Sales",$A$3,"City","Bangalore")
```

Means:

> "Give me the Sales value for Bangalore."

### Key Difference

**Cell Reference** → References a location.

**GETPIVOTDATA** → References a Pivot Table result.

This makes GETPIVOTDATA more reliable when the Pivot Table layout changes.

---

# Professional Uses

## 1. KPI Cards ⭐⭐⭐⭐⭐

Use Pivot Tables as the **calculation/analysis layer** and GETPIVOTDATA to bring important results into a dashboard.

Example:

```text
┌────────────────────┐
│    TOTAL SALES     │
│     ₱950,516       │
└────────────────────┘
```

The KPI can pull its value from a Pivot Table.

---

## 2. Management Reports ⭐⭐⭐⭐⭐

Keep the Pivot Tables on a supporting sheet and display selected results on a clean report.

```text
Sales Summary

Total Sales       ₱950,516
Bangalore Sales   ₱319,916
Pune Sales        ₱325,400
Mumbai Sales      ₱305,200
```

The user sees the **report**, not the complicated analysis behind it.

---

## 3. Combining Pivot Results ⭐⭐⭐⭐☆

GETPIVOTDATA can retrieve multiple results that can then be used in other formulas.

Example:

```text
Total Sales = ₱950,516
Total Cost  = ₱600,000
```

Then:

```excel
=Sales-Cost
```

Result:

```text
Profit = ₱350,516
```

---

# Mental Model

```text
Pivot Table
     ↓
Analyze / Summarize
     ↓
GETPIVOTDATA
     ↓
Dashboard / Report
```

Think:

> **"Give me this specific result from my Pivot Table."**

---

# GETPIVOTDATA vs XLOOKUP

| Tool | Main Purpose |
|---|---|
| **XLOOKUP** | Find information in a table |
| **Pivot Table** | Summarize data |
| **GETPIVOTDATA** | Retrieve a result from a Pivot Table |

---

# Analyst Workflow

```text
Raw Data
   ↓
XLOOKUP / Data Cleaning
   ↓
Prepared Dataset
   ↓
Pivot Table
   ↓
GETPIVOTDATA
   ↓
Dashboard / Management Report
```

---

# Key Takeaways

- GETPIVOTDATA retrieves **specific results from Pivot Tables**.
- Excel can automatically create the formula when you click a Pivot Table value after typing `=`.
- It references the **meaning of the data**, rather than simply a cell location.
- Very useful for **KPI cards and dashboards**.
- Helps separate the **analysis layer** from the **presentation layer**.

> **GETPIVOTDATA = "Give me this specific result from my Pivot Table."**