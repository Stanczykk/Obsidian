# 1. Summarize Values By
> Questions it answers:
> "How should Excel summarize my Data?"

This is the most fundamental setting in every Pivot Table.
Instead of changing the data, you change how it is calculated


***Common Options***
### SUM

Question:

> How much?

Example

```
Sales

100
200
300

↓

600
```

Most common use:

- Revenue
- Profit
- Expenses
- Quantity
### COUNT

Question:

> How many?

Example

```
Orders

A
B
C

↓

3 Orders
```

Use when counting records.

### AVERAGE

Question:

> What's the typical value?

Example

```
Sales

100
150
250

↓

166.67
```

---

### MAX

Question:

> What's the highest value?

---

### MIN

Question:

> What's the lowest value?

---

## Remember

> **Summarize Values By changes HOW Excel calculates a field.**

---
# 2. Show Values As

> **Question it answers:**
> 
> **"How do I want to compare these numbers?"**

Unlike "Summarize Values By," this doesn't change the underlying calculation.

Instead, it changes how the results are displayed.

---

## Common Options

### % of Grand Total ⭐⭐⭐⭐⭐

Question

> What percentage of the entire business does this represent?

Example

```
City

Manila 40%

Cebu 35%

Davao 25%
```

Perfect for dashboards.

---

### % of Row Total

Question

> What percentage does each value contribute within this row?

Before

|City|Food|Drinks|
|---|---|---|
|Manila|300|700|
|Cebu|600|400|

↓

% of Row Total

|City|Food|Drinks|
|---|---|---|
|Manila|30%|70%|
|Cebu|60%|40%|

Each **row** totals **100%**.

---

### % of Column Total

Question

> What percentage does each value contribute within this column?

Before

|City|Food|Drinks|
|---|---|---|
|Manila|300|700|
|Cebu|600|400|

↓

% of Column Total

|City|Food|Drinks|
|---|---|---|
|Manila|33.3%|63.6%|
|Cebu|66.7%|36.4%|

Each **column** totals **100%**.

---

### % Difference From ⭐⭐⭐⭐☆

Question

> How much did something increase or decrease?

Example

```
January

$1,000

February

$1,250

↓

+25%
```

Great for month-over-month analysis.

---

### Running Total ⭐⭐⭐⭐⭐

Question

> How is my total accumulating over time?

Example

```
January

500

February

1100

March

1600
```

Useful for

- Sales Growth
- Budget Tracking
- Savings
- Inventory

---

### Rank Largest to Smallest ⭐⭐⭐⭐☆

Question

> Who is #1?

Example

```
Store A

Rank 1

Store B

Rank 2
```

Useful for Top Performers.

---

## Remember

> **Show Values As changes HOW results are displayed—not how they are calculated.**

# 3. Value Filters ⭐⭐⭐⭐☆

> **Question it answers:**
> 
> **"Which values should I focus on?"**

Instead of showing everything...

Show only what's important.

---

## Top 10

Question

> Who are my best performers?

Examples

Top

- 10 Products
- 5 Cities
- 20 Employees

---

## Bottom 10

Question

> Which areas need improvement?

Examples

Bottom

- Stores
- Products
- Salespeople

---

## Greater Than

Show only

```
Sales > $10,000
```

---

## Less Than

Show only

```
Profit < $500
```

---

## Above Average

Find exceptional performers.

---

## Below Average

Find weak performers.

---

## Why Analysts Love Value Filters

Instead of reading

500 products...

You immediately focus on

Top 10.