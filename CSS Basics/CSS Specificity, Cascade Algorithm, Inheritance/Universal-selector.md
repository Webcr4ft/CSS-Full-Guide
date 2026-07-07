# What Is the Universal Selector, and What Is Its Specificity?

The **universal selector (`*`)** is a special CSS selector that matches **every element** in an HTML document.

It is commonly used to apply the same styles to all elements, making it useful for **CSS resets** and **normalizing browser styles**.

The universal selector can target:

- Every element in the document.
- Every element within a specific context.

---

# Basic Example

### HTML

```html
<link rel="stylesheet" href="styles.css">

<h1>Heading element</h1>
<p>Example paragraph element</p>
```

### CSS

```css
* {
  margin: 0;
  padding: 0;
}
```

---

## Explanation

In this example:

- The `*` selector targets **every HTML element**.
- Every element has its `margin` set to `0`.
- Every element has its `padding` set to `0`.

This technique is widely used as a **CSS reset**, ensuring that browsers start with consistent spacing before custom styles are added.

---

# Specificity of the Universal Selector

The universal selector has the **lowest specificity** of all CSS selectors.

Its specificity value is:

```text
(0, 0, 0, 0)
```

Because of this, **any other selector** will override it when both target the same element.

Selectors with higher specificity include:

- Type selectors (`p`, `h1`, `div`)
- Class selectors (`.card`)
- ID selectors (`#header`)
- Inline styles

---

# Example of Specificity

### HTML

```html
<head>
  <style>
    * {
      color: blue;
    }

    p {
      color: red;
    }

    .highlight {
      color: green;
    }

    #unique {
      color: purple;
    }
  </style>
</head>

<body>
  <p id="unique" class="highlight">
    This text has multiple styles applied.
  </p>
</body>
```

---

# How CSS Resolves the Styles

The paragraph matches **all four selectors**:

1. Universal selector (`*`)
2. Type selector (`p`)
3. Class selector (`.highlight`)
4. ID selector (`#unique`)

CSS compares their specificity to determine which style wins.

| Selector | Color | Specificity |
|----------|-------|-------------|
| `*` | Blue | `(0, 0, 0, 0)` |
| `p` | Red | `(0, 0, 0, 1)` |
| `.highlight` | Green | `(0, 0, 1, 0)` |
| `#unique` | Purple | `(0, 1, 0, 0)` |

---

# Order of Precedence

From **lowest** to **highest** specificity:

```text
*            → Blue
↓
p            → Red
↓
.highlight   → Green
↓
#unique      → Purple (Final Applied Color)
```

The paragraph's text is displayed in **purple** because the **ID selector (`#unique`)** has the highest specificity among all the matching selectors.

---

# Key Points

- `*` matches **every element** in the document.
- It is commonly used for **CSS resets** and **normalizing default browser styles**.
- The universal selector has the **lowest specificity**: `(0, 0, 0, 0)`.
- Any type, class, ID, or inline style can override the styles applied by the universal selector.
- When multiple selectors match the same element, the selector with the **highest specificity** determines the final style.
