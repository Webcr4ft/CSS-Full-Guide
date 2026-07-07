# How Does the Cascade Algorithm Work at a High Level?

The **Cascade Algorithm** is the process browsers use to determine which CSS rules should be applied when multiple declarations target the same element.

It ensures that the most appropriate style is chosen by evaluating CSS rules in a specific order.

Rather than selecting styles randomly, the browser follows a series of well-defined steps to resolve conflicts between competing declarations.

---

# The Four Stages of the Cascade Algorithm

The browser resolves conflicting CSS rules by considering the following factors:

1. Relevance
2. Origin and Importance
3. Specificity
4. Order of Appearance

Each stage helps narrow down which declaration should ultimately be applied.

---

# 1. Relevance

The browser first determines whether a CSS rule is relevant to the current element.

A rule is considered relevant only if:

- Its selector matches the element.
- Any associated media queries evaluate to `true`.

## What Are Media Queries?

A media query is a CSS feature that allows styles to be applied based on characteristics of the device or viewport, such as:

- Width
- Height
- Screen orientation
- Resolution

### Example

```css
@media (max-width: 768px) {
  p {
    color: blue;
  }
}
```

The rule above applies only when the viewport width is **768 pixels or smaller**.

---

# 2. Origin and Importance

Once relevant rules have been identified, the browser considers where each rule comes from and whether it has been marked with `!important`.

CSS rules can originate from several sources:

- Browser default styles (User-Agent styles)
- User styles
- Author styles (your stylesheet)

The browser also checks whether a declaration uses the `!important` keyword.

Rules marked with `!important` receive higher priority than normal declarations from the same origin.

---

# 3. Specificity

If multiple relevant rules have the same origin and importance, the browser compares their specificity.

Specificity measures how precise a selector is.

Generally, selectors with greater specificity take precedence over less specific ones.

### Specificity Examples

| Selector | Specificity |
|----------|-------------:|
| `p` | `(0, 0, 0, 1)` |
| `.text` | `(0, 0, 1, 0)` |
| `#header` | `(0, 1, 0, 0)` |
| Inline style | `(1, 0, 0, 0)` |

---

# 4. Order of Appearance

If two rules have:

- The same origin,
- The same importance,
- The same specificity,

then the browser applies the rule that appears **last** in the stylesheet.

### Example

#### HTML

```html
<link rel="stylesheet" href="styles.css">

<p>Example paragraph</p>
```

#### CSS

```css
p {
  color: blue;
}

p {
  color: green;
}
```

### Result

The paragraph displays **green** text.

Although both selectors are identical and have the same specificity, the second rule appears later in the stylesheet, so it overrides the first one.

---

# Cascade Algorithm Flow

The browser resolves CSS conflicts in this order:

```text
Relevance
      ↓
Origin & Importance
      ↓
Specificity
      ↓
Order of Appearance
```

Each step eliminates competing rules until only one declaration remains.

---

# Why the Cascade Algorithm Matters

Understanding the Cascade Algorithm helps you:

- Predict which styles will be applied.
- Resolve conflicting CSS rules.
- Write cleaner and more maintainable stylesheets.
- Reduce unnecessary use of `!important`.
- Better organize CSS for larger projects.

---

# Key Points

- The Cascade Algorithm determines which CSS declaration is applied when multiple rules target the same element.
- It evaluates rules using four stages:
  - Relevance
  - Origin and Importance
  - Specificity
  - Order of Appearance
- Media queries are checked during the relevance stage.
- `!important` affects declaration priority but does not change selector specificity.
- When specificity is equal, the rule written last wins.
- Understanding the cascade makes CSS more predictable and easier to maintain.
