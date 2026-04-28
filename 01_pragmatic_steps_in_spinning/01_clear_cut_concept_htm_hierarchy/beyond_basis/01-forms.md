# 01 — Forms

## What is a Form?

A `<form>` is a container that collects user input and sends it somewhere (a server, email, etc.). It is a **block element** and a direct child of `<body>` or any block container.

---

## Form Family Hierarchy

```
form                        ← root of form
 ├── fieldset               ← groups related inputs
 │    ├── legend            ← title of the fieldset (ONLY inside fieldset)
 │    ├── label             ← describes an input
 │    └── input             ← the actual input field
 ├── label                  ← can also live directly in form
 ├── input                  ← text, email, password, checkbox, radio, etc.
 ├── textarea               ← multi-line text input
 ├── select                 ← dropdown
 │    ├── option            ← each choice
 │    └── optgroup          ← group of options
 │         └── option
 └── button                 ← submit / reset / custom action
```

---

## `<form>` — The Root Container

```html
<form action="/submit" method="POST">
  <!-- all inputs live here -->
</form>
```

| Attribute | What it does |
|---|---|
| `action` | Where to send the data (URL) |
| `method` | How to send: `GET` or `POST` |

- **Parent:** `<body>`, `<main>`, `<section>`, `<div>` (any block)
- **Children:** `<fieldset>`, `<label>`, `<input>`, `<textarea>`, `<select>`, `<button>`

---

## `<fieldset>` & `<legend>` — Grouping

```html
<fieldset>
  <legend>Personal Information</legend>
  <!-- inputs here -->
</fieldset>
```

- `<fieldset>` groups related inputs visually and semantically
- `<legend>` is the **title** of the group — ONLY valid inside `<fieldset>`
- **Parent of fieldset:** `<form>`
- **Parent of legend:** `<fieldset>` ONLY

---

## `<label>` — Describing Inputs

```html
<!-- Method 1: wrap the input -->
<label>
  Username
  <input type="text">
</label>

<!-- Method 2: use 'for' attribute matching input 'id' -->
<label for="email">Email</label>
<input id="email" type="email">
```

- `<label>` is an **inline** element
- Always pair every `<input>` with a `<label>` for accessibility

---

## `<input>` — All Types

`<input>` is a **self-closing** inline-block element (no closing tag needed).

```html
<input type="text">        <!-- single line text -->
<input type="email">       <!-- email validation -->
<input type="password">    <!-- hidden text -->
<input type="number">      <!-- numbers only -->
<input type="checkbox">    <!-- tick box -->
<input type="radio">       <!-- one of many choices -->
<input type="file">        <!-- file upload -->
<input type="date">        <!-- date picker -->
<input type="submit">      <!-- submit button -->
<input type="hidden">      <!-- invisible data -->
```

Common attributes:
```html
<input
  type="text"
  name="username"        <!-- key when form is submitted -->
  id="username"          <!-- links to label's 'for' -->
  placeholder="Enter name"  <!-- hint text -->
  required               <!-- cannot submit if empty -->
  value="default text"   <!-- pre-filled value -->
>
```

---

## `<textarea>` — Multi-line Input

```html
<textarea name="message" rows="5" cols="40">
  Default text here
</textarea>
```

- Unlike `<input>`, `<textarea>` has an opening AND closing tag
- Content between tags = default text
- **Parent:** `<form>`, `<fieldset>`, `<div>`

---

## `<select>` — Dropdown

```html
<select name="country">
  <option value="">-- Choose --</option>
  <option value="us">United States</option>

  <optgroup label="Europe">
    <option value="uk">United Kingdom</option>
    <option value="de">Germany</option>
  </optgroup>

</select>
```

- `<select>` children: `<option>` and `<optgroup>` ONLY
- `<optgroup>` children: `<option>` ONLY
- `selected` attribute pre-selects an option: `<option selected>`

---

## `<button>` — Actions

```html
<button type="submit">Submit Form</button>
<button type="reset">Clear All</button>
<button type="button">Custom Action</button>
```

| Type | What it does |
|---|---|
| `submit` | Sends the form data |
| `reset` | Clears all inputs |
| `button` | Does nothing unless JS is attached |

- `<button>` can contain text AND inline elements like `<span>`, `<img>`
- **Parent:** `<form>`, `<div>`, any block container

---

## Full Form Example

```html
<form action="/register" method="POST">

  <fieldset>
    <legend>Account Details</legend>

    <label for="username">Username</label>
    <input type="text" id="username" name="username" required>

    <label for="email">Email</label>
    <input type="email" id="email" name="email" required>

    <label for="password">Password</label>
    <input type="password" id="password" name="password" required>

  </fieldset>

  <fieldset>
    <legend>Preferences</legend>

    <label>
      <input type="checkbox" name="newsletter"> Subscribe to newsletter
    </label>

    <label>Gender</label>
    <label><input type="radio" name="gender" value="m"> Male</label>
    <label><input type="radio" name="gender" value="f"> Female</label>

    <label for="country">Country</label>
    <select id="country" name="country">
      <option value="us">United States</option>
      <option value="uk">United Kingdom</option>
    </select>

  </fieldset>

  <label for="bio">Bio</label>
  <textarea id="bio" name="bio" rows="4"></textarea>

  <button type="submit">Register</button>
  <button type="reset">Clear</button>

</form>
```

---

## Parent-Child Rules Summary

| Tag | Must be inside | Can contain |
|---|---|---|
| `<form>` | any block element | fieldset, label, input, textarea, select, button, div |
| `<fieldset>` | `<form>` | legend, label, input, textarea, select, div |
| `<legend>` | `<fieldset>` ONLY | text, inline elements |
| `<label>` | form, fieldset, div | text, input, span |
| `<input>` | form, fieldset, label, div | nothing (self-closing) |
| `<textarea>` | form, fieldset, div | text only |
| `<select>` | form, fieldset, div | option, optgroup ONLY |
| `<option>` | select, optgroup ONLY | text only |
| `<optgroup>` | select ONLY | option ONLY |
| `<button>` | form, div, any block | text, span, img |
