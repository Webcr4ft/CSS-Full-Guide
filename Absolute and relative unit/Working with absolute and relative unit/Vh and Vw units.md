# CSS Repository: `vh` and `vw` Units

---

# What Are `vh` and `vw` Units in CSS?

`vh` and `vw` are **viewport-relative CSS units** that size elements based on the dimensions of the browser window (viewport).

They are commonly used to create **responsive layouts** that automatically adapt to different screen sizes.

- `vh` = **Viewport Height**
- `vw` = **Viewport Width**

These units are calculated as a percentage of the viewport.

---

# Understanding `vh`

`vh` stands for **Viewport Height**.

```
1vh = 1% of the viewport's height
```

Examples:

```css
height: 50vh;
```

The element occupies **50%** of the browser's height.

```css
height: 100vh;
```

The element occupies **100%** of the browser's height.

---

# Understanding `vw`

`vw` stands for **Viewport Width**.

```
1vw = 1% of the viewport's width
```

Examples:

```css
width: 50vw;
```

The element occupies **50%** of the browser's width.

```css
width: 100vw;
```

The element occupies the entire browser width.

---

# Example 1: Full-Screen Hero Section

## HTML

```html
<link rel="stylesheet" href="styles.css">

<section class="hero">
  <h1>100vh / 100vw Example</h1>
  <p>This section fills the entire browser window.</p>
</section>
```

## CSS

```css
body {
  margin: 0;
  font-family: sans-serif;
  border: 5px dashed #333;
}

.hero {
  height: 100vh;
  width: 100vw;
  background-color: #add8e6;
  padding: 2em;
}

.hero h1 {
  font-size: 2em;
  margin-bottom: 0.5em;
}

.hero p {
  font-size: 1em;
}
```

---

# How It Works

```css
height: 100vh;
```

Makes the section fill the full height of the browser.

```css
width: 100vw;
```

Makes the section fill the full width of the browser.

Regardless of screen size, the hero section always fills the viewport.

---

# Example 2: Responsive Typography

## HTML

```html
<link rel="stylesheet" href="styles.css">

<h1>Responsive Heading</h1>

<p>The heading scales with the viewport width.</p>
```

## CSS

```css
h1 {
  font-size: 5vw;
}
```

---

# How It Works

```
5vw
```

Means:

```
5% of the viewport width
```

As the browser becomes wider:

- Text becomes larger.

As the browser becomes narrower:

- Text becomes smaller.

This creates fluid typography.

---

# Why `vh` and `vw` Are Useful

These units automatically update whenever the viewport changes.

If the user:

- Resizes the browser
- Rotates a mobile device
- Switches between screens

Elements using `vh` and `vw` resize instantly without refreshing the page.

---

# Common Use Cases

Use `vh` and `vw` for:

- Hero sections
- Landing pages
- Full-screen backgrounds
- Responsive typography
- Responsive banners
- Splash screens
- Image galleries
- Modern responsive layouts

---

# Advantages

- Responsive by default
- Automatically adjusts to screen size
- Great for full-screen layouts
- Easy to create fluid designs
- Works well with Flexbox and Grid

---

# Things to Be Careful About

## Using `vw` for Text

Large monitors may make text excessively large.

Small phones may make text too small.

Example:

```css
h1 {
  font-size: 8vw;
}
```

This may not be comfortable to read on every device.

---

## Mobile Viewport Height

On many mobile browsers, the address bar appears and disappears while scrolling.

Because of this:

```css
height: 100vh;
```

can sometimes produce unexpected layout shifts.

This is one reason developers often combine `vh` with newer viewport units or other layout techniques.

---

# Best Practices

- Use `100vh` for full-screen sections.
- Use `100vw` for full-width layouts.
- Use `vw` carefully for typography.
- Test layouts on both desktop and mobile devices.
- Combine viewport units with Flexbox, Grid, and relative units for better responsiveness.

---

# Comparison

| Unit | Relative To | Best Used For |
|------|-------------|---------------|
| `px` | Fixed value | Borders, icons |
| `%` | Parent element | Flexible layouts |
| `em` | Parent/current font size | Component spacing |
| `rem` | Root font size | Typography |
| `vh` | Viewport height | Full-screen sections |
| `vw` | Viewport width | Responsive layouts and text |

---

# Summary

`vh` and `vw` are viewport-relative units that allow elements to scale with the browser window.

- Use **`vh`** for heights based on the viewport.
- Use **`vw`** for widths and responsive sizing based on the viewport.

These units are excellent for building responsive websites, especially full-screen layouts and fluid designs. However, they should be used thoughtfully—particularly for typography and on mobile devices—to ensure a consistent user experience.
