# What Is the Specificity for Type Selectors?

Type selectors, also known as **element selectors**, target HTML elements based on their **tag name**.

They are one of the most fundamental CSS selectors and allow you to apply styles to **every instance** of a specific HTML element.

A type selector is written using only the name of the HTML tag you want to style.

## Basic Example

### HTML

```html
<link rel="stylesheet" href="styles.css">

<p>Paragraph one</p>
<p>Paragraph two</p>
<p>Paragraph three</p>
```

### CSS

```css
p {
  color: blue;
}
```

### Result

All `<p>` elements on the page will display **blue** text.

---

# Specificity of Type Selectors

Type selectors have a relatively **low specificity**.

**Specificity Value:**

```text
(0, 0, 0, 1)
```

Because of this low specificity, type selectors can easily be overridden by selectors with higher specificity, such as:

- Class selectors (`.class`)
- ID selectors (`#id`)
- Inline styles (`style=""`)

However, if no higher-specificity rule exists, the type selector's styles will be applied normally.

---

# Example: Class Selector Overrides a Type Selector

Suppose you have the following HTML:

```html
<p class="para">I am a paragraph</p>
<p class="para">Here is another paragraph</p>
```

Both paragraphs have the class `para`.

### CSS

```css
p {
  color: blue;
}

.para {
  color: red;
}
```

---

# Why Does This Happen?

The `p` selector gives every paragraph a **blue** text color.

The `.para` selector targets elements with the `para` class and sets their text color to **red**.

Since **class selectors have a higher specificity than type selectors**, the class rule overrides the type selector.

As a result, both paragraphs appear **red** instead of **blue**.

---

# Specificity Comparison

| Selector | Specificity |
|----------|-------------:|
| `p` | `(0, 0, 0, 1)` |
| `.para` | `(0, 0, 1, 0)` |
| `#header` | `(0, 1, 0, 0)` |
| Inline style | `(1, 0, 0, 0)` |

---

# Key Points

- Type selectors target elements by their HTML tag name.
- They are written using only the element name (such as `p`, `h1`, or `div`).
- Type selectors have a specificity of **`(0, 0, 0, 1)`**.
- Class selectors, ID selectors, and inline styles have higher specificity and will override type selector rules when they target the same element.
- Type selectors are ideal for applying consistent styles to all elements of a particular type.
