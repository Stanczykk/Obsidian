#  Regex

Regex = **Regular Expression**

Regex is a language for describing text patterns.

Use regex when simple methods like:

```
.str.contains()
.str.startswith()
.str.endswith()
```

aren't enough.

### Common regex symbols

|Regex|Meaning|
|---|---|
|`[a-z]`|lowercase letter|
|`[A-Z]`|uppercase letter|
|`[0-9]`|digit|
|`[A-Za-z]`|any letter|
|`[A-Za-z0-9]`|letter or digit|
|`+`|one or more|
|`*`|zero or more|
|`?`|zero or one|
|`^`|beginning|
|`$`|end|
|`.`|any character|
|`\.`|literal period|
|`|`|
|`{4}`|exactly 4|
|`{2,4}`|2 to 4|

---

# 9. Regex Examples

## Starts with JBL1

```
^JBL1
```

Means:

```
^
↓
beginning

JBL1
↓
must appear here
```

Matches:

```
JBL1       ✓
JBL123     ✓
JBL1-ABC   ✓
```

Doesn't match:

```
1JBL1      ✗
ABCJBL1    ✗
```

For simple prefixes, prefer:

```
.str.startswith("JBL1")
```

---

## Exactly JBL1

```
^JBL1$
```

`^` = beginning

`$` = end

Therefore the entire string must be exactly:

```
JBL1
```

---

# 10. Regex in Pandas

Important regex-related `.str` methods:

|Method|Purpose|
|---|---|
|`.str.match()`|Match regex from beginning|
|`.str.fullmatch()`|Entire string must match regex|
|`.str.contains()`|Search for regex anywhere|
|`.str.extract()`|Extract text using regex|
|`.str.replace()`|Replace using regex|

### `.str.fullmatch()`

Useful for **validation**.

```
df["code"].str.fullmatch(r"[A-Z]{3}[0-9]{4}")
```

Conceptually:

> Does the entire value follow this pattern?

