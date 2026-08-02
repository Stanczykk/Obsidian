# Report Connections (One Slicer, Multiple Pivot Tables)

> **Goal:** Control multiple Pivot Tables (and Pivot Charts) using a single slicer.

---

# Mental Model

Think of the slicer as a **remote control**.

Instead of controlling one TV...

It controls multiple TVs at the same time.

```text
           Week Slicer
                │
      ┌─────────┼─────────┐
      │         │         │
      ▼         ▼         ▼
 Pivot 1    Pivot 2   Pivot Chart
```

One click updates every connected report. [[3](https://www.wiseowl.co.uk/power-pivot/tips/filters-slicers/slicer-multiple-pivots/)][[1](https://trumpexcel.com/connect-slicer-to-multiple-pivot-tables/)]

---

# Why Use It?

Instead of changing filters one Pivot Table at a time...

Change one slicer.

Everything updates automatically.

Perfect for

- Dashboards
- Finance Reports
- Sales Reports
- Personal Finance Trackers

---

# How to Connect

1. Click the slicer.
2. Right-click → **Report Connections** (or **PivotTable Connections**).
3. Check the Pivot Tables you want to control.
4. Click **OK**. [[3](https://www.wiseowl.co.uk/power-pivot/tips/filters-slicers/slicer-multiple-pivots/)][[1](https://trumpexcel.com/connect-slicer-to-multiple-pivot-tables/)]

---

# Requirements

✔ Pivot Tables should share the same data source (or Pivot Cache/Data Model). Otherwise they cannot be connected. [[6](https://excelsamurai.com/use-one-slicer-for-multiple-pivot-tables-from-different-data-sources/)][[2](https://www.reddit.com/r/excel/comments/n78f7h/is_it_possible_to_connect_a_slicer_to_multiple/)]

---

# Real Example

Week Slicer

↓

Updates

- Sales by City
- Sales by Category
- Top Products
- Sales Trend Chart

All with one click.

---

# Best Practices

✔ Use one slicer per business filter (Week, City, Category).

✔ Connect it to every related Pivot Table.

✔ Place slicers once at the top or side of the dashboard.

✔ Avoid duplicate slicers for the same field.

---

# Remember

> **One Slicer → Many Pivot Tables**

Report Connections make dashboards interactive, consistent, and much easier for users.