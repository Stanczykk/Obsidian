# The 5-Step Thinking Process

Whenever you create a Pivot Table, ask yourself these questions **in order**.

```
1. What business question am I trying to answer?

2. What do I want to compare?

3. What number am I measuring?

4. Do I want another level of comparison?

5. Do I only want to look at part of the data?
```

# Question 1

## What business question am I trying to answer?

This is the MOST important question.

Examples

- Which city has the highest sales?
- Which employee sold the most?
- Which month earned the most revenue?
- Which product is least profitable?

Everything else depends on this.

If you don't know the question...

You won't know what belongs in the Pivot Table.

# Question 2

## What do I want to compare?

This determines the **Rows**. Ask:
> **"What should each row represent?"**

Examples

|Business Question|Rows|
|---|---|
|Sales by City|City|
|Sales by Store|Store|
|Sales by Employee|Employee|
|Sales by Month|Month|

#### Mental model:
Rows answer

> **"One row for every _____."**

Examples

*One row for every*
- City
- Store
- Product
- Employee
- Customer

# Question 3

## What number am I measuring?

This determines the **Values**.

Ask

> **"What am I calculating?"**

Examples

Sales

Profit

Units

Quantity

Expenses

Hours Worked

Then ask another question

> **"What calculation do I need?"**

Usually

- Sum
- Count
- Average
- Max
- Min

Example

Business question

> Which city made the most money?

Values

```
Sum of Sales
```

Different question

> Which city had the most orders?

Values

```
Count of Orders
```

Same data.

Different calculation.

# Question 4

## Do I want another level of comparison?

This determines the **Columns**.

Ask

> **"Do I want to split each row into smaller groups?"**

Without Columns

|City|Sales|
|---|---|
|Manila|12000|
|Cebu|9000|

With Category in Columns

|City|Drinks|Snacks|Daily Bites|
|---|---|---|---|
|Manila|4000|3000|5000|
|Cebu|2500|1500|5000|

Columns let you compare across another dimension.

# Question 5

## Do I only want part of the data?

This determines the **Filters**.

Ask

> **"Should I only analyze certain records?"**

Examples

Only Week 2

Only Store 101

Only Manila

Only Drinks

Instead of deleting data...

You filter it.

# Here's the Mental Model

Instead of memorizing the boxes...

Remember these questions.

|Pivot Area|Question|
|---|---|
|Rows|**What do I want to compare?**|
|Values|**What am I measuring?**|
|Columns|**How do I want to split the comparison?**|
|Filters|**Do I want to analyze only part of the data?**|
# The Analyst's Secret

You'll notice that **Rows** and **Columns** don't actually contain numbers.

They contain **descriptions** (also called **dimensions** or **categories**) such as City, Product, Store, or Month.

**Values** contains the **measure**—the numeric field you want Excel to calculate, like Sales, Profit, Units, or Cost.

This distinction is fundamental in analytics:

- **Dimensions** describe _what_ you're analyzing.
- **Measures** quantify _how much_ or _how many_.