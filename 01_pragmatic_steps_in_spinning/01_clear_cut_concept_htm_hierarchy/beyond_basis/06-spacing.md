# 06 — Spacing (Horizontal & Vertical)

---

## HTML Spacing Tools

### 1. `&nbsp;` — Non-Breaking Space (Horizontal ↔)

Adds a single horizontal space that won't wrap to the next line.

```html
<p>First &nbsp; Second</p>              <!-- 1 space -->
<p>First &nbsp;&nbsp;&nbsp; Second</p>  <!-- 3 spaces -->
```

- Each `&nbsp;` = one extra space unit
- **Use for:** small inline gaps between text/elements
- **Do not use for:** large layout spacing (use CSS margin/padding instead)

---

### 2. `<br>` — Line Break (Vertical ↕)

Forces content to the next line. Self-closing, no closing tag.

```html
<p>Line one<br>Line two<br>Line three</p>
```

Renders as:
```
Line one
Line two
Line three
```

Stack multiple for more vertical space:
```html
<p>Top content</p>
<br>
<br>
<br>
<p>Bottom content — 3 lines below</p>
```

- **Use for:** address formatting, poems, intentional line breaks within text
- **Do not use for:** spacing between sections/blocks (use CSS margin instead)

---

### 3. `<hr>` — Horizontal Rule (Visual Divider)

Adds a horizontal line AND creates vertical space around it.

```html
<p>Section one content.</p>
<hr>
<p>Section two content.</p>
```

- Self-closing block element
- Creates visual separation between thematic content blocks
- Has natural top and bottom margin

---

## CSS Spacing (The Professional Way)

> 💡 These are CSS hints — essential to understand for real spacing control.

### margin — Space OUTSIDE the element

```html
<div style="margin-top: 40px;">Space above me</div>
<div style="margin-bottom: 20px;">Space below me</div>
<div style="margin-left: 30px;">Space to my left</div>
<div style="margin-right: 30px;">Space to my right</div>

<!-- shorthand: top right bottom left -->
<div style="margin: 20px 10px 20px 10px;">All sides</div>

<!-- equal all sides -->
<div style="margin: 20px;">Same on all sides</div>
```

### padding — Space INSIDE the element

```html
<div style="padding: 20px;">
  Content has breathing room inside the box
</div>

<div style="padding-top: 40px; padding-left: 20px;">
  Custom padding per side
</div>
```

---

## margin vs padding — Key Difference

```
┌─────────────────────────────────┐
│           MARGIN                │  ← outside (pushes other elements away)
│   ┌─────────────────────────┐   │
│   │        PADDING          │   │  ← inside (pushes content away from border)
│   │   ┌─────────────────┐   │   │
│   │   │    CONTENT      │   │   │
│   │   └─────────────────┘   │   │
│   └─────────────────────────┘   │
└─────────────────────────────────┘
```

| Property | Space location | Effect |
|---|---|---|
| `margin` | Outside the element | Pushes other elements away |
| `padding` | Inside the element | Pushes content away from edges |

---

## Spacing Quick Reference

| Method | Direction | Type | Use when |
|---|---|---|---|
| `&nbsp;` | Horizontal ↔ | HTML | Small gaps between inline text |
| `<br>` | Vertical ↕ | HTML | Line breaks within text blocks |
| `<hr>` | Vertical ↕ | HTML | Thematic visual divider |
| `margin` | Both ↔↕ | CSS | Space between block elements |
| `padding` | Both ↔↕ | CSS | Space inside an element |

---

## Common Mistakes

```html
❌ Using &nbsp;&nbsp;&nbsp;&nbsp; for layout spacing
❌ Using <br><br><br><br> instead of CSS margin
❌ Using <table> just to create columns with spacing
✅ Use margin/padding for all meaningful layout spacing
✅ Use &nbsp; only for minor inline text adjustments
✅ Use <br> only for intentional line breaks in text content
```
