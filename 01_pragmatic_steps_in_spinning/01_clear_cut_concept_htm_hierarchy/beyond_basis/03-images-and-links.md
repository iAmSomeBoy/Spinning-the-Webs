# 03 — Images & Links

---

## `<img>` — Images

`<img>` is a **self-closing inline-block** element. It has no closing tag.

```html
<img src="photo.jpg" alt="A landscape photo">
```

### Required Attributes

| Attribute | Purpose |
|---|---|
| `src` | Path or URL to the image file |
| `alt` | Text description (accessibility, shown if image fails) |

### Optional Attributes

```html
<img
  src="photo.jpg"
  alt="Description"
  width="400"          <!-- width in pixels -->
  height="300"         <!-- height in pixels -->
  loading="lazy"       <!-- loads only when scrolled into view -->
  title="Hover text"   <!-- tooltip on hover -->
>
```

### Parent Rules for `<img>`
- **Valid parents:** `<div>`, `<p>`, `<section>`, `<article>`, `<figure>`, `<a>`, `<li>`, `<td>`, any block or inline-block
- **Invalid parents:** none — img is very flexible

```html
<!-- img inside p (inline context) -->
<p>Here is an image: <img src="icon.png" alt="icon"> in the text.</p>

<!-- img inside div (block context) -->
<div>
  <img src="banner.jpg" alt="Banner">
</div>

<!-- img inside a (clickable image) -->
<a href="page.html">
  <img src="thumbnail.jpg" alt="Go to page">
</a>
```

---

## `<figure>` & `<figcaption>` — Image with Caption

```
figure                  ← groups image + caption
 ├── img                ← the image
 └── figcaption         ← caption (ONLY valid inside figure)
```

```html
<figure>
  <img src="chart.png" alt="Sales chart">
  <figcaption>Figure 1: Monthly sales for 2026.</figcaption>
</figure>
```

- `<figure>` is a **block** element
- `<figcaption>` is ONLY valid inside `<figure>`
- `<figcaption>` can be first OR last child of `<figure>`
- **Parent of figure:** any block element — `<main>`, `<section>`, `<article>`, `<div>`

---

## `<a>` — Links (Anchors)

`<a>` is an **inline** element that creates hyperlinks.

```html
<a href="https://example.com">Visit Example</a>
```

### Key Attributes

| Attribute | Purpose | Example |
|---|---|---|
| `href` | Destination URL | `href="https://google.com"` |
| `target` | Where to open | `target="_blank"` (new tab) |
| `rel` | Relationship to linked page | `rel="noopener"` |
| `download` | Downloads the file instead of opening | `download` |
| `title` | Tooltip on hover | `title="Go to home"` |

### Types of Links

```html
<!-- External link -->
<a href="https://example.com" target="_blank" rel="noopener">
  External Site
</a>

<!-- Internal page link -->
<a href="/about.html">About Page</a>

<!-- Section anchor (jumps to id on same page) -->
<a href="#section2">Jump to Section 2</a>
<section id="section2">...</section>

<!-- Email link -->
<a href="mailto:hello@example.com">Send Email</a>

<!-- Phone link -->
<a href="tel:+1234567890">Call Us</a>

<!-- Download link -->
<a href="file.pdf" download>Download PDF</a>
```

### What `<a>` Can Contain

```html
<!-- text (most common) -->
<a href="#">Click here</a>

<!-- span inside a -->
<a href="#"><span>Styled link text</span></a>

<!-- img inside a (clickable image) -->
<a href="#">
  <img src="logo.png" alt="Home">
</a>

<!-- multiple inline elements -->
<a href="#">
  <img src="icon.png" alt="">
  <span>Read More</span>
</a>
```

### ❌ What `<a>` Cannot Contain
```html
❌ <a href="#"><div>...</div></a>        <!-- block inside inline -->
❌ <a href="#"><p>text</p></a>           <!-- block inside inline -->
❌ <a href="#"><a href="#">nested</a></a> <!-- a inside a = invalid -->
```

---

## Image Formats Reference

| Format | Best for |
|---|---|
| `.jpg` / `.jpeg` | Photos, complex images |
| `.png` | Images needing transparency |
| `.svg` | Icons, logos (scales perfectly) |
| `.webp` | Modern format, smaller file size |
| `.gif` | Simple animations |

---

## Parent-Child Summary

| Tag | Valid Parents | Valid Children |
|---|---|---|
| `<img>` | any block or inline-block | nothing (self-closing) |
| `<figure>` | any block element | `<img>`, `<figcaption>`, `<video>`, `<code>` |
| `<figcaption>` | `<figure>` ONLY | text, inline elements |
| `<a>` | any block or inline | text, `<span>`, `<img>` — inline only |
