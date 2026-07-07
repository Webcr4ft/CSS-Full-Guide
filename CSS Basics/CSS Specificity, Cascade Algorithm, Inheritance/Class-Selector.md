# What Is the Specificity for Class Selectors?

Class selectors are a fundamental part of CSS that allow developers to target **multiple elements** sharing the same `class` attribute and apply consistent styling.

They are highly versatile and are commonly used to reuse styles across different parts of a website.

A class selector is written using a period (`.`) followed by the class name.

## Basic Example

### HTML

```html
<link rel="stylesheet" href="styles.css">

<p class="highlight">Example paragraph</p>
```

### CSS

```css
.highlight {
  color: green;
}
```

### Result

Any element with the class `highlight` will display **green** text.

---

# Specificity of Class Selectors

Class selectors have a **higher specificity** than type selectors but a **lower specificity** than ID selectors and inline styles.

**Specificity Value:**

```text
(0, 0, 1, 0)
```

Because of this, class selectors:

- Override type selectors.
- Can be overridden by ID selectors.
- Can also be overridden by inline styles.

---

# Combining Class Selectors with Type Selectors

Class selectors can be combined with other selectors to create more specific styling rules.

### HTML

```html
<link rel="stylesheet" href="styles.css">

<p class="bold-text">Example paragraph</p>
<p class="bold-text">Example paragraph</p>
<p>Another paragraph</p>
<p>Yet another paragraph</p>
```

### CSS

```css
p.bold-text {
  font-weight: bold;
}
```

---

# How This Works

The selector:

```css
p.bold-text
```

matches only `<p>` elements that have the class `bold-text`.

As a result:

- The first two paragraphs become **bold**.
- The remaining paragraphs remain unchanged because they do not have the `bold-text` class.

---

# Specificity Comparison

| Selector | Specificity |
|----------|-------------:|
| `p` | `(0, 0, 0, 1)` |
| `.highlight` | `(0, 0, 1, 0)` |
| `p.highlight` | `(0, 0, 1, 1)` |
| `#header` | `(0, 1, 0, 0)` |
| Inline style | `(1, 0, 0, 0)` |

---

# Key Points

- Class selectors are written using a period (`.`) followed by the class name.
- They can target multiple elements that share the same class.
- Class selectors have a specificity of **`(0, 0, 1, 0)`**.
- They override type selectors but can be overridden by ID selectors and inline styles.
- Class selectors can be combined with type selectors to create more specific CSS rules.
- Using classes promotes reusable, maintainable, and consistent styling across a website.
