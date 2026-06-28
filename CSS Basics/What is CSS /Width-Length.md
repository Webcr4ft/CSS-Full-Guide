# How Do `width` and `height` Work?

In CSS, the `width` and `height` properties control the size (dimensions) of elements on a webpage.

These properties can be set using different CSS units, including:

- `px` (Pixels)
- `%` (Percentage)
- `vw` (Viewport Width)
- `vh` (Viewport Height)
- And many more.

---

# The `width` Property

The `width` property specifies **how wide** an element should be.

## Default Value

```css
width: auto;
```

When `width` is set to `auto` (the default), the browser decides the element's width based on:

- Its content
- Its parent element
- Its display type

For example, a `<div>` with `width: auto` usually stretches to fill the entire width of its parent container.

---

# The `height` Property

The `height` property specifies **how tall** an element should be.

## Default Value

```css
height: auto;
```

When the height is `auto`, the browser automatically adjusts the height to fit the content inside the element.

---

# Example: Setting `width` and `height`

```html
<head>
  <style>
    .box {
      width: 100px;
      height: 100px;
      background-color: skyblue;
    }
  </style>
</head>

<body>
  <div class="box"></div>
</body>
```

### Explanation

The `.box` element has:

- `width: 100px`
- `height: 100px`
- `background-color: skyblue`

The result is a **100 × 100 pixel** sky-blue square.

---

# What Are Pixels (`px`)?

Pixels (`px`) are fixed-size units in CSS.

Example:

```css
width: 100px;
```

This always creates an element that is **100 pixels wide**, regardless of the screen size.

Pixels provide precise control over an element's dimensions.

---

# The `min-width` Property

The `min-width` property sets the **smallest width** an element is allowed to have.

Example:

```css
min-width: 100px;
```

Even if the element's content is smaller, it **cannot shrink below 100px**.

---

# The `min-height` Property

The `min-height` property sets the **smallest height** an element can have.

Example:

```css
min-height: 100px;
```

The element will never become shorter than **100px**.

---

# Example: `min-width` and `min-height`

```html
<head>
  <style>
    .box {
      width: 50px;
      min-width: 100px;

      height: 50px;
      min-height: 100px;

      background-color: lightcoral;
    }
  </style>
</head>

<body>
  <div class="box"></div>
</body>
```

### Explanation

Although the box is set to:

```css
width: 50px;
height: 50px;
```

It will actually become:

```text
100px × 100px
```

This happens because:

```css
min-width: 100px;
min-height: 100px;
```

are larger than the specified `width` and `height`.

> **Rule:** If `min-width` or `min-height` is larger than `width` or `height`, the minimum values take priority.

---

# Why Use `min-width` and `min-height`?

They prevent elements from becoming too small.

This helps maintain:

- Consistent layouts
- Better readability
- Improved usability

---

# The `max-width` Property

The `max-width` property sets the **largest width** an element is allowed to have.

Example:

```css
max-width: 150px;
```

Even if more space is available, the element **cannot grow wider than 150px**.

---

# The `max-height` Property

The `max-height` property sets the **largest height** an element can grow to.

Example:

```css
max-height: 150px;
```

The element will never exceed **150px** in height.

---

# Example: `max-width` and `max-height`

```html
<head>
  <style>
    .box {
      width: 200px;
      max-width: 150px;

      height: 200px;
      max-height: 150px;

      background-color: lightgreen;
    }
  </style>
</head>

<body>
  <div class="box"></div>
</body>
```

### Explanation

The box is initially set to:

```css
width: 200px;
height: 200px;
```

However, because:

```css
max-width: 150px;
max-height: 150px;
```

the final size becomes:

```text
150px × 150px
```

> **Rule:** If `max-width` or `max-height` is smaller than `width` or `height`, the maximum values take priority.

---

# Why Use `max-width` and `max-height`?

They prevent elements from becoming too large.

This helps create:

- Responsive layouts
- Better control over designs
- Cleaner user interfaces

---

# CSS Priority Rules

CSS follows these rules when determining an element's size.

## Minimum Size

If:

```css
width: 50px;
min-width: 100px;
```

The final width becomes:

```text
100px
```

because the minimum size overrides the smaller width.

---

## Maximum Size

If:

```css
width: 600px;
max-width: 500px;
```

The final width becomes:

```text
500px
```

because the maximum size limits the element.

---

# Priority Summary

| Property | Effect |
|----------|--------|
| `width` | Sets the normal width |
| `height` | Sets the normal height |
| `min-width` | Prevents width from becoming too small |
| `min-height` | Prevents height from becoming too small |
| `max-width` | Prevents width from becoming too large |
| `max-height` | Prevents height from becoming too large |

---

# Key Takeaways

- `width` controls an element's width.
- `height` controls an element's height.
- Both default to `auto`.
- `min-width` and `min-height` set the smallest allowed size.
- `max-width` and `max-height` set the largest allowed size.
- `min-*` properties override smaller values.
- `max-*` properties override larger values.
- Using these properties helps create responsive, consistent, and maintainable layouts.
