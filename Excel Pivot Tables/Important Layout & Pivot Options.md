# 📊 Excel Dashboard — Important Layout & Pivot Options

> **Goal:** Keep Pivot Tables, Pivot Charts, and Slicers stable, clean, and professional when the report is filtered or refreshed.

---

# 1. Chart/Object → Don't Move or Size with Cells ⭐⭐⭐⭐⭐

### What it does

Prevents the chart from moving or resizing when the cells underneath it are changed.

### Why use it?

Dashboard charts should behave like **fixed objects**, not like normal cell contents.

```text
Without:
Resize columns
      ↓
Chart may move / resize ❌

With:
Resize columns
      ↓
Chart stays in position ✅
```

### Use for:

- Pivot Charts
- Dashboard charts
- Shapes
- KPI cards
- Logos / images

> **Dashboard rule:** Fixed visual objects → **Don't Move or Size with Cells**

---

# 2. PivotTable → Autofit Column Widths on Update ⭐⭐⭐⭐⭐

### What it does

Controls whether Excel automatically changes Pivot Table column widths when the Pivot Table updates.

### For dashboards:

Usually **turn this OFF**.

Otherwise:

```text
Slicer changes
     ↓
Pivot updates
     ↓
Column width changes
     ↓
Dashboard layout gets pushed around ❌
```

With it OFF:

```text
Slicer changes
     ↓
Pivot updates
     ↓
Column width stays consistent ✅
```

> **Dashboard rule:** Keep Pivot Table dimensions stable → **Turn OFF Autofit Column Widths on Update**

---

# 3. PivotTable → Preserve Cell Formatting on Update ⭐⭐⭐⭐☆

Keeps your formatting when the Pivot Table refreshes.

Useful when you have:

- Number formats
- Borders
- Fonts
- Alignment
- Custom formatting

> **Tip:** Generally keep this **ON** for formatted reports.

---

# 4. PivotTable → Defer Layout Update ⭐⭐⭐☆☆

You encountered this earlier.

When **ON**, Excel waits until you click **Update** before applying changes to the Pivot Table layout.

Useful when you are moving several fields around.

```text
Move fields
Move fields
Move fields
      ↓
     Update
      ↓
Pivot recalculates once
```

### Best for:

Building complicated Pivot Tables.

### Not particularly important for:

Finished dashboards.

> **Think:** "Let me finish arranging the Pivot before Excel recalculates it."

---

# 5. PivotChart → Hide Field Buttons ⭐⭐⭐⭐⭐

Pivot Charts can display buttons such as:

```text
[City ▼]   [Sum of Sales ▼]
```

These are useful while building the Pivot Chart.

But on a finished dashboard they usually create visual clutter.

### Professional approach

During development:

> **Keep Field Buttons ON**

Finished dashboard:

> **Hide Field Buttons**

This gives the user a cleaner chart.

---

# 6. Worksheet → Hide Gridlines ⭐⭐⭐⭐☆

Gridlines are useful when working with Excel.

For a finished dashboard, they can make the sheet look like a spreadsheet instead of a report.

### Development

```text
Gridlines → ON
```

### Finished dashboard

```text
Gridlines → OFF
```

> **Think:** Spreadsheet = gridlines useful.  
> Dashboard = cleaner without them.

---

# 7. Slicers → Report Connections ⭐⭐⭐⭐⭐

You already learned this one.

One slicer can control multiple Pivot Tables/Pivot Charts.

```text
             City Slicer
                 │
       ┌─────────┼─────────┐
       ↓         ↓         ↓
   Pivot 1    Pivot 2    Chart
```

> **Dashboard rule:** Connect related Pivot Tables to the same slicer.

---

# 8. Slicers → Button Layout ⭐⭐⭐⭐☆

Slicers can be formatted so the buttons fit naturally into the dashboard.

For example:

```text
City

[Bangalore] [Chennai]
[Delhi]     [Mumbai]
[Pune]
```

Instead of one long vertical list.

Adjust:

- Number of columns
- Button height
- Button width

> **Goal:** Make frequently used filters easy to click.

---

# 9. PivotTable → Refresh Data ⭐⭐⭐⭐⭐

A dashboard is only useful if the underlying data is current.

Remember:

```text
New Data
   ↓
Refresh
   ↓
Pivot Table updates
   ↓
Pivot Chart updates
   ↓
Dashboard updates
```

For recurring reports, **refreshing the data should be part of the workflow**.

---

# 🧠 Dashboard Settings Cheat Sheet

| Option | Dashboard Recommendation | Why |
|---|---|---|
| Don't Move or Size with Cells | **ON** | Keep charts fixed |
| Autofit Column Widths on Update | **OFF** | Prevent layout changes |
| Preserve Cell Formatting on Update | **ON** | Keep formatting |
| Defer Layout Update | Optional | Useful while building |
| PivotChart Field Buttons | **OFF** when finished | Reduce clutter |
| Gridlines | **OFF** when finished | Cleaner appearance |
| Report Connections | **ON/use when needed** | One slicer → multiple reports |
| Slicer Button Layout | Customize | Easier interaction |
| Refresh Data | **Essential** | Keep report current |

---

# ⭐ The Professional Dashboard Principle

The settings are all working toward one goal:

> **Filtering or refreshing the report should change the DATA, not destroy the LAYOUT.**

```text
                USER
                 │
                 ▼
             SLICER
                 │
                 ▼
           PIVOT TABLE
                 │
                 ▼
           PIVOT CHART
                 │
                 ▼
             DASHBOARD

       ┌─────────────────────┐
       │ Layout stays stable │
       │ Charts stay stable  │
       │ Formatting stays    │
       └─────────────────────┘
```

### Remember these 3 first ⭐

**1. Don't Move or Size with Cells**  
→ Keep dashboard objects fixed.

**2. Turn OFF Autofit Column Widths on Update**  
→ Keep Pivot Table layout stable.

**3. Hide unnecessary PivotChart Field Buttons**  
→ Keep the finished dashboard clean.

> **Good dashboard = Dynamic data + Stable layout + Clear visualization**