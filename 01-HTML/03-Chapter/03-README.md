# 🧱 HTML Chapter 3 — Layout, Semantics & Developer Workflow

## 📑 Table of Contents

- [1. Block vs Inline Elements](#1-block-vs-inline-elements)
- [2. `<div>` — Block Container](#2-div--block-container)
- [3. `<span>` — Inline Container](#3-span--inline-container)
- [4. `<hr>` — Horizontal Rule](#4-hr--horizontal-rule)
- [5. `<sup>` & `<sub>` — Superscript / Subscript](#5-sup--sub--superscript--subscript)
- [6. Semantic HTML](#6-semantic-html)
- [7. Semantic Tags Reference](#7-semantic-tags-reference)
- [8. HTML Entities](#8-html-entities)
- [9. Emmet Abbreviations](#9-emmet-abbreviations)
- [10. HTML Boilerplate](#10-html-boilerplate)
- [11. HTML Best Practices](#11-html-best-practices)
- [12. Core Concepts](#12-core-concepts)
- [13. Common Mistakes](#13-common-mistakes)
- [14. Cheat Sheet](#14-cheat-sheet)

---

## 1. Block vs Inline Elements

### Block Elements
Start on a **new line** and occupy the **full available width** of their parent.

```html
<div> <p> <h1>...<h6> <header> <footer> <section> <article> <nav> <main> <ul> <ol> <li>
```

- Used to build webpage structure
- Can contain block and inline elements

### Inline Elements
Occupy only the width their content needs and **do not** start on a new line.

```html
<span> <a> <img> <b> <i> <strong> <em> <sup> <sub> <label>
```

- Used to style or format text
- Cannot contain block elements

```html
<p>I am learning <span>HTML</span> and <span>CSS</span>.</p>
```

### Comparison

| Feature | Block Element | Inline Element |
|---|---|---|
| Starts on new line | ✅ Yes | ❌ No |
| Width | Full width | Required width |
| Purpose | Page layout | Text formatting |
| Examples | `<div>`, `<p>` | `<span>`, `<a>` |

---

## 2. `<div>` — Block Container

A generic **block-level container** used to group elements. No default styling.

```html
<div>
    <h2>About Me</h2>
    <p>I am learning Full Stack Web Development.</p>
</div>
```

- Starts on a new line, occupies full width
- Groups related elements together
- Commonly paired with CSS and JavaScript

---

## 3. `<span>` — Inline Container

A generic **inline container** used to style a small portion of text without breaking the line.

```html
<p>My favourite language is <span style="color:red;">Java</span>.</p>
```

### `<div>` vs `<span>`

| `<div>` | `<span>` |
|---|---|
| Block element | Inline element |
| Full width | Required width |
| Used for layout | Used for text styling |
| Starts new line | Stays on same line |

---

## 4. `<hr>` — Horizontal Rule

Draws a horizontal line to separate sections. An **empty/void element** — no closing tag.

```html
<h2>Introduction</h2>
<hr>
<h2>Conclusion</h2>
```

---

## 5. `<sup>` & `<sub>` — Superscript / Subscript

| Tag | Effect | Example | Output |
|---|---|---|---|
| `<sup>` | Raises text | `x<sup>2</sup>` | x² |
| `<sub>` | Lowers text | `H<sub>2</sub>O` | H₂O |

```html
<p>(a+b)<sup>2</sup></p>
<p>H<sub>2</sub>SO<sub>4</sub></p>
```

Used in mathematical and scientific notation.

---

## 6. Semantic HTML

**Semantic markup** means choosing elements based on the *meaning* of the content, not just its appearance — improving readability, SEO, and accessibility.

```html
<!-- ❌ Non-semantic -->
<div class="header">My Website</div>
<div class="menu">Home About Contact</div>
<div class="footer">Copyright</div>
```

```html
<!-- ✅ Semantic -->
<header>My Website</header>
<nav>Home About Contact</nav>
<footer>Copyright</footer>
```

**Benefits:** better SEO · improved accessibility · easier maintenance · clearer structure

---

## 7. Semantic Tags Reference

| Tag | Purpose |
|---|---|
| `<header>` | Introductory content — logo, title, nav, search |
| `<nav>` | Navigation links |
| `<main>` | Primary content (**only one per page**) |
| `<section>` | Groups related content |
| `<article>` | Independent, self-contained content (blog post, review) |
| `<aside>` | Sidebar / related content |
| `<footer>` | Bottom section — copyright, contact, links |

### Full Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Semantic HTML</title>
</head>
<body>

  <header>
    <h1>My Website</h1>
    <nav>
      <a href="#">Home</a>
      <a href="#">About</a>
      <a href="#">Contact</a>
    </nav>
  </header>

  <main>
    <section>
      <h2>Latest Articles</h2>
      <article>
        <h3>HTML Basics</h3>
        <p>Learning Semantic HTML.</p>
      </article>
    </section>

    <aside>
      <h3>Related Posts</h3>
      <p>CSS Basics</p>
    </aside>
  </main>

  <footer>
    <p>&copy; 2026 Aman Salmani</p>
  </footer>

</body>
</html>
```

---

## 8. HTML Entities

Reserved characters are displayed safely using **entities**, which begin with `&` and end with `;`.

| Character | Entity |
|---|---|
| `<` | `&lt;` |
| `>` | `&gt;` |
| `&` | `&amp;` |
| `"` | `&quot;` |
| `'` | `&apos;` |
| Space | `&nbsp;` |
| © | `&copy;` |
| ® | `&reg;` |
| ™ | `&trade;` |
| ₹ | `&#8377;` |

```html
<p>&lt;h1&gt;Hello&lt;/h1&gt;</p>   <!-- <h1>Hello</h1> -->
<p>&copy; 2026 Aman Salmani</p>    <!-- © 2026 Aman Salmani -->
Price: &#8377;500                 <!-- Price: ₹500 -->
```

---

## 9. Emmet Abbreviations

**Emmet** is a built-in editor toolkit (VS Code and others) that expands short abbreviations into full HTML on `Tab`.

| Operator | Meaning | Abbreviation | Expands To |
|---|---|---|---|
| `!` | Boilerplate | `!` | Full HTML5 template |
| `>` | Child | `div>p` | `<div><p></p></div>` |
| `+` | Sibling | `h1+p` | `<h1></h1><p></p>` |
| `*` | Multiply | `li*5` | 5× `<li></li>` |
| `$` | Numbering | `li.item$*5` | `class="item1"` … `item5` |
| `.` | Class | `div.container` | `<div class="container"></div>` |
| `#` | ID | `div#header` | `<div id="header"></div>` |
| `{}` | Text content | `h1{Welcome}` | `<h1>Welcome</h1>` |
| `[]` | Attributes | `input[type="text"]` | `<input type="text">` |

**Composite example**

```text
header>nav>ul>li*4>a{Home}
```

```html
<header>
  <nav>
    <ul>
      <li><a href="">Home</a></li>
      <li><a href="">Home</a></li>
      <li><a href="">Home</a></li>
      <li><a href="">Home</a></li>
    </ul>
  </nav>
</header>
```

| Shortcut | Result |
|---|---|
| `!` | HTML boilerplate |
| `ul>li*5` | List with 5 items |
| `table>tr*3>td*4` | 3×4 table |
| `header>nav>ul>li*4>a` | Basic nav bar |

---

## 10. HTML Boilerplate

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>

</body>
</html>
```

| Tag | Purpose |
|---|---|
| `<!DOCTYPE html>` | HTML5 declaration |
| `<html>` | Root element |
| `<head>` | Metadata |
| `<meta charset>` | Character encoding |
| `<meta viewport>` | Responsive scaling |
| `<title>` | Browser tab title |
| `<body>` | Visible content |

---

## 11. HTML Best Practices

| Practice | ❌ Avoid | ✅ Prefer |
|---|---|---|
| Use semantic tags | `<div class="header">` | `<header>` |
| Indent properly | `<div><p>Hello</p></div>` | Multi-line, nested indentation |
| Lowercase tags | `<BODY>` | `<body>` |
| Double-quote attributes | `<img src='x.png'>` | `<img src="x.png">` |
| Meaningful class names | `class="abc"` | `class="navbar"` |
| Always add `alt` text | `<img src="cat.png">` | `<img src="cat.png" alt="Sleeping Cat">` |
| Comment key sections | — | `<!-- Navigation Starts --> ... <!-- Navigation Ends -->` |
| Group related sections | — | `<header>` / `<main>` / `<footer>` |

---

## 12. Core Concepts

**HTML** (HyperText Markup Language) structures content — CSS handles styling, JavaScript handles behavior.

An element typically has: **opening tag → content → closing tag**

```html
<p>Hello World</p>
```

**Void (self-closing) elements** — no closing tag required:

```html
<br> <hr> <img> <input> <meta> <link>
```

**Nesting** — elements can be placed inside other elements:

```html
<div>
  <p>Learning <strong>HTML</strong></p>
</div>
```

---

## 13. Common Mistakes

```html
<!-- ❌ Div soup -->
<div><div><div></div></div></div>

<!-- ✅ Semantic structure -->
<header></header>
<main></main>
<footer></footer>
```

```html
<!-- ❌ Poor indentation -->
<div>
<p>Hello</p>
</div>

<!-- ✅ Proper indentation -->
<div>
    <p>Hello</p>
</div>
```

```html
<!-- ❌ Missing alt text -->
<img src="logo.png">

<!-- ✅ Descriptive alt text -->
<img src="logo.png" alt="Website Logo">
```

```html
<!-- ❌ Multiple <main> tags — only ONE allowed per page -->
<main></main>
<main></main>
```

---

## 14. Cheat Sheet

**Block elements**
```html
<div> <p> <section> <header> <footer> <main>
```

**Inline elements**
```html
<span> <a> <img> <sup> <sub>
```

**Semantic tags**
```html
<header> <nav> <main> <section> <article> <aside> <footer>
```

**HTML entities**
```html
&lt; &gt; &amp; &nbsp; &copy; &#8377;
```

**Void elements**
```html
<br> <hr> <img> <input> <meta> <link>
```

**Emmet**
```text
! | div | div.container | div#header | ul>li*5 | li.item$*5 | header>nav>ul>li*4>a
```
