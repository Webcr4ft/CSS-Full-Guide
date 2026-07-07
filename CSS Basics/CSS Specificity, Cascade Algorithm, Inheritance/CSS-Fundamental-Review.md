# CSS Fundamentals Review

## Table of Contents

1. CSS Basics
2. Inline, Internal, and External CSS
3. Working With `width` and `height`
4. CSS Combinators
5. Inline, Block, and Inline-Block Elements
6. Margin and Padding
7. CSS Specificity
8. Cascade Algorithm
9. CSS Inheritance

---

# CSS Basics

## What is CSS?

**Cascading Style Sheets (CSS)** is a stylesheet language used to style HTML documents. It controls the appearance of web pages, including colors, layouts, spacing, fonts, backgrounds, and much more.

---

## Basic Anatomy of a CSS Rule

A CSS rule consists of two main parts:

- **Selector** – Targets the HTML element(s) to style.
- **Declaration Block** – Contains one or more property-value pairs.

### Syntax

```css
selector {
  property: value;
}
```

Example:

```css
p {
  color: blue;
}
```

---

## `meta name="viewport"`

The viewport meta tag tells the browser how to control a page's dimensions and scaling on different devices, especially smartphones and tablets.

Example:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

---

## Default Browser Styles

Browsers automatically apply default styles to HTML elements.

Examples include:

- Default margins
- Default padding
- Font sizes
- Heading styles
- List indentation

These defaults often differ slightly between browsers.

---

# Inline, Internal, and External CSS

## Inline CSS

Inline CSS is written directly inside an HTML element using the `style` attribute.

Example:

```html
<p style="color: red;">This is a red paragraph.</p>
```

### Advantages

- Quick styling
- Useful for testing

### Disadvantages

- Hard to maintain
- Breaks separation of concerns
- Not recommended for large projects

---

## Internal CSS

Internal CSS is written inside a `<style>` element within the `<head>` section.

Example:

```html
<head>
  <style>
    p {
      color: blue;
    }
  </style>
</head>
```

### Best Used For

- Small projects
- Demonstrations
- Short examples

---

## External CSS

External CSS is stored in a separate `.css` file and linked using the `<link>` element.

Example:

```html
<link rel="stylesheet" href="styles.css">
```

### Advantages

- Easy maintenance
- Reusable styles
- Cleaner HTML
- Best practice for most websites

---

# Working With `width` and `height`

## `width`

Defines the width of an element.

```css
div {
  width: 300px;
}
```

Default value:

```css
width: auto;
```

The browser determines the width based on:

- Content
- Parent element
- Display type

---

## `min-width`

Defines the minimum width an element can become.

```css
div {
  min-width: 200px;
}
```

---

## `max-width`

Defines the maximum width an element can reach.

```css
div {
  max-width: 800px;
}
```

---

## `height`

Defines the height of an element.

```css
div {
  height: 250px;
}
```

Default:

```css
height: auto;
```

The height grows automatically to fit its content.

---

## `min-height`

Sets the minimum height.

```css
div {
  min-height: 150px;
}
```

---

## `max-height`

Sets the maximum height.

```css
div {
  max-height: 500px;
}
```

---

# CSS Combinators

CSS combinators define relationships between selectors.

---

## Descendant Combinator (Space)

Targets all matching descendants.

HTML:

```html
<ul>
  <li>Example item one</li>
  <li>Example item two</li>
  <li>Example item three</li>
</ul>
```

CSS:

```css
ul li {
  background-color: yellow;
}
```

All `li` elements inside the `ul` are selected.

---

## Child Combinator (`>`)

Targets only direct children.

HTML:

```html
<div class="container">
  <p>This will get styled.</p>

  <div>
    <p>This will not get styled.</p>
  </div>
</div>
```

CSS:

```css
.container > p {
  background-color: black;
  color: white;
}
```

Only the first paragraph is selected.

---

## Next-Sibling Combinator (`+`)

Targets the immediately following sibling.

HTML:

```html
<h2>I am a sub heading</h2>

<p>This paragraph gets styled.</p>
```

CSS:

```css
h2 + p {
  background-color: red;
}
```

Only the paragraph immediately after the `h2` is selected.

---

## Subsequent-Sibling Combinator (`~`)

Targets every matching sibling that comes after the first element.

HTML:

```html
<div class="container">
  <p>This will not get styled.</p>

  <ul>
    <li>Example item one</li>
    <li>Example item two</li>
    <li>Example item three</li>
  </ul>

  <p>This will get styled.</p>
</div>

<p>This will not get styled.</p>
```

CSS:

```css
ul ~ p {
  background-color: green;
}
```

Only the paragraph sharing the same parent as the `ul` is selected.

---

# Inline, Block, and Inline-Block Elements

## Inline Elements

Inline elements:

- Only use the space they need
- Do not start on a new line

Common examples:

- `span`
- `a`
- `img`

---

## Block Elements

Block elements:

- Start on a new line
- Occupy the full available width

Common examples:

- `div`
- `p`
- `section`

---

## Inline-Block Elements

Elements with:

```css
display: inline-block;
```

They:

- Stay on the same line
- Can have custom width
- Can have custom height

Example:

```css
button {
  display: inline-block;
  width: 200px;
  height: 50px;
}
```

---

# Margin and Padding

## `margin`

Creates space **outside** an element.

```css
div {
  margin: 20px;
}
```

---

## `padding`

Creates space **inside** an element.

```css
div {
  padding: 20px;
}
```

---

## Margin Shorthand

One value:

```css
margin: 20px;
```

Applies to all sides.

---

Two values:

```css
margin: 20px 10px;
```

- Top & Bottom → 20px
- Left & Right → 10px

---

Three values:

```css
margin: 20px 10px 30px;
```

- Top → 20px
- Left & Right → 10px
- Bottom → 30px

---

Four values:

```css
margin: 20px 15px 30px 10px;
```

- Top
- Right
- Bottom
- Left

(clockwise)

---

## Padding Shorthand

One value:

```css
padding: 20px;
```

---

Two values:

```css
padding: 20px 10px;
```

---

Three values:

```css
padding: 20px 10px 30px;
```

---

Four values:

```css
padding: 20px 15px 30px 10px;
```

---

# CSS Specificity

Specificity determines which CSS rule is applied when multiple rules target the same element.

---

## Inline CSS

Highest specificity.

Specificity value:

```text
(1, 0, 0, 0)
```

Example:

```html
<p style="color:red;">Hello</p>
```

---

## Internal CSS

Internal styles use the same specificity rules as external CSS.

Their priority depends entirely on the selectors used.

---

## External CSS

External styles also depend on selector specificity.

If two selectors have equal specificity, the one written later wins.

---

## Universal Selector (`*`)

Matches every element.

Example:

```css
* {
  margin: 0;
  padding: 0;
}
```

Specificity:

```text
(0, 0, 0, 0)
```

Lowest specificity.

---

## Type Selectors

Select by tag name.

Example:

```css
p {
  color: blue;
}
```

Specificity:

```text
(0, 0, 0, 1)
```

---

## Class Selectors (`.`)

Select by class.

Example:

```css
.card {
  border: 1px solid black;
}
```

Specificity:

```text
(0, 0, 1, 0)
```

---

## ID Selectors (`#`)

Select by ID.

Example:

```css
#header {
  background: black;
}
```

Specificity:

```text
(0, 1, 0, 0)
```

Higher than classes and type selectors.

---

## `!important`

Forces a declaration to take priority over normal CSS rules.

Example:

```css
p {
  color: blue !important;
}
```

Use sparingly because it makes CSS harder to maintain.

---

# Cascade Algorithm

The cascade determines which CSS declaration is applied when multiple rules match the same element.

The browser considers:

1. Importance (`!important`)
2. Origin
3. Specificity
4. Source order

When specificity is equal, the rule written later wins.

---

# CSS Inheritance

Inheritance allows child elements to receive certain styles from their parent elements automatically.

Example:

```css
body {
  color: navy;
}
```

HTML:

```html
<body>
  <h1>Heading</h1>
  <p>Paragraph</p>
</body>
```

Both the heading and paragraph inherit the text color unless another rule overrides it.

Common inherited properties include:

- `color`
- `font-family`
- `font-size`
- `line-height`

Properties like `margin`, `padding`, `border`, and `width` are **not** inherited by default.

---

# Summary

This review covered:

- CSS basics
- CSS rule syntax
- Viewport meta tag
- Browser default styles
- Inline, internal, and external CSS
- Width and height properties
- CSS combinators
- Display types
- Margin and padding
- CSS specificity
- Universal, type, class, and ID selectors
- `!important`
- Cascade algorithm
- CSS inheritance
