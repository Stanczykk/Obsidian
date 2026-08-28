# Power Query — Introduction

## What is Power Query?

**Power Query** is Excel’s tool for **importing, cleaning, transforming, and combining data** before it is analyzed.

Think of it as the **data preparation stage** of the Excel workflow.

> **Power Query prepares the data. PivotTables analyze the data.**

---

## The Big Picture

Raw Data
   ↓
Power Query
   ↓
Clean & Transform
   ↓
Data Model
   ↓
PivotTable / PivotChart
   ↓
Analysis & Insights
### The distinction

|Tool|Main Purpose|
|---|---|
|**Power Query**|Import, clean, transform, and combine data|
|**PivotTable**|Summarize and analyze data|
|**PivotChart**|Visualize summarized data|
|**Power Pivot**|Build advanced data models and relationships|
|**DAX**|Create advanced calculations in the data model|

---

# Power Query vs PivotTable

### PivotTable asks:

> **"What can I learn from this data?"**

### Power Query asks:

> **"How do I get this data ready so I can analyze it?"**

This is one of the most important concepts to remember.

---

# What Can Power Query Do?

## 1. Remove Unnecessary Data
Power Query can remove:

- Unwanted columns
- Unwanted rows
- Blank rows
- Duplicate records

---

## 2. Clean Data

Power Query can standardize inconsistent data.

For example:

```
"   Coke 1.5L   "
"coke 1.5 l"
"COKE 1.5L"
```

Can be transformed into:

```
"Coke 1.5L"
"Coke 1.5L"
"Coke 1.5L"
```

This prevents the same product from being treated as three different products in a PivotTable.

---

## 3. Change Data Types

Power Query allows you to specify whether a column contains:

- Text
- Whole Number
- Decimal Number
- Date
- Time
- Date/Time
- True/False

> **Correct data types are important because Excel needs to understand what your data represents.**

---

## 4. Create New Columns

Power Query can create calculated columns.

Example:

Sales = Price × Quantity

|Product|Price|Quantity|Sales|
|---|---|---|---|
|Coke|₱75|4|₱300|

---

## 5. Combine Data

One of Power Query’s major strengths is combining multiple datasets.

For example:

```
January.xlsx
February.xlsx
March.xlsx
April.xlsx
       ↓
  Power Query
       ↓
One Clean Dataset
```

Instead of manually copying and pasting each month's data, Power Query can combine them.

---

## 6. Connect to Different Data Sources

Power Query can work with many types of sources, including:

- Excel workbooks
- CSV files
- Text files
- Folders
- Databases
- Web data
- Other data sources

This makes Power Query useful beyond simple Excel worksheets.

---

# The Most Important Concept: Refresh

Power Query can turn your data-cleaning process into a **repeatable process**.

Imagine you receive a new sales file every week.

### Without Power Query

```
Import
  ↓
Clean
  ↓
Copy
  ↓
Paste
  ↓
Fix
  ↓
Update PivotTable
```

You repeat the process manually.

### With Power Query

```
New Raw Data
     ↓
   Refresh
     ↓
Power Query repeats

the transformation steps
     ↓
Clean Dataset
     ↓
PivotTable
```

> **Power Query records the transformation steps so they can be repeated when the data changes.**

This is one of the biggest reasons Power Query is powerful.

---

# Power Query as a Data Pipeline

A useful mental model is:

```
Raw Data
    ↓
Import
    ↓
Remove unnecessary data
    ↓
Clean values
    ↓
Change data types
    ↓
Create/transform columns
    ↓
Combine datasets
    ↓
Clean Dataset
    ↓
PivotTable / Data Model
```

This is essentially a **data preparation pipeline**.

---

# Power Query and M

Power Query has its own programming language called **M**.

When you perform transformations through the Power Query interface, Power Query generates M code behind the scenes.

For example, you may eventually encounter code such as:

Table.TransformColumns(...)

### For now:

> **Power Query = Visual Data Transformation**

Later:

> **M = The language behind Power Query**

You do **not** need to learn M immediately.

Start by understanding the transformations and the logic behind them.

---

# Where Power Query Fits in My Excel Journey

```
Excel Fundamentals
       ↓
Data Cleaning
       ↓
XLOOKUP / Combining Data
       ↓
PivotTables
       ↓
Power Query ← CURRENT STAGE
       ↓
Power Pivot
       ↓
DAX
       ↓
Advanced Data Analysis
       ↓
Dashboards & Data Visualization
```

---

# The Bigger Excel Data Workflow

Eventually, the workflow can look like:

```
                RAW DATA
                    │
                    ▼
              POWER QUERY
         Import + Clean + Transform
                    │
                    ▼
               DATA MODEL
                    │
               POWER PIVOT
                    │
          ┌─────────┴─────────┐
          ▼                   ▼
      PIVOTTABLE          PIVOTCHART
          │                   │
          └─────────┬─────────┘
                    ▼
                 INSIGHTS
```
---

# Data Analyst Mindset

When looking at a dataset, start asking:

1. **Where did this data come from?**
2. **What is wrong or inconsistent with it?**
3. **What transformations are necessary?**
4. **Can I make those transformations repeatable?**
5. **What structure should the final dataset have for analysis?**

---

# Key Takeaway

> **Power Query prepares the data.**
> 
> **PivotTables summarize the data.**
> 
> **Power Pivot models the data.**
> 
> **DAX calculates insights from the data model.**
> 
> **Charts and dashboards communicate the insights.**

Power Query is therefore the bridge between **messy real-world data** and **reliable analysis**.