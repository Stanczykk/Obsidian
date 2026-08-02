# Pivot Table Filters

> **Goal:** Display only the data needed to answer a business question.

Always ask:

> **"What data do I want to see?"**

---

# 1. Report Filter ⭐⭐⭐⭐⭐

**Question it answers**

> "What data should I include?"

Filters the **entire Pivot Table**.

Examples

- Week = 2
- City = Bangalore
- Category = Drinks

Think:

> **Filter the whole report.**

---

# 2. Label Filters ⭐⭐⭐⭐☆

**Question it answers**

> "Which names do I want?"

Filters based on **text**.

Most Common

- Equals
- Does Not Equal
- Begins With
- Contains ⭐⭐⭐⭐⭐

Example

```text
Contains "Roll"

↓

Chicken Roll
Egg Roll
Spring Roll
```

Think:

> **Filter by names.**

---

# 3. Value Filters ⭐⭐⭐⭐⭐

**Question it answers**

> "Which numbers matter?"

Filters based on calculated values.

Most Common

- Top 10 ⭐⭐⭐⭐⭐
- Bottom 10 ⭐⭐⭐⭐⭐
- Greater Than
- Less Than
- Above Average
- Below Average

Example

```text
Top 10 Products
```

Think:

> **Filter by numbers.**

---

# 4. Date Filters ⭐⭐⭐⭐☆

**Question it answers**

> "What date range do I want to analyze?"

Most Common

- Before
- After
- Between ⭐⭐⭐⭐⭐
- This Month
- Last Month
- This Year

Example

```text
01/05/2013

↓

30/06/2013
```

Think:

> **Manual date filtering.**

# 5. Timeline ⭐⭐⭐⭐⭐

**Question it answers**

> "Can I interactively browse my data over time?"

A Timeline is a **visual filter made specifically for dates**. It lets users filter by **Years, Quarters, Months, or Days** using a slider instead of menus. [[1](https://support.microsoft.com/en-us/excel/create-a-pivottable-timeline-to-filter-dates)]

Example

```text
Jan ─ Feb ─ Mar ─ Apr ─ May ─ Jun
                █████
```

Think:

> **Interactive date filtering.**

# Filter Cheat Sheet

| Filter | Think... | Best Used For |
|---------|----------|---------------|
| Report Filter | What data? | Entire report |
| Label Filter | Which names? | Text filtering |
| Value Filter | Which numbers? | Top/Bottom performers |
| Date Filter | Which dates? | Static reports |
| Timeline | Browse dates | Dashboards |

---

# Analyst Decision Guide

Manager says...

"Show only Week 2."

→ Report Filter

---

"Show products containing 'Roll'."

→ Label Filter

---

"Show the Top 10 products."

→ Value Filter

---

"Show sales from May to June."

→ Date Filter

---

"I want to interactively browse sales by Month."

→ Timeline

---

# Key Takeaways

- **Report Filter** → Filter the entire report.
- **Label Filter** → Filter by text.
- **Value Filter** → Filter by numbers.
- **Date Filter** → Manually filter dates.
- **Timeline** → Interactive date filter for dashboards.

> **Remember:**
> *Report = What data?*
> *Label = Which names?*
> *Value = Which numbers?*
> *Date = Which dates?*
> *Timeline = Interactive dates.*