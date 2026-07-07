# How Do You Space List Items Using `margin` or `line-height`?

Proper spacing between list items improves readability and gives your content a cleaner appearance. In CSS, the two most common properties used for this are `margin` and `line-height`.

While both can increase vertical space, they serve different purposes.

---

# Spacing List Items with `margin`

The `margin` property adds space **outside** an element. When applied to list items (`li`), it creates space between each item in the list.

## Example HTML

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

By default, browsers apply only a small amount of spacing between list items.

---

## Using `margin-bottom`

You can increase the space between each list item by applying `margin-bottom`.

### HTML

```html
<link rel="stylesheet" href="styles.css">

<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

### CSS

```css
li {
  margin-bottom: 40px;
}
```

### Result

Each list item receives **40 pixels** of space below it, making the list easier to read.

---

# Spacing List Items with `line-height`

The `line-height` property controls the vertical spacing between lines of text inside an element.

Unlike `margin`, it does **not** directly add space between separate list items.

---

## How `line-height` Works

- Increases the spacing between lines of text.
- Makes paragraphs and long list items easier to read.
- Can make single-line list items appear more spaced out because each line becomes taller.

---

## Example HTML

```html
<link rel="stylesheet" href="styles.css">

<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

### CSS

```css
li {
  line-height: 2;
}
```

---

## What Does `line-height: 2;` Mean?

```css
li {
  line-height: 2;
}
```

A value of `2` means each line's height is **twice the font size**.

For example:

- Font size: `16px`
- Line height: `32px`

This creates more vertical space within the text.

---

# `margin` vs `line-height`

| Property | Purpose | Affects |
|----------|---------|---------|
| `margin` | Adds space outside an element | Space between list items |
| `line-height` | Increases the height of text lines | Space between lines inside a list item |

---

# When to Use Each

Use **`margin`** when you want to:

- Increase the gap between list items.
- Separate elements from one another.
- Improve the visual layout of lists.

Example:

```css
li {
  margin-bottom: 20px;
}
```

---

Use **`line-height`** when you want to:

- Improve text readability.
- Increase spacing between multiple lines of text.
- Create a more open text layout.

Example:

```css
li {
  line-height: 1.8;
}
```

---

# Key Points

- `margin` adds space **outside** an element.
- `margin-bottom` is commonly used to separate list items.
- `line-height` controls the spacing between lines of text.
- `line-height` does **not** directly control the spacing between different list items.
- For spacing between list items, use `margin` or `padding`.
- For improving text readability inside list items, use `line-height`.

---

# Summary

Both `margin` and `line-height` help improve the appearance of lists, but they serve different purposes.

- Use **`margin`** to create space **between** list items.
- Use **`line-height`** to increase the spacing **within** the text of each list item.

Choosing the appropriate property helps create cleaner, more readable, and better-organized web pages.
