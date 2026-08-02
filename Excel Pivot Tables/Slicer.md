# Pivot Table - Slicers

> **Goal:** Give users an easy and interactive way to filter Pivot Tables.

Think of a slicer as a **visual filter**.
Instead of opening filter drop-downs, users simply click buttons.
Perfect for dashboards and users who are not familiar with Excel.

---

# Mental Model

Question it answers:

> "What data do I want to see?"

Examples

- Week 1
- Bangalore
- Drinks

One click updates the entire Pivot Table (or multiple Pivot Tables if connected).

---

# Common Slicers

- Year
- Month
- Week
- City
- Category
- Department
- Store

Avoid using slicers for fields with hundreds or thousands of values (e.g., Item Code, Customer ID).

---

# Professional Dashboard Layout

Professionals usually place slicers:

✅ At the **top** of the dashboard
or
✅ Along the **left/right side**

Typical order:

```text
Week | City | Category | Store
```

Arrange from **general → specific**.

---

# Best Practices

✔ Use meaningful fields (City, Week, Category)
✔ Keep slicers the same size
✔ Align them neatly
✔ Use one color theme
✔ Connect one slicer to multiple Pivot Tables (Report Connections)
✔ Use multiple columns for slicers with many buttons (e.g., Weeks)

---

# Remember

- **Report Filter** = Traditional filter
- **Slicer** = Visual, user-friendly filter

They do the same job.

Slicers simply make dashboards interactive.

---

# Key Takeaways

- Slicers are designed for dashboards.
- They let non-Excel users filter reports easily.
- Use slicers on fields people naturally filter by.
- Keep the layout clean, aligned, and consistent.
- One slicer can control multiple Pivot Tables.

![[Pasted image 20260801153131.png]]![[Pasted image 20260801153333.png]]

A Pivot Chart is **directly connected** to its Pivot Table.

The flow looks like this:

```
Raw Data
    ↓
Pivot Table
    ↓
Pivot Chart
```

When you click a **Slicer**, Excel doesn't change the chart directly.

It changes the **Pivot Table**, and the Pivot Chart automatically redraws itself based on the updated Pivot Table. [[1](https://support.microsoft.com/en-us/excel/get-started/use-slicers-to-filter-data)][[3](https://rowzero.com/blog/slicers-and-pivot-tables)]

Example:

```
Raw Data
      ↓
Pivot Table (All Cities)
      ↓
Pivot Chart (All Cities)

Click "Bangalore" on the slicer

      ↓

Pivot Table (Bangalore only)
      ↓
Pivot Chart (Bangalore only)
```

This is why dashboards feel "alive." One slicer can control **multiple Pivot Tables and Pivot Charts** through **Report Connections**, allowing every chart to update simultaneously. [[1](https://support.microsoft.com/en-us/excel/get-started/use-slicers-to-filter-data)][[3](https://rowzero.com/blog/slicers-and-pivot-tables)]

### Key Takeaway

> **Slicer → Pivot Table → Pivot Chart**

The slicer never talks to the chart directly—it filters the Pivot Table, and the chart simply visualizes the Pivot Table's current state.