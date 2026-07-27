# CSS Repository: em and rem Units

---

# What Are `em` and `rem` Units in CSS?

`em` and `rem` are **relative CSS length units** used to create flexible, scalable, and accessible web designs.

Unlike absolute units such as `px`, these units adjust based on font sizes, making them ideal for responsive layouts and accessible typography.

The two units may seem similar, but they reference different elements.

- `em` is relative to the **current element's font size** (or its parent's font size when used for `font-size`).
- `rem` is relative to the **root (`html`) element's font size**.

---

# Why Use Relative Units?

Pixels (`px`) create fixed sizes that don't always respond well when users change their browser's default font size.

Relative units solve this problem by allowing text and spacing to scale automatically.

Benefits include:

- Better accessibility
- Responsive typography
- Flexible layouts
- Easier scaling across different screen sizes
- Improved user experience

---

# The `em` Unit

The `em` unit is based on the **font size of the current element**.

When used for the `font-size` property, it becomes relative to the **parent element's font size**.

## Basic Syntax

```css
selector {
  margin: 1.5em;
}
```

---

# Example 1: Using `em` for Margin

## HTML

```html
<link rel="stylesheet" href="styles.css">

<p class="para">
  I am a paragraph element
</p>

<div class="blue-box"></div>
```

## CSS

```css
.para {
  font-size: 20px;
  margin-bottom: 1.5em;
  border: 2px solid red;
}

.blue-box {
  background-color: blue;
  color: white;
  padding: 10px;
  width: 100px;
  height: 100px;
}
```

---

# How It Works

The paragraph's font size is:

```
20px
```

Its margin is:

```
1.5em
```

Calculation:

```
1.5 × 20px = 30px
```

So the bottom margin becomes:

```
30px
```

This creates space between the paragraph and the blue box.

---

# What Happens Without `font-size`?

If you remove:

```css
font-size: 20px;
```

The paragraph inherits the font size of its parent.

Usually, the parent is the `body` element, whose default font size is:

```
16px
```

Calculation:

```
1.5 × 16px = 24px
```

Now the margin becomes **24px** instead of **30px**.

---

# Common Uses for `em`

`em` is excellent for components that should scale together.

Examples include:

- Buttons
- Cards
- Navigation menus
- Form controls
- Alerts
- Badges

When the font size changes, everything inside the component changes proportionally.

Example:

```css
.button {
  font-size: 1.2rem;
  padding: 1em 2em;
}
```

If the button text becomes larger, the padding also grows automatically.

---

# Accessibility Problem with Pixels

Many users increase their browser's default font size because of:

- Visual impairments
- Reading difficulties
- High-resolution displays

If your typography is written entirely in pixels:

```css
font-size: 18px;
```

The design becomes less adaptable because the text doesn't scale as naturally with browser settings.

---

# The `rem` Unit

`rem` stands for:

```
Root EM
```

Unlike `em`, it is always relative to the **root (`html`) element**.

By default:

```css
html {
    font-size: 16px;
}
```

Every `rem` value is calculated from this size.

---

# Example 2: Using `rem`

## HTML

```html
<link rel="stylesheet" href="styles.css">

<p>This is regular text.</p>

<p class="para">
  This text is slightly larger.
</p>
```

## CSS

```css
.para {
  font-size: 1.2rem;
  margin-bottom: 1.5em;
  border: 2px solid red;
}
```

---

# How `rem` Is Calculated

Default root size:

```
16px
```

Calculation:

```
1.2 × 16px
```

Result:

```
19.2px
```

So:

```css
font-size: 1.2rem;
```

equals:

```
19.2px
```

---

# Why `rem` Is Better for Typography

Suppose a user changes their browser's default font size to:

```
20px
```

Now:

```css
font-size: 1.2rem;
```

becomes:

```
1.2 × 20px = 24px
```

Everything automatically scales.

This makes websites much easier to read.

---

# `em` vs `rem`

| `em` | `rem` |
|------|-------|
| Relative to the current element (or parent for `font-size`) | Relative to the root (`html`) element |
| Can compound when nested | Always consistent |
| Best for component spacing | Best for typography |
| Changes based on local context | Changes based only on the root font size |

---

# When Should You Use `em`?

Use `em` for:

- Padding
- Margins
- Borders
- Component spacing
- Buttons
- Cards
- Navigation items
- Elements that should scale together

Example:

```css
.card {
  font-size: 1rem;
  padding: 2em;
}
```

---

# When Should You Use `rem`?

Use `rem` for:

- Font sizes
- Headings
- Paragraphs
- Lists
- Consistent spacing
- Global layouts

Example:

```css
h1 {
  font-size: 2.5rem;
}

p {
  font-size: 1rem;
}
```

---

# Advantages of `em`

- Scales with the component
- Great for reusable UI elements
- Keeps proportions consistent
- Useful for modular design

---

# Advantages of `rem`

- Better accessibility
- Consistent typography
- Responds to browser settings
- Easier to maintain
- Prevents unwanted nested scaling

---

# Best Practices

- Use `rem` for font sizes.
- Use `em` for padding and spacing inside components.
- Avoid using pixels for typography unless necessary.
- Let users control text size through browser settings.
- Combine `rem` and `em` for responsive, accessible designs.

---

# Quick Comparison

| Unit | Relative To | Best Used For |
|------|-------------|---------------|
| `px` | Fixed size | Borders, icons, small details |
| `%` | Parent element | Responsive layouts |
| `em` | Current element / parent font size | Component spacing |
| `rem` | Root (`html`) font size | Typography |

---

# Summary

`em` and `rem` are two of the most important relative CSS units.

- Use **`em`** when elements inside a component should scale together.
- Use **`rem`** for font sizes and global spacing because it respects the user's browser settings and improves accessibility.

Using these units instead of fixed pixels helps create websites that are responsive, flexible, and easier for everyone to use.
