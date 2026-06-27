# What Is the Basic Anatomy of a CSS Rule?

CSS is responsible for the **styles** of a web page. Every style you see on a website is created using **CSS rules**.

---

# A CSS Rule Has Two Main Parts

A CSS rule consists of:

* **Selector**
* **Declaration Block**

### Basic Syntax

```css
selector {
  property: value;
}
```

---

# 1. Selector

A **selector** is used to target specific HTML elements that you want to style.

## Common Selectors

* Type Selector → `p`
* Class Selector → `.class-name`
* ID Selector → `#id-name`

---

# 2. Declaration Block

The code inside the curly braces `{}` is called the **declaration block**.

```css
p {
  color: blue;
}
```

A declaration block contains one or more **declarations**.

---

# Declaration Structure

Each declaration has:

* **Property**
* **Value**

```css
property: value;
```

### Example

```css
background-color: purple;
```

* **Property:** `background-color`
* **Value:** `purple`

---

# CSS Syntax Rules

Every declaration follows this format:

```css
property: value;
```

Remember:

* `:` comes after the property.
* `;` comes after the value.

Example:

```css
color: blue;
font-size: 18px;
background-color: purple;
```

---

# Example 1: Styling Paragraphs

### HTML

```html
<link rel="stylesheet" href="styles.css">

<h1>Learning about CSS</h1>

<p>Example paragraph element</p>

<p>Another example paragraph element</p>
```

### CSS

```css
p {
  color: blue;
}
```

### Result

* The **type selector** `p` targets **all** paragraph elements.
* Every paragraph's text becomes **blue**.

---

# Styling Multiple Selectors

You can apply the same styles to multiple selectors by separating them with commas `,`.

### HTML

```html
<link rel="stylesheet" href="styles.css">

<h1 id="title">Example heading</h1>

<h2 class="subheading">Example subheading</h2>

<p>This paragraph is not affected by the selector.</p>
```

### CSS

```css
#title,
.subheading {
  color: navy;
}
```

---

# Understanding the Selectors

## ID Selector

```css
#title
```

* Starts with `#`
* Targets an element with:

```html
id="title"
```

---

## Class Selector

```css
.subheading
```

* Starts with `.`
* Targets every element with:

```html
class="subheading"
```

---

# Result

Both selectors receive the same style:

```css
color: navy;
```

So:

* `#title` → Navy text
* `.subheading` → Navy text
* `<p>` → Unchanged

---

# Quick Summary

| Term | Meaning |
|------|---------|
| `selector` | Chooses which HTML element to style |
| `{}` | Declaration block |
| `property` | What you want to change |
| `value` | The style you apply |
| `:` | Separates property from value |
| `;` | Ends each declaration |
| `#` | ID selector |
| `.` | Class selector |
| `,` | Styles multiple selectors together |

---

# Key Takeaways

* Every CSS rule has a **selector** and a **declaration block**.
* A declaration contains a **property** and a **value**.
* Use `#` for **ID selectors**.
* Use `.` for **class selectors**.
* Use `,` to style multiple selectors at once.
* Always end declarations with a semicolon `;`.
