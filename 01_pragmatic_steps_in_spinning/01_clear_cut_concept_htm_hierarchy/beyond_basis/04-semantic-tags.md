# 04 — Semantic Tags

## What are Semantic Tags?

Semantic tags give **meaning** to content beyond just visually grouping it. They tell browsers, search engines, and screen readers WHAT the content is — not just where it sits.

---

## Full Semantic Tags Reference

---

### `<time>` — Dates and Times

```html
<time datetime="2026-04-28">April 28, 2026</time>
<time datetime="2026-04-28T09:00">9:00 AM, April 28</time>
```

- `datetime` attribute = machine-readable format
- Display text between tags = human-readable
- **Type:** inline
- **Parent:** any block or inline context
- **Children:** text only

```html
<p>Published on <time datetime="2026-04-28">April 28, 2026</time>.</p>
<p>Event starts at <time datetime="18:30">6:30 PM</time>.</p>
```

---

### `<address>` — Contact Information

```html
<address>
  <p>MyBrand Inc.</p>
  <p>123 Main Street, New York, NY</p>
  <a href="mailto:hello@mybrand.com">hello@mybrand.com</a>
</address>
```

- Used for contact info of the nearest `<article>` or `<body>`
- **Type:** block
- **Parent:** `<body>`, `<article>`, `<footer>`, `<section>`
- **Children:** inline elements and `<p>` — NOT headings or sections

---

### `<mark>` — Highlighted Text

```html
<p>Search results for <mark>HTML tutorial</mark> found 42 items.</p>
```

- Highlights text like a yellow marker pen (by default)
- **Type:** inline
- **Parent:** any block or inline
- **Children:** text only

---

### `<abbr>` — Abbreviations

```html
<p>I am learning <abbr title="HyperText Markup Language">HTML</abbr>.</p>
```

- `title` attribute shows the full form on hover
- **Type:** inline
- **Parent:** any block or inline
- **Children:** text only

---

### `<cite>` — Creative Work Title

```html
<p>I read <cite>The HTML Handbook</cite> last week.</p>
<blockquote>
  <p>Structure gives meaning.</p>
  <cite>— Tim Berners-Lee</cite>
</blockquote>
```

- Used for titles of books, films, songs, articles
- Also used to attribute quotes
- **Type:** inline
- **Children:** text only

---

### `<blockquote>` — Long Quotes

```html
<blockquote cite="https://source.com">
  <p>The web is more a social creation than a technical one.</p>
</blockquote>
```

- For quoting from another source
- `cite` attribute = source URL (not displayed)
- **Type:** block
- **Parent:** any block element
- **Children:** `<p>`, block and inline elements

---

### `<q>` — Short Inline Quote

```html
<p>He said <q>HTML is easy to learn</q> and I agreed.</p>
```

- Adds quotation marks automatically
- **Type:** inline (vs `<blockquote>` which is block)
- **Children:** text only

---

### `<code>` — Inline Code

```html
<p>Use the <code>display: flex</code> property to align items.</p>
```

- Displays in monospace font
- **Type:** inline
- **Children:** text only

---

### `<pre>` — Preformatted Text

```html
<pre>
  This text
    preserves    all
  spaces and line breaks
</pre>
```

- Preserves whitespace and line breaks exactly
- **Type:** block
- **Children:** text, `<code>` (common combination)

```html
<pre><code>
  function hello() {
    return "world";
  }
</code></pre>
```

---

### `<details>` & `<summary>` — Expandable Content

```
details                   ← collapsible container
 ├── summary              ← always visible title/toggle
 └── (any content)        ← hidden until clicked
```

```html
<details>
  <summary>What is HTML?</summary>
  <p>HTML stands for HyperText Markup Language. It is the standard language for web pages.</p>
</details>
```

- `<summary>` must be the **first child** of `<details>`
- Content below summary is hidden/shown on click
- No JavaScript needed — pure HTML
- **Parent of details:** any block element
- **Parent of summary:** `<details>` ONLY

---

### `<strong>` vs `<b>` — Bold

```html
<strong>Important warning!</strong>   <!-- semantic: important meaning -->
<b>Bold text</b>                       <!-- visual only: no meaning -->
```

Use `<strong>` when the bold carries importance. Use `<b>` for purely visual bold.

---

### `<em>` vs `<i>` — Italic

```html
<em>Really important</em>    <!-- semantic: stressed emphasis -->
<i>Italic text</i>            <!-- visual only: no meaning -->
```

---

### `<small>` — Fine Print

```html
<p><small>© 2026 MyBrand. All rights reserved.</small></p>
```

- For disclaimers, copyright, fine print
- **Type:** inline

---

### `<sub>` and `<sup>` — Subscript & Superscript

```html
<p>Water formula: H<sub>2</sub>O</p>
<p>Einstein: E = mc<sup>2</sup></p>
```

- `<sub>` goes below the line
- `<sup>` goes above the line
- Both are **inline**

---

### `<hr>` — Horizontal Rule (Thematic Break)

```html
<section>
  <p>First topic content.</p>
  <hr>
  <p>Second topic content.</p>
</section>
```

- Self-closing block element
- Represents a **thematic break** between content
- Renders as a horizontal line

---

## Semantic Tags Quick Reference

| Tag | Type | Purpose |
|---|---|---|
| `<time>` | inline | dates and times |
| `<address>` | block | contact information |
| `<mark>` | inline | highlighted text |
| `<abbr>` | inline | abbreviations with tooltips |
| `<cite>` | inline | titles of works, attribution |
| `<blockquote>` | block | long external quotes |
| `<q>` | inline | short inline quotes |
| `<code>` | inline | inline code snippet |
| `<pre>` | block | preformatted/code blocks |
| `<details>` | block | expandable content |
| `<summary>` | block | toggle for details |
| `<strong>` | inline | important bold text |
| `<em>` | inline | stressed italic text |
| `<small>` | inline | fine print |
| `<sub>` | inline | subscript |
| `<sup>` | inline | superscript |
| `<hr>` | block | thematic break / divider |
