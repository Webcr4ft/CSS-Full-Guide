# What Is the `!important` Keyword, and What Are the Best Practices for Using It?

The `!important` keyword in CSS gives a style declaration the **highest priority**.

When applied to a CSS property, it instructs the browser to use that declaration even when other rules with higher specificity would normally win.

It is commonly used to override existing styles, but it should be used **carefully and sparingly**.

---

# Basic Example

Suppose you have the following HTML:

### HTML

```html
<p class="para" style="background-color: lightblue; color: black;">
  This is a paragraph.
</p>
```

The paragraph has inline styles that set:

- Background color to `lightblue`
- Text color to `black`

---

# CSS Without `!important`

### CSS

```css
.para {
  background-color: black;
  color: white;
}
```

### Result

The paragraph **does not** use the black background or white text.

This is because **inline styles have a higher priority** than class selectors.

---

# Using the `!important` Keyword

You can force the browser to apply the class styles by adding `!important`.

### CSS

```css
.para {
  background-color: black !important;
  color: white !important;
}
```

### Result

The paragraph now displays:

- A **black** background.
- **White** text.

The `!important` keyword overrides the conflicting inline styles.

---

# Syntax

The `!important` keyword is placed **after the property value** and **before the semicolon**.

```css
selector {
  property: value !important;
}
```

### Example

```css
h1 {
  color: blue !important;
}
```

---

# Does `!important` Change Specificity?

No.

The `!important` keyword **does not increase the specificity** of a selector.

Instead, it changes the order in which conflicting declarations are considered by the browser.

Even a selector with lower specificity can override a more specific selector if its declaration includes `!important`.

---

# Common Use Cases

Using `!important` can be appropriate in situations such as:

- Overriding inline styles.
- Overriding styles from third-party libraries or CSS frameworks.
- Applying utility classes that must always take precedence.
- Handling rare edge cases where changing the original CSS is not possible.

---

# Why Overusing `!important` Is Discouraged

Although `!important` is useful, excessive use can create several problems:

- Makes CSS harder to maintain.
- Breaks the natural cascade.
- Makes debugging style conflicts more difficult.
- Encourages writing increasingly specific or forceful rules.

For these reasons, it should only be used when there is a clear need.

---

# Best Practices

- Use `!important` only as a last resort.
- Prefer improving selector specificity instead of forcing styles.
- Avoid using it throughout an entire stylesheet.
- Use it when overriding third-party CSS that cannot be modified.
- Keep your styles organized to minimize the need for `!important`.

---

# Priority Comparison

| Rule | Priority |
|------|---------:|
| Type selector | Low |
| Class selector | Higher |
| ID selector | Even higher |
| Inline style | Very high |
| `!important` declaration | Highest |

---

# Key Points

- `!important` gives a CSS declaration the highest priority.
- It overrides conflicting declarations, including inline styles.
- It **does not** change the selector's specificity.
- It is useful for overriding third-party styles and unavoidable conflicts.
- Overusing `!important` can make CSS difficult to maintain and debug.
- Use it sparingly and only when a better solution is not available.
