# What Are Some Default Browser Styles Applied to HTML?

When you create an HTML page, browsers automatically apply **default styles** before you write any CSS.

These styles are known as:

* **Default Browser Styles**
* **User-Agent Styles**

Their purpose is to make HTML pages **readable and usable** across different browsers.

> **Note:** Default styles can vary slightly between browsers.

---

# Why Do Browsers Apply Default Styles?

Default browser styles help by:

* Making text readable.
* Giving elements basic spacing.
* Providing default font sizes and weights.
* Making links easy to recognize.
* Styling lists, headings, and other elements automatically.

---

# Common Default Browser Styles

## 1. Heading Elements (`<h1>` - `<h6>`)

Headings are automatically styled with different font sizes and font weights.

### Example

```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
```

### Default Behavior

* `<h1>` → Largest and boldest heading.
* `<h2>` → Slightly smaller.
* `<h3>` → Smaller again.
* Continues down to `<h6>`, which is the smallest.

These headings create a clear **content hierarchy**.

---

# 2. Horizontal Rule (`<hr>`)

The `<hr>` element creates a horizontal line used to separate sections.

### Example

```html
<p>Paragraph 1</p>
<p>Paragraph 2</p>

<hr>

<p>Paragraph 3</p>
<p>Paragraph 4</p>
```

### Default Behavior

Browsers automatically add:

* A thin horizontal line.
* Space above the line.
* Space below the line.

This visually separates content.

---

# 3. Blockquote (`<blockquote>`)

The `<blockquote>` element is used for quotations from another source.

### Example

```html
<p>Paragraph 1</p>
<p>Paragraph 2</p>

<blockquote>
I think, therefore I am. (Rene Descartes)
</blockquote>

<p>Paragraph 3</p>
<p>Paragraph 4</p>
```

### Default Behavior

Browsers usually:

* Indent the quotation.
* Sometimes display it in italics.

This helps distinguish quoted text from normal content.

---

# 4. Anchor Element (`<a>`)

Anchor elements create hyperlinks.

### Example

```html
<p>Paragraph 1</p>
<p>Paragraph 2</p>

<a href="https://freecodecamp.org/">
Visit the freeCodeCamp learn page
</a>

<p>Paragraph 3</p>
<p>Paragraph 4</p>
```

### Default Behavior

Browsers normally display links as:

* Blue text
* Underlined text

This lets users immediately recognize clickable links.

---

# 5. Ordered List (`<ol>`)

Ordered lists display numbered items.

### Example

```html
<ol>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ol>
```

### Default Behavior

Browsers automatically add:

* Numbers
* Indentation
* Spacing between items

---

# 6. Unordered List (`<ul>`)

Unordered lists display bullet points.

### Example

```html
<ul>
  <li>Item</li>
  <li>Another Item</li>
  <li>Yet Another Item</li>
</ul>
```

### Default Behavior

Browsers automatically add:

* Bullet points
* Indentation
* Default spacing

---

# Combined Example

```html
<p>Sample Paragraph</p>

<ol>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ol>

<ul>
  <li>Item</li>
  <li>Another Item</li>
  <li>Yet Another Item</li>
</ul>

<p>Ending Paragraph</p>
```

### Result

Both lists are automatically:

* Indented to the right.
* Given spacing between items.
* Styled with numbers or bullets.

---

# What Do Default Browser Styles Include?

Browsers commonly apply:

* Default margins
* Default padding
* Different heading sizes
* Bold headings
* Blue underlined links
* Indented blockquotes
* Numbered and bulleted lists
* Horizontal rules with spacing

---

# CSS Reset

Since browsers have slightly different default styles, developers often use a **CSS Reset**.

A CSS Reset removes or standardizes browser defaults so every browser starts with the same styling.

This makes it easier to create a consistent website design.

---

# Quick Summary

| HTML Element | Default Browser Style |
|--------------|-----------------------|
| `<h1>`–`<h6>` | Different font sizes and bold text |
| `<hr>` | Horizontal line with spacing |
| `<blockquote>` | Indented quotation |
| `<a>` | Blue and underlined link |
| `<ol>` | Numbered list with indentation |
| `<ul>` | Bulleted list with indentation |

---

# Key Takeaways

* Browsers automatically apply **default (user-agent) styles**.
* These styles improve readability before CSS is added.
* Common elements with default styling include headings, links, blockquotes, horizontal rules, and lists.
* Default styles may differ slightly between browsers.
* A **CSS Reset** is commonly used to remove or standardize these default styles for consistent web design.
