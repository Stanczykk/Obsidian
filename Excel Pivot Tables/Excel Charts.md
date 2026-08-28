# 📊 Excel Charts — Choosing the Right Chart

> **Core Rule:** Choose the chart based on **what you want the viewer to understand**.

---

## 1. Bar / Column Chart ⭐⭐⭐⭐⭐

### Use when:
> **"I want to compare categories."**

Examples:
- Sales by City
- Sales by Product
- Sales by Store
- Units sold by Category

```text
City        Sales
Pune        ███████████
Mumbai      █████████
Chennai     ████████
Delhi       ███████
```

### Bar vs Column

**Column** → Good for a small number of categories.

**Bar** → Better when you have many categories or long names.

> **Think: Comparison**

---

# 2. Line Chart ⭐⭐⭐⭐⭐

### Use when:
> **"I want to see a trend or change over time."**

Examples:
- Sales by Month
- Revenue by Week
- Expenses over time
- Daily transactions

```text
Sales
  │       ╱───╮
  │    ╱─╯    ╰──
  │ ╱─╯
  └────────────────
    Jan Feb Mar Apr
```

> **Think: Trend**

---

# 3. Pie / Donut Chart ⭐⭐⭐☆☆

### Use when:
> **"I want to show how a total is divided."**

Examples:
- % of sales by category
- % of expenses by type
- Market share

Example:

```text
Snacks      45%
Drinks      30%
Other       25%
```

### Best Practice

Use when there are **only a few categories**.

Avoid pie charts when there are many categories because comparing similar-sized slices becomes difficult.

> **Think: Part of a Whole**

---

# 4. Scatter Plot ⭐⭐⭐⭐☆

### Use when:
> **"I want to see whether two numerical variables are related."**

Examples:

- Price vs Units Sold
- Advertising Cost vs Sales
- Experience vs Productivity

```text
Units
 │       •
 │    •
 │  •    •
 │ •
 └──────────── Price
```

> **Think: Relationship**

---

# 5. Area Chart ⭐⭐☆☆☆

### Use when:
> **"I want to emphasize the magnitude of change over time."**

Similar to a line chart but emphasizes the amount/volume.

Useful for:
- Revenue trends
- Total volume
- Cumulative values

Usually, a line chart is easier to read.

> **Think: Trend + Magnitude**

---

# 6. Stacked Column / Bar ⭐⭐⭐⭐☆

### Use when:
> **"I want to compare totals AND see their composition."**

Example:

```text
City       Drinks + Snacks + Other
Pune       █████████████████
Mumbai     ███████████████
Delhi      ████████████
```

Useful for:
- Sales by city broken down by category
- Expenses by department
- Revenue composition over time

> **Think: Comparison + Composition**

---

# 🧠 Quick Decision Guide

| Question | Chart |
|---|---|
| Which is bigger? | **Bar / Column** ⭐ |
| How is it changing over time? | **Line** ⭐ |
| What makes up the total? | **Pie / Donut** |
| Are two variables related? | **Scatter** |
| How much is changing over time? | **Area** |
| Compare totals + their components? | **Stacked Bar/Column** |

---

# Analyst Mindset

Before creating a chart, ask:

### 1. What question am I answering?

### 2. What comparison or pattern should the viewer notice?

### 3. Which chart makes that answer easiest to see?

> **Do not choose a chart because it looks interesting.**
>
> **Choose it because it communicates the insight clearly.**

---

# ⭐ Most Important Charts to Master

For everyday Excel/data analyst work:

1. **Bar / Column** → Comparison
2. **Line** → Trends
3. **Stacked Bar / Column** → Comparison + Composition
4. **Scatter** → Relationships
5. **Pie / Donut** → Simple Part-to-Whole

> **Chart selection = Question → Insight → Visualization**