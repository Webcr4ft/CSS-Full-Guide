# What Is the Specificity for ID Selectors?

ID selectors are among the most powerful selectors in CSS. They allow developers to target **a single, unique element** by using its `id` attribute.

Because an ID should be unique within an HTML document, ID selectors are ideal for styling elements that require special or one-of-a-kind styles.

An ID selector is written using a hash (`#`) followed by the ID name.

## Basic Example

### HTML

```html
<link rel="stylesheet" href="styles.css">

<p id="unique">Example paragraph</p>
<p>Another paragraph</p>
<p>Yet another paragraph</p>
```

### CSS

```css
#unique {
  color: purple;
}
```

### Result

Only the element with the ID `unique` will display **purple** text.

The other paragraph elements remain unaffected because they do not have the matching ID.

---

# Specificity of ID Selectors

ID selectors have a **very high specificity**.

**Specificity Value:**

```text
(0, 1, 0, 0)
```

This means that ID selectors:

- Override type selectors.
- Override class selectors.
- Can still be overridden by inline styles.

Because of their high specificity, ID selectors should be used carefully to avoid making styles difficult to override later.

---

# Example: ID Selector Overrides a Class Selector

### HTML

```html
<p id="unique" class="highlight">
  Example paragraph
</p>
```

### CSS

```css
.highlight {
  color: green;
}

#unique {
  color: purple;
}
```

### Result

Although the paragraph has the `highlight` class, the text appears **purple** because the ID selector has a higher specificity than the class selector.

---

# Specificity Comparison

| Selector | Specificity |
|----------|-------------:|
| `p` | `(0, 0, 0, 1)` |
| `.highlight` | `(0, 0, 1, 0)` |
| `#unique` | `(0, 1, 0, 0)` |
| Inline style | `(1, 0, 0, 0)` |

---

# Best Practices

- Use IDs only for elements that are unique within the page.
- Avoid assigning the same ID to multiple elements.
- Prefer class selectors for reusable styles.
- Reserve ID selectors for unique components or JavaScript interactions when appropriate.

---

# Key Points

- ID selectors are written using a hash (`#`) followed by the ID name.
- An ID should be unique within an HTML document.
- ID selectors have a specificity of **`(0, 1, 0, 0)`**.
- They override both type and class selectors.
- Inline styles have a higher specificity and can override ID selector rules.
- Use ID selectors sparingly to keep your CSS easier to maintain.
