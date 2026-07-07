# How Does Inheritance Work with CSS at a High Level?

**Inheritance** is one of the core concepts of CSS. It describes how certain CSS properties are automatically passed from a **parent element** to its **child elements**.

Think of inheritance like a family tree. Just as children can inherit characteristics from their parents, child HTML elements can inherit specific CSS properties from their parent elements.

This behavior helps you write cleaner, more consistent, and more maintainable styles.

---

# Parent and Child Elements

HTML elements are organized in a hierarchy known as the **Document Object Model (DOM)**.

For example:

```html
<div>
  Parent element
  <p>Child element</p>
</div>
```

In this example:

- The `<div>` is the **parent** element.
- The `<p>` is the **child** element.

Some CSS properties applied to the parent are automatically inherited by the child.

---

# Properties That Are Inherited

Not every CSS property is inherited by default.

Some commonly inherited properties include:

- `color`
- `font-family`
- `font-size`
- `font-style`
- `font-weight`
- `line-height`
- `text-align`
- `visibility`

When these properties are applied to a parent element, child elements automatically receive the same values unless they define their own.

---

# Example: Inheriting the `color` Property

### HTML

```html
<div style="color: blue;">
  This is the parent element.

  <p>
    This is the child element inheriting the color.
  </p>
</div>
```

### Result

Both the parent `<div>` and the child `<p>` display **blue** text because the `color` property is inherited.

---

# Properties That Are Not Inherited

Some CSS properties are **not inherited automatically**.

Common examples include:

- `margin`
- `padding`
- `border`
- `background`
- `width`
- `height`
- `display`

If these properties are applied to a parent element, child elements will **not** automatically receive them.

---

# Using the `inherit` Keyword

You can force a child element to inherit a property by using the `inherit` keyword.

This is especially useful for properties that are not inherited by default.

### HTML

```html
<div style="padding: 20px;">
  This is the parent element with padding.

  <p style="padding: inherit;">
    This child inherits the parent's padding.
  </p>
</div>
```

### Result

The `<p>` element inherits the `20px` padding from its parent because the `inherit` keyword explicitly tells it to do so.

---

# Why Is Inheritance Useful?

Inheritance helps make CSS more efficient by reducing repetition.

Instead of writing the same style for multiple elements, you can apply it once to a parent element and allow child elements to inherit it.

### Without Inheritance

```css
h1 {
  color: blue;
}

p {
  color: blue;
}

span {
  color: blue;
}
```

### With Inheritance

```css
body {
  color: blue;
}
```

All child elements inherit the text color automatically, resulting in cleaner and more maintainable CSS.

---

# Important Rule About Inheritance

Inheritance works in **one direction only**:

```text
Parent
   ↓
Child
```

Styles flow **from parent to child**.

If a child element changes an inherited property, the parent element is **not affected**.

### Example

```html
<div style="color: blue;">
  Parent text

  <p style="color: red;">
    Child text
  </p>
</div>
```

### Result

- The parent text remains **blue**.
- The child text becomes **red**.

Changing the child's color does not change the parent's color.

---

# Inheritance at a Glance

| Property | Inherited by Default? |
|-----------|:---------------------:|
| `color` | Yes |
| `font-family` | Yes |
| `font-size` | Yes |
| `line-height` | Yes |
| `text-align` | Yes |
| `margin` | No |
| `padding` | No |
| `border` | No |
| `background` | No |
| `width` | No |
| `height` | No |

---

# Key Points

- Inheritance allows child elements to receive certain CSS properties from their parent elements.
- It helps create consistent styling while reducing duplicate CSS.
- Common inherited properties include `color`, `font-family`, `font-size`, and `line-height`.
- Properties such as `margin`, `padding`, `border`, and `background` are **not** inherited automatically.
- The `inherit` keyword can force a child element to inherit a property from its parent.
- Inheritance only works **from parent to child**.
- Overriding a property on a child element does **not** affect its parent.
