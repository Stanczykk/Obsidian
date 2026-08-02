# Pivot Tables - Grouping

> **Goal:** Combine detailed data into meaningful categories to make analysis easier.

![[Pasted image 20260726150002.png]]

---

# Mental Model

Imagine looking at a crowd of 10,000 people.
Instead of seeing every individual person...
You group them into:

- Children
- Teenagers
- Adults
- Seniors

You lose some detail...

But you gain a much clearer picture.

**Pivot Table Grouping does the same thing.**

---

# What Problem Does Grouping Solve?

Raw data is usually too detailed.

Example

```text
07:05
07:18
07:42
08:01
08:15
08:30
```

This is difficult to analyze.

Instead, group them into

```text
Morning
Afternoon
Evening
```

Now patterns become obvious.

---

# Think Before You Group

Ask yourself

> "Is this data too detailed to answer my business question?"

If YES

↓

Group it.

---

# Common Things to Group

## Dates

Before

```text
01/01/2025
02/01/2025
03/01/2025
```

After

```text
January
February
March
```

or

```text
Quarter 1
Quarter 2
```

---

## Numbers

Before

```text
18
21
24
27
30
```

After

```text
18–25
26–35
36–45
```

Useful for

- Age
- Salary
- Price
- Sales

---

## Time

Before

```text
08:00
09:00
10:00
11:00
```

After

```text
Morning
Afternoon
Evening
```

Useful for

- Staff Scheduling
- Customer Traffic
- Sales Trends

---

## Categories

Example

Before

```text
Burger
Pizza
Fries
Coke
Coffee
Tea
```

After

```text
Food

Drinks
```

---

# Real Business Uses

Restaurant

Question

> Which shift generates the most revenue?

Group

```text
Morning

Afternoon

Evening
```

---

Retail

Question

> Which quarter sells the most?

Group

```text
Months

↓

Quarters
```

---

HR

Question

> Which age group has the highest employee turnover?

Group

```text
18–25

26–35

36–45
```

---

# How to Create a Group

1. Select the items in the Pivot Table.
2. Right-click.
3. Click **Group**.
4. Rename the group if needed.

---

# My Shift Example

Hours

```text
08:00
09:00
10:00
11:00
```

↓

Group

```text
Morning
```

Hours

```text
12:00
13:00
14:00
16:00
```

↓

Group

```text
Afternoon
```
Hours
```text
17:00
18:00
19:00
20:00
```
↓
Group

```text
Evening
```

Now instead of comparing 24 different hours...
I compare only three shifts.
Much easier.

---

# Benefits

✅ Simplifies reports
✅ Makes trends easier to see
✅ Improves readability
✅ Better charts
✅ Easier for management to understand

---

# Best Practices

✔ Group only when it helps answer the business question.
✔ Don't remove important detail unnecessarily.
✔ Give groups meaningful names.

Examples

✅ Morning
✅ Afternoon
✅ Evening

Instead of

❌ Group1
❌ Group2
❌ Group3

---

# Common Mistakes

❌ Grouping just because you can.
❌ Making groups too broad.
❌ Creating overlapping groups.
❌ Forgetting to rename groups.

---

# Key Takeaways

- Grouping summarizes detailed data into meaningful categories.
- It is used to simplify analysis, not change the original data.
- Always ask:
  > "Will grouping make the business question easier to answer?"
- If yes, group it.

---

# Remember This

> **Grouping doesn't change the data.**
>
> **Grouping changes how people understand the data.**