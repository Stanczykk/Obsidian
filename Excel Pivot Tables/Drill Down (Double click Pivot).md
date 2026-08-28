# Pivot Table - Drill Down / Show Details

> **Goal:** Investigate the individual records behind a summarized Pivot Table value.

## What is Drill Down?

**Double-click a value inside a Pivot Table** → Excel creates a new worksheet containing the **underlying records** that make up that value.

Example:

```text
Pivot Table

Bangalore → ₱319,916

        ↓ Double-click

Underlying Transactions

Date | City | Product | Units | Sales
...
```

The Pivot Table tells you:

> **"What happened?"**

Drill Down tells you:

> **"Which records caused it?"**

---

## How It Can Be Used

### 1. Investigate unusual numbers ⭐⭐⭐⭐⭐

> "Why is Bangalore's sales unusually high?"

Double-click the total → inspect the transactions.

### 2. Investigate data errors ⭐⭐⭐⭐⭐

> "Why does this total look wrong?"

Drill down → look for incorrect quantities, prices, dates, etc.

### 3. Answer follow-up questions ⭐⭐⭐⭐☆

> "Show me the transactions behind this total."

Drill down gives you the underlying records.

### 4. Extract a specific subset ⭐⭐⭐⭐☆

Filter the Pivot Table first:

```text
City → Mumbai
Week → 3
```

Then double-click the total.

Excel extracts the records matching that Pivot Table selection.

---

# Mental Model

```text
Source Data
     ↓
Pivot Table
     ↓
Double-click a value
     ↓
Underlying Records
```

**Pivot Table** → Summarize

**Drill Down** → Investigate

---

# Important Limitation

The extracted worksheet is a **snapshot of the underlying records**.

It is mainly an investigation tool, not a replacement for Power Query.

If the source data changes, the extracted worksheet should not be treated as automatically synchronized with the source.

---

# Analyst Mindset

When you see a number that makes you ask:

> **"Why?"**

Use **Drill Down**.

---

# Where It Fits

| Tool | Main Purpose |
|---|---|
| Pivot Table | Summarize |
| Drill Down | Investigate |
| Power Query | Clean & Transform |
| Power Pivot | Model & Analyze |

> **Drill Down = "Show me the records behind this number."**