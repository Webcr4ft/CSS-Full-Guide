# What Is CSS Specificity, and the Specificity for Inline, Internal, and External CSS?

CSS **specificity** is the system browsers use to determine which CSS rule should be applied when multiple rules target the same element.

Understanding specificity helps you predict which styles will be used and resolve conflicts between competing CSS rules.

---

# What Is CSS Specificity?

Specificity is a ranking system based on the selectors used in a CSS rule.

When multiple selectors match the same element, the browser compares their specificity values. The selector with the **highest specificity** wins.

For example:

```html
<link rel="stylesheet" href="styles.css">

<p style="color: red;">Red paragraph</p>
<p>Other paragraph</p>
<p>Another paragraph</p>
<p>Yet another paragraph</p>
```

```css
p {
  color: blue;
}
```

### Result

- The **first paragraph** is **red** because it uses an **inline style**.
- The remaining paragraphs are **blue** because they match the `p` selector.

Inline styles have higher specificity than type selectors.

---

# CSS Specificity Hierarchy

From highest to lowest specificity:

1. Inline styles
2. ID selectors
3. Class selectors, attribute selectors, and pseudo-classes
4. Type selectors and pseudo-elements
5. Universal selector (`*`)

---

# 1. Inline Styles

Inline styles have the **highest specificity** because they are written directly on the HTML element.

### Example

```html
<p style="color: red;">
  This text is red.
</p>
```

Specificity:

```text
(1, 0, 0, 0)
```

Because the style is attached directly to the element, it overrides almost every other CSS rule.

---

# 2. ID Selectors

ID selectors have the next highest specificity.

### HTML

```html
<link rel="stylesheet" href="styles.css">

<p id="para">Red paragraph</p>
<p>Other paragraph</p>
<p>Another paragraph</p>
<p>Yet another paragraph</p>
```

### CSS

```css
#para {
  color: red;
}

p {
  color: blue;
}
```

### Result

- The paragraph with `id="para"` is **red**.
- All other paragraphs are **blue**.

This happens because an ID selector is more specific than a type selector.

Specificity:

```text
(0, 1, 0, 0)
```

---

# 3. Class Selectors, Attribute Selectors, and Pseudo-Classes

These selectors have a **moderate level of specificity**.

Examples include:

### Class selector

```css
.container
```

```css
.button
```

### Attribute selector

```css
[type="text"]
```

### Pseudo-class

```css
:hover
```

> **Note:** Pseudo-classes are covered in more detail in later lessons.

---

## Example

### HTML

```html
<link rel="stylesheet" href="styles.css">

<p id="para">Example paragraph</p>

<p class="example-para">
  Other paragraph
</p>

<p class="example-para">
  Another paragraph
</p>

<p>Yet another paragraph</p>
```

### CSS

```css
#para {
  color: red;
}

.example-para {
  color: green;
}

p {
  color: blue;
}
```

### Result

- The paragraph with the ID is **red**.
- Paragraphs with the class are **green**.
- The remaining paragraph is **blue**.

The ID selector overrides both the class selector and the type selector.

Specificity:

```text
(0, 0, 1, 0)
```

---

# 4. Type Selectors and Pseudo-Elements

Type selectors target HTML elements directly.

Examples include:

```css
p
```

```css
div
```

```css
h1
```

Pseudo-elements include:

```css
::before
```

```css
::after
```

These selectors have lower specificity than IDs and classes.

---

## Example

### HTML

```html
<link rel="stylesheet" href="styles.css">

<p id="para">Example paragraph</p>

<p>Other paragraph</p>

<p>Yet another paragraph</p>
```

### CSS

```css
#para {
  color: red;
}

p {
  color: blue;
}
```

### Result

The paragraph with the ID remains **red** because the ID selector has greater specificity.

Specificity:

```text
(0, 0, 0, 1)
```

---

# 5. Universal Selector

The universal selector (`*`) matches every element on the page.

```css
* {
  color: red;
}
```

However, it has the **lowest specificity**.

---

## Example

### HTML

```html
<link rel="stylesheet" href="styles.css">

<p id="para">Example paragraph</p>

<p>Other paragraph</p>

<p>Yet another paragraph</p>
```

### CSS

```css
* {
  color: red;
}

#para {
  color: green;
}

p {
  color: blue;
}
```

### Result

- The first paragraph is **green**.
- The remaining paragraphs are **blue**.

The universal selector loses because both the ID selector and the type selector are more specific.

Specificity:

```text
(0, 0, 0, 0)
```

---

# Understanding Specificity Values

Specificity is represented as a four-part value:

```text
(a, b, c, d)
```

Where:

| Value | Represents |
|--------|------------|
| `a` | Inline styles |
| `b` | ID selectors |
| `c` | Class selectors, attribute selectors, and pseudo-classes |
| `d` | Type selectors and pseudo-elements |

---

# How Each Value Is Calculated

## Inline Styles (`a`)

Each inline style contributes:

```text
1
```

Example:

```text
(1, 0, 0, 0)
```

---

## ID Selectors (`b`)

Each ID contributes:

```text
1
```

Example:

```css
#header
```

Specificity:

```text
(0, 1, 0, 0)
```

---

## Class Selectors (`c`)

Every class, attribute selector, and pseudo-class contributes:

```text
1
```

Example:

```css
.card
```

Specificity:

```text
(0, 0, 1, 0)
```

---

## Type Selectors (`d`)

Each type selector or pseudo-element contributes:

```text
1
```

Example:

```css
p
```

Specificity:

```text
(0, 0, 0, 1)
```

---

## Universal Selector (`*`)

The universal selector contributes:

```text
0
```

It does **not** affect specificity.

---

# Inline CSS

Inline CSS is written directly on an element.

Example:

```html
<p style="color: red;">
  This text is red.
</p>
```

Specificity:

```text
(1, 0, 0, 0)
```

Inline styles override internal and external styles unless `!important` is used.

---

# Internal CSS

Internal CSS is written inside a `<style>` element in the document's `<head>`.

Example:

```html
<head>
  <style>
    #text {
      color: blue;
    }
  </style>
</head>

<body>
  <div id="text">
    This text is blue.
  </div>
</body>
```

The specificity depends on the selectors used.

In this case:

```text
(0, 1, 0, 0)
```

Internal CSS **does not automatically have higher priority** than external CSS. If two rules have the same specificity, whichever appears **later** in the document wins.

---

# External CSS

External CSS is stored in a separate `.css` file and linked using the `<link>` element.

### HTML

```html
<head>
  <link
    rel="stylesheet"
    href="styles.css">
</head>

<body>
  <div class="text">
    This text's color is defined in an external CSS file.
  </div>
</body>
```

### CSS

```css
.text {
  color: purple;
}
```

The specificity is determined by the selector used.

Here, the class selector has a specificity of:

```text
(0, 0, 1, 0)
```

External CSS is generally preferred for larger projects because it keeps styles organized, reusable, and easier to maintain.

---

# Inline vs Internal vs External CSS

| CSS Type | Where It Is Written | Specificity |
|----------|----------------------|-------------|
| Inline CSS | Inside the HTML element | `(1, 0, 0, 0)` |
| Internal CSS | Inside a `<style>` element | Depends on the selector |
| External CSS | Inside a `.css` file | Depends on the selector |

Remember:

- Inline styles always have the highest specificity.
- Internal and external CSS follow the same specificity rules.
- If two rules have equal specificity, the one written later takes precedence.

---

# Key Points

- CSS specificity determines which rule is applied when multiple selectors target the same element.
- Inline styles have the highest specificity.
- ID selectors are more specific than class selectors.
- Class selectors are more specific than type selectors.
- Type selectors are more specific than the universal selector.
- The universal selector has no specificity value.
- Specificity is represented as `(a, b, c, d)`.
- Internal and external CSS use the same specificity rules.
- When specificity is equal, the rule that appears later wins.

---

# Summary

CSS specificity is the browser's method of deciding which CSS rule should be applied when multiple rules match the same element. It is based on the selectors used rather than whether the CSS is internal or external. Understanding the specificity hierarchy helps you write predictable, maintainable styles and avoid unexpected styling conflicts in your projects.
