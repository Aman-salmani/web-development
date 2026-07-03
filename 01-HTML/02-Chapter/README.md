# HTML Chapter 2 - Lists, Attributes, Links & Images

## Topics Covered

- HTML Lists
- HTML Attributes
- Anchor Element (`<a>`)
- Image Element (`<img>`)
- More HTML Tags
- HTML Comments
- HTML Case Sensitivity

---

# 1. HTML Lists

## Definition

HTML Lists are used to display a collection of related items in an organized format.

## Types of HTML Lists

1. Ordered List (`<ol>`)
2. Unordered List (`<ul>`)
3. Description List (`<dl>`)

---

## 1.1 Ordered List (`<ol>`)

### Definition

Displays items in a numbered sequence.

### Syntax

```html
<ol>
    <li>Item 1</li>
    <li>Item 2</li>
</ol>
```

### Key Points

- Uses numbers by default.
- Each item is written inside the `<li>` tag.
- Supports attributes like `type` and `start`.

### Example

```html
<ol>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ol>
```

### Output

1. HTML
2. CSS
3. JavaScript

---

## 1.2 Unordered List (`<ul>`)

### Definition

Displays items using bullet points.

### Syntax

```html
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
</ul>
```

### Key Points

- Uses bullet points.
- Each item is enclosed inside the `<li>` tag.
- Bullet style can be changed using CSS.

### Example

```html
<ul>
    <li>Apple</li>
    <li>Mango</li>
</ul>
```

### Output

- Apple
- Mango

---

## 1.3 Description List (`<dl>`)

### Definition

Used to display terms and their descriptions.

### Syntax

```html
<dl>
    <dt>Term</dt>
    <dd>Description</dd>
</dl>
```

### Key Points

- `<dl>` = Description List
- `<dt>` = Description Term
- `<dd>` = Description Details

### Example

```html
<dl>
    <dt>HTML</dt>
    <dd>Markup Language</dd>
</dl>
```

### Output

HTML

> Markup Language

---

# 2. HTML Attributes

## Definition

Attributes provide additional information about an HTML element.

### Syntax

```html
<tagname attribute="value">Content</tagname>
```

### Example

```html
<a href="https://google.com">Google</a>
```

### Key Points

- Attributes are written inside the opening tag.
- They always have a name and value.
- Values are enclosed inside double quotes.
- One element can have multiple attributes.

### Example

```html
<img src="cat.jpg" alt="Cat" width="300">
```

---

# 3. Anchor Element (`<a>`)

## Definition

The Anchor tag is used to create hyperlinks between web pages.

### Syntax

```html
<a href="URL">Link Text</a>
```

### Common Attributes

- `href`
- `target`
- `title`

### Key Points

- `href` specifies the destination URL.
- `target="_blank"` opens the link in a new tab.
- `target="_self"` opens the link in the same tab (default).
- Can link to webpages, images, files, email addresses, and sections of a webpage.

### Example

```html
<a href="https://google.com">
    Google
</a>
```

### Open in New Tab

```html
<a href="https://google.com" target="_blank">
    Google
</a>
```

---

# 4. Image Element (`<img>`)

## Definition

The `<img>` tag is used to display images on a webpage.

### Syntax

```html
<img src="image.jpg" alt="Description">
```

### Common Attributes

- `src`
- `alt`
- `width`
- `height`

### Key Points

- `<img>` is a Void (Empty) tag.
- `src` specifies the image location.
- `alt` displays alternative text if the image fails to load.
- `width` and `height` control image size.

### Example

```html
<img
    src="dog.jpg"
    alt="Cute Dog"
    width="250">
```

---

# 5. More HTML Tags

## 5.1 Line Break (`<br>`)

### Definition

Moves content to the next line.

### Syntax

```html
<br>
```

### Example

```html
Hello<br>World
```

### Output

Hello

World

---

## 5.2 Horizontal Rule (`<hr>`)

### Definition

Creates a horizontal line.

### Syntax

```html
<hr>
```

---

## 5.3 Bold (`<b>`)

### Definition

Displays text in bold.

### Syntax

```html
<b>Bold Text</b>
```

---

## 5.4 Italic (`<i>`)

### Definition

Displays text in italic.

### Syntax

```html
<i>Italic Text</i>
```

---

## 5.5 Underline (`<u>`)

### Definition

Underlines text.

### Syntax

```html
<u>Underline Text</u>
```

---

## 5.6 Superscript (`<sup>`)

### Definition

Displays text above the normal line.

### Syntax

```html
x<sup>2</sup>
```

### Output

x²

---

## 5.7 Subscript (`<sub>`)

### Definition

Displays text below the normal line.

### Syntax

```html
H<sub>2</sub>O
```

### Output

H₂O

---

# 6. HTML Comments

## Definition

Comments are notes written inside HTML code.

The browser ignores comments and they are **not displayed** on the webpage.

### Syntax

```html
<!-- This is a comment -->
```

### Key Points

- Used to explain code.
- Helps during debugging.
- Improves code readability.
- Not visible in the browser.

### Shortcut

```
Ctrl + /
```

---

# 7. HTML Case Sensitivity

## Definition

HTML is **NOT** case-sensitive.

### Key Points

- `<h1>` and `<H1>` work the same.
- Lowercase tags are recommended.
- XHTML is case-sensitive.

### Good Practice

```html
<h1>Hello</h1>
```

### Avoid

```html
<H1>Hello</H1>
```

---
# Summary

- HTML Lists organize related content.
- Attributes provide additional information to HTML elements.
- `<a>` creates hyperlinks.
- `<img>` displays images.
- HTML comments improve readability but are ignored by browsers.
- HTML is not case-sensitive, but lowercase tags are recommended.