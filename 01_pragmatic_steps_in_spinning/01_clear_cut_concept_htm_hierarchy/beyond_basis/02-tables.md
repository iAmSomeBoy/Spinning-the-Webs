# 02 — Tables

## What is a Table?

A `<table>` organizes data into **rows and columns**. It is a **block element** and should only be used for **tabular data** — never for page layout.

---

## Table Family Hierarchy

```
table                     ← root
 ├── caption              ← table title (optional, must be FIRST child)
 ├── thead                ← header row group
 │    └── tr              ← a row
 │         ├── th         ← header cell (bold, centered by default)
 │         └── th
 ├── tbody                ← body row group (main data)
 │    ├── tr
 │    │    ├── td         ← data cell
 │    │    └── td
 │    └── tr
 │         ├── td
 │         └── td
 └── tfoot                ← footer row group (totals, summaries)
      └── tr
           ├── td
           └── td
```

---

## Each Tag Explained

### `<table>` — Root Container
```html
<table>
  <!-- everything lives here -->
</table>
```
- **Parent:** any block element (`<div>`, `<section>`, `<main>`, `<body>`)
- **Children:** `<caption>`, `<thead>`, `<tbody>`, `<tfoot>` ONLY as direct children

---

### `<caption>` — Table Title
```html
<table>
  <caption>Monthly Sales Report</caption>
  <!-- rest of table -->
</table>
```
- Must be the **FIRST child** of `<table>`
- Displays as a title above the table
- **Parent:** `<table>` ONLY

---

### `<thead>`, `<tbody>`, `<tfoot>` — Row Groups
```html
<table>
  <thead>...</thead>    <!-- header rows -->
  <tbody>...</tbody>    <!-- data rows -->
  <tfoot>...</tfoot>    <!-- footer/summary rows -->
</table>
```
- All three are **optional but recommended** for semantics
- Each can only contain `<tr>` as children
- **Parent:** `<table>` ONLY
- **Children:** `<tr>` ONLY

---

### `<tr>` — Table Row
```html
<tr>
  <td>Cell 1</td>
  <td>Cell 2</td>
</tr>
```
- Represents one horizontal row
- **Parent:** `<thead>`, `<tbody>`, `<tfoot>` ONLY
- **Children:** `<th>` or `<td>` ONLY

---

### `<th>` — Header Cell
```html
<tr>
  <th>Name</th>
  <th>Age</th>
  <th>City</th>
</tr>
```
- Bold and centered by default
- Use in `<thead>` rows
- **Parent:** `<tr>` ONLY
- **Children:** any inline or block content

---

### `<td>` — Data Cell
```html
<tr>
  <td>Alice</td>
  <td>25</td>
  <td>New York</td>
</tr>
```
- Regular data cell
- **Parent:** `<tr>` ONLY
- **Children:** any inline or block content — even nested tables!

---

## Spanning Cells

```html
<!-- colspan: cell spans multiple columns -->
<td colspan="2">I take up 2 columns</td>

<!-- rowspan: cell spans multiple rows -->
<td rowspan="3">I take up 3 rows</td>
```

---

## Full Table Example

```html
<table>

  <caption>Student Grades</caption>

  <thead>
    <tr>
      <th>Name</th>
      <th>Subject</th>
      <th>Grade</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>Alice</td>
      <td>Math</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Bob</td>
      <td>Science</td>
      <td>B+</td>
    </tr>
    <tr>
      <td>Carol</td>
      <td>English</td>
      <td>A-</td>
    </tr>
  </tbody>

  <tfoot>
    <tr>
      <td colspan="2">Class Average</td>
      <td>A-</td>
    </tr>
  </tfoot>

</table>
```

---

## Parent-Child Rules Summary

| Tag | Must be inside | Can contain |
|---|---|---|
| `<table>` | any block | caption, thead, tbody, tfoot |
| `<caption>` | `<table>` ONLY | text, inline elements |
| `<thead>` | `<table>` ONLY | `<tr>` ONLY |
| `<tbody>` | `<table>` ONLY | `<tr>` ONLY |
| `<tfoot>` | `<table>` ONLY | `<tr>` ONLY |
| `<tr>` | thead, tbody, tfoot ONLY | `<th>` or `<td>` ONLY |
| `<th>` | `<tr>` ONLY | text, inline, block content |
| `<td>` | `<tr>` ONLY | text, inline, block, even nested table |

---

## ⚠️ Common Mistakes

```html
❌ <table><td>data</td></table>         ← missing tr
❌ <table><tr><tr></tr></tr></table>    ← tr inside tr
❌ Use table for page layout            ← NEVER do this
✅ Use table ONLY for data grids
```
