# 📘 HTML Layout & Hierarchy — Study Notes

A compact but complete reference on HTML layout hierarchy, parent-child relationships, block vs inline elements, and page structure. Based on a full Q&A learning session.

---

## 📂 Repository Structure

```
Spinning-the-Webs/01-pragmatic-steps-in-spinning
├── README.md                        ← You are here
├── 01_clear_cut_concepts/
│   ├── 01-core-concept.md           ← DOM tree, nesting, basic rules
│   ├── 02-block-vs-inline.md        ← Block, inline, inline-block explained
│   ├── 03-div-section-article.md    ← When to use which container
│   ├── 04-parent-child-table.md     ← Who can be whose child/parent/sibling
│   ├── 05-homepage-hierarchy.md     ← Homepage layout structure
│   └── 06-flexbox-hint.md           ← CSS flexbox (complementary hint only)
└── 02_core_layouts/
    ├── 01-basic-body-skeleton.html       ← Minimal valid HTML page
    ├── 02-header-nav-footer.html         ← Header, nav, footer relations
    ├── 03-main-sections.html             ← Main → sections hierarchy
    ├── 04-section-article-aside.html     ← Section, article, aside relations
    ├── 05-full-homepage-hierarchy.html   ← Full homepage all tags combined
    ├── 06-block-vs-inline-demo.html      ← Block vs inline behaviour
    ├── 07-deep-nesting.html              ← Deep parent-child-grandchild chains
    └── 08-siblings-demo.html             ← Sibling relationships at body level
```

---

## 🧠 Key Concepts at a Glance

| Concept | Answer |
|---|---|
| Top-most tag | `<html>` |
| Top visible container | `<body>` |
| Page regions | `<header>`, `<main>`, `<footer>`, `<nav>`, `<aside>` |
| Content zones | `<section>`, `<article>` |
| Generic containers | `<div>` (block), `<span>` (inline) |
| Siblings of `<main>` | `<header>`, `<nav>`, `<aside>`, `<footer>` |
| Smallest inline unit | `<span>` |
| Most flexible parent | `<div>` |

---

## 📖 How to Use This Repo

1. Read notes in order (`01` → `06`) for full understanding
2. Open each `.html` file in a browser to see live structure
3. Use browser DevTools (F12) to inspect the DOM tree visually
4. If you are benefitted, give a star
5. You are also encouraged to contribute in this repo
