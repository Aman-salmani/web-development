# 🧱 HTML Level 3 — Tables & Forms

## 📑 Table of Contents

- [1. Tables in HTML](#1-tables-in-html)
- [2. Semantics in Tables](#2-semantics-in-tables)
- [3. Colspan & Rowspan](#3-colspan--rowspan)
- [4. Forms in HTML](#4-forms-in-html)
- [5. `<input>` — Form Element](#5-input--form-element)
- [6. Placeholders & Labels](#6-placeholders--labels)
- [7. `<button>` Element](#7-button-element)
- [8. `name` Attribute](#8-name-attribute)
- [9. Checkbox Input](#9-checkbox-input)
- [10. Radio Input](#10-radio-input)
- [11. `<select>` — Dropdown](#11-select--dropdown)
- [12. Range Input](#12-range-input)
- [13. `<textarea>`](#13-textarea)
- [14. Best Practices](#14-best-practices)
- [15. Common Mistakes](#15-common-mistakes)
- [16. Cheat Sheet](#16-cheat-sheet)

---

## 1. Tables in HTML

A **table** organizes data into rows and columns using `<table>`, `<tr>` (row), `<th>` (header cell), and `<td>` (data cell).

```html
<table border="1">
  <tr>
    <th>Name</th>
    <th>Age</th>
    <th>City</th>
  </tr>
  <tr>
    <td>Aman</td>
    <td>21</td>
    <td>Kashipur</td>
  </tr>
  <tr>
    <td>Riya</td>
    <td>22</td>
    <td>Delhi</td>
  </tr>
</table>
```

**Key points**
- `<table>` — wraps the entire table
- `<tr>` — table row
- `<th>` — header cell (bold, centered by default)
- `<td>` — standard data cell
- `border` attribute is legacy — use CSS (`border-collapse`, `border`) instead

---

## 2. Semantics in Tables

Semantic table elements describe the *role* of each section, improving accessibility and structure — especially for screen readers.

| Tag | Purpose |
|---|---|
| `<thead>` | Groups the header row(s) |
| `<tbody>` | Groups the main data rows |
| `<tfoot>` | Groups footer/summary rows |
| `<caption>` | Adds a title/description to the table |

```html
<table>
  <caption>Employee Records</caption>

  <thead>
    <tr>
      <th>Name</th>
      <th>Role</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>Aman</td>
      <td>Developer</td>
    </tr>
  </tbody>

  <tfoot>
    <tr>
      <td colspan="2">Total: 1 Employee</td>
    </tr>
  </tfoot>
</table>
```

**Why it matters**
- Screen readers announce header vs. body context correctly
- Allows independent styling of header/body/footer via CSS
- `<caption>` gives the table an accessible title (should be the first child of `<table>`)

---

## 3. Colspan & Rowspan

Used to merge cells **across columns or rows**.

### `colspan` — merge across columns

```html
<table border="1">
  <tr>
    <td colspan="2">Merged across 2 columns</td>
  </tr>
  <tr>
    <td>Cell 1</td>
    <td>Cell 2</td>
  </tr>
</table>
```

### `rowspan` — merge across rows

```html
<table border="1">
  <tr>
    <td rowspan="2">Merged across 2 rows</td>
    <td>Row 1</td>
  </tr>
  <tr>
    <td>Row 2</td>
  </tr>
</table>
```

**Key points**
- `colspan="n"` — cell spans `n` columns
- `rowspan="n"` — cell spans `n` rows
- Both attributes go on `<td>` or `<th>`
- Commonly used for totals, grouped headers, and summary rows

---

## 4. Forms in HTML

A `<form>` collects user input and sends it to a server for processing.

```html
<form action="/submit" method="POST">
  <!-- form fields go here -->
</form>
```

| Attribute | Purpose |
|---|---|
| `action` | URL the form data is sent to |
| `method` | HTTP method — `GET` (visible in URL) or `POST` (in request body) |
| `autocomplete` | Enables/disables browser autofill |

---

## 5. `<input>` — Form Element

The most versatile form element — its behavior changes based on the `type` attribute.

```html
<input type="text" name="username">
<input type="email" name="email">
<input type="password" name="password">
<input type="date" name="dob">
<input type="number" name="age">
```

| Type | Purpose |
|---|---|
| `text` | Single-line text input |
| `email` | Validates email format |
| `password` | Masks input characters |
| `number` | Numeric input with spin controls |
| `date` | Date picker |
| `file` | File upload |

---

## 6. Placeholders & Labels

### `placeholder`
Shows hint text inside an empty input — disappears once the user starts typing. **Not a substitute for a label.**

```html
<input type="text" placeholder="Enter your name">
```

### `<label>`
Describes an input for both sighted users and screen readers. Clicking the label focuses the linked input.

```html
<label for="email">Email:</label>
<input type="email" id="email" name="email">
```

**Key points**
- `label`'s `for` attribute must match the input's `id`
- Improves accessibility and usability (larger clickable area)
- Always pair inputs with `<label>` — placeholders alone are not accessible

---

## 7. `<button>` Element

Represents a clickable button, commonly used inside forms.

```html
<button type="submit">Submit</button>
<button type="reset">Reset</button>
<button type="button">Click Me</button>
```

| Type | Behavior |
|---|---|
| `submit` | Submits the form (default type) |
| `reset` | Clears all form fields |
| `button` | No default action — used with JavaScript |

> 💡 Always specify `type` explicitly — inside a `<form>`, a button defaults to `submit`, which can cause accidental submissions.

---

## 8. `name` Attribute

The `name` attribute identifies form fields when data is submitted — it's the **key** in the key-value pair sent to the server.

```html
<input type="text" name="username">
```

Submitting this sends: `username=<value>`

**Key points**
- Required for a field's data to be included in form submission
- `id` is for CSS/JS targeting; `name` is for form submission — they serve different purposes
- Radio buttons in the same group must share the same `name` to work together

---

## 9. Checkbox Input

Allows selecting **multiple options independently**.

```html
<label><input type="checkbox" name="hobby" value="reading"> Reading</label>
<label><input type="checkbox" name="hobby" value="coding"> Coding</label>
<label><input type="checkbox" name="hobby" value="sports" checked> Sports</label>
```

**Key points**
- Each checkbox toggles independently
- `checked` pre-selects an option
- Multiple checkboxes can share the same `name` to submit as a group

---

## 10. Radio Input

Allows selecting **only one option** from a group.

```html
<label><input type="radio" name="gender" value="male"> Male</label>
<label><input type="radio" name="gender" value="female"> Female</label>
<label><input type="radio" name="gender" value="other"> Other</label>
```

**Key points**
- All radio buttons in a group **must share the same `name`**
- Selecting one automatically deselects the others in that group
- Use `checked` to pre-select a default option

---

## 11. `<select>` — Dropdown

Creates a dropdown list of options.

```html
<label for="country">Country:</label>
<select id="country" name="country">
  <option value="in">India</option>
  <option value="us">USA</option>
  <option value="uk">UK</option>
</select>
```

**Key points**
- `<option>` defines each choice; `value` is what gets submitted
- Add `selected` to an `<option>` to set a default
- Add `multiple` to `<select>` to allow multiple selections

---

## 12. Range Input

A slider for selecting a numeric value within a defined range.

```html
<label for="volume">Volume:</label>
<input type="range" id="volume" name="volume" min="0" max="100" step="5">
```

| Attribute | Purpose |
|---|---|
| `min` | Minimum value |
| `max` | Maximum value |
| `step` | Increment between values |
| `value` | Default position |

---

## 13. `<textarea>`

A multi-line text input for longer content like comments or messages.

```html
<label for="message">Message:</label>
<textarea id="message" name="message" rows="4" cols="40" placeholder="Type your message..."></textarea>
```

**Key points**
- `rows` / `cols` control default visible size
- Unlike `<input>`, content goes **between** the opening and closing tags, not in a `value` attribute
- Resizable by the user via CSS `resize` property (default: both directions)

---

## 14. Best Practices

- ✔ Always pair inputs with `<label for="...">` for accessibility.
- ✔ Use semantic table structure (`<thead>`, `<tbody>`, `<tfoot>`) for data tables.
- ✔ Explicitly set `type="button"` for non-submit buttons inside forms.
- ✔ Give every submittable field a meaningful `name`.
- ✔ Use `placeholder` as a hint, never as a replacement for `<label>`.
- ✔ Group related radio buttons with the same `name`.
- ✔ Use `<caption>` to describe what a table represents.

---

## 15. Common Mistakes

```html
<!-- ❌ Radio buttons with different names — all can be selected -->
<input type="radio" name="gender1" value="male">
<input type="radio" name="gender2" value="female">

<!-- ✅ Same name — mutually exclusive -->
<input type="radio" name="gender" value="male">
<input type="radio" name="gender" value="female">
```

```html
<!-- ❌ Input with no label — inaccessible -->
<input type="text" placeholder="Name">

<!-- ✅ Input with proper label -->
<label for="name">Name:</label>
<input type="text" id="name" placeholder="Enter your name">
```

```html
<!-- ❌ Button inside a form with no explicit type — submits accidentally -->
<button onclick="doSomething()">Click</button>

<!-- ✅ Explicit type -->
<button type="button" onclick="doSomething()">Click</button>
```

---

## 16. Cheat Sheet

**Table tags**
```html
<table> <caption> <thead> <tbody> <tfoot> <tr> <th> <td>
```

**Merging cells**
```html
colspan="n"   → merges n columns
rowspan="n"   → merges n rows
```

**Form tags**
```html
<form> <input> <label> <button> <select> <option> <textarea>
```

**Input types**
```html
text | email | password | number | date | file
checkbox | radio | range | submit | reset | button
```

**Key attributes**
```html
name        → identifies data on submission
id          → links <label for="">
placeholder → hint text (not a label replacement)
checked     → pre-selects checkbox/radio
selected    → pre-selects <option>
min/max/step → constraints for range/number
```
