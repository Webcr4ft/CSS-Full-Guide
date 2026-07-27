# CSS Repository: Percentage (%) Units

---

# What Are Percentage (%) Units in CSS?

Percentages (`%`) are **relative CSS units** that allow you to size elements based on a proportion of another element, usually their **parent container**.

Instead of assigning a fixed size, percentages tell the browser:

> "Make this element **X%** of its parent."

This makes percentage units one of the most important tools for building **responsive** and **flexible** web layouts.

---

# Basic Syntax

```css
selector {
  property: percentage;
}
```

## Example

```css
.box {
  width: 50%;
}
```

The element will take up **50% of the width** of its parent.

---

# Example 1: Percentage Width and Height

## HTML

```html
<link rel="stylesheet" href="styles.css" />

<div class="container">
  <div class="box"></div>
</div>
```

## CSS

```css
.container {
  width: 400px;
  height: 200px;
  background-color: lightgray;
}

.box {
  width: 50%;
  height: 100%;
  background-color: red;
}
```

## Result

- Parent width = **400px**
- Child width = **50%** = **200px**
- Child height = **100%** = **200px**

The child fills the parent's height while using only half of its width.

---

# Example 2: Creating Responsive Layouts

Percentages are perfect for layouts that automatically adjust to different screen sizes.

## HTML

```html
<link rel="stylesheet" href="styles.css" />

<div class="parent">
  <div class="child"></div>
</div>
```

## CSS

```css
.parent {
  width: 100%;
  height: 300px;
  background-color: lightblue;
}

.child {
  width: 80%;
  height: 100%;
  background-color: red;
}
```

## Result

The child always occupies:

- **80%** of the parent's width
- **100%** of the parent's height

Whether the parent becomes wider or narrower, the child adjusts automatically.

---

# Example 3: Flexible Images

Images should resize with their containers instead of overflowing.

## HTML

```html
<link rel="stylesheet" href="styles.css" />

<img src="https://placehold.co/150x150" alt="Example Product Image">
```

## CSS

```css
img {
  max-width: 100%;
  height: auto;
}
```

## Why Use This?

- Prevents images from overflowing
- Makes images responsive
- Keeps the original aspect ratio

This is one of the most common responsive CSS techniques.

---

# Example 4: Percentage Font Sizes

Percentages can also scale text relative to the parent's font size.

## HTML

```html
<link rel="stylesheet" href="styles.css" />

<div class="text-container">
  Parent text.

  <p class="text">
    This is some example text.
  </p>
</div>
```

## CSS

```css
.text-container {
  font-size: 16px;
}

.text {
  font-size: 120%;
}
```

## Result

Parent font size:

```
16px
```

Child font size:

```
120% of 16px = 19.2px
```

The paragraph becomes **20% larger** than its parent.

---

# Example 5: Vertical Centering

Percentages are often combined with `transform` to center elements.

## HTML

```html
<link rel="stylesheet" href="styles.css" />

<div class="centered"></div>
```

## CSS

```css
.centered {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);

  width: 300px;
  height: 300px;

  background-color: red;
}
```

## How It Works

```css
top: 50%;
```

Moves the element halfway down its container.

Then:

```css
transform: translateY(-50%);
```

Moves it upward by **50% of its own height**.

Together, these two properties perfectly center the element vertically.

---

# Percentage Values Are Relative

Percentages are **always calculated relative to something else**.

## Width

```css
width: 50%;
```

Relative to:

```
Parent's width
```

---

## Height

```css
height: 100%;
```

Relative to:

```
Parent's height
```

> The parent must have a defined height for percentage heights to work properly.

---

## Font Size

```css
font-size: 120%;
```

Relative to:

```
Parent's font size
```

---

## Transform

```css
translateY(-50%);
```

Relative to:

```
The element's own size
```

---

# When Should You Use Percentages?

Use percentages when you want:

- Responsive layouts
- Flexible containers
- Scalable images
- Responsive typography
- Fluid designs that adapt to different screen sizes
- Elements that resize with their parent

---

# Advantages

- Responsive by default
- Adapts to different screen sizes
- Easy to create fluid layouts
- Works well with Flexbox and Grid
- Great for modern web design

---

# Things to Be Careful About

## Percentage Heights

```css
.child {
  height: 100%;
}
```

This only works if the parent has a defined height.

Example:

```css
.parent {
  height: 300px;
}
```

Without a parent height, percentage heights may not behave as expected.

---

## Nested Percentages

Using multiple percentage-based elements inside one another can sometimes produce unexpected sizes.

Example:

```css
.parent {
  width: 80%;
}

.child {
  width: 80%;
}
```

The child's width becomes **80% of the parent's 80%**, not 80% of the screen.

---

# Absolute Units vs Percentage Units

| Absolute Units | Percentage Units |
|----------------|------------------|
| Fixed size | Relative size |
| Doesn't adapt | Adapts automatically |
| Good for icons and borders | Great for layouts |
| Not responsive | Responsive |

---

# Best Practices

- Use percentages for responsive layouts.
- Use `max-width: 100%` for responsive images.
- Define parent heights before using percentage heights.
- Avoid deeply nested percentage layouts when possible.
- Combine percentages with Flexbox and Grid for modern responsive designs.

---

# Summary

Percentage (`%`) units are **relative CSS units** that size elements based on their parent or another reference value.

They're essential for creating:

- Responsive websites
- Flexible layouts
- Fluid containers
- Scalable images
- Adaptive typography

Unlike fixed units like `px`, percentages allow elements to grow and shrink automatically, making them one of the most important CSS units for modern web development.

---
