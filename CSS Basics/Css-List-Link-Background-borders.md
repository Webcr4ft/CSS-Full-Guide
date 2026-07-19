# Lists, Links, Background and Borders Review

---

# Styling Lists

## `line-height` Property

The `line-height` property is used to create space between lines of text, making content easier to read.

### Accepted values
- `normal`
- Numbers (e.g. `1.5`)
- Percentages (e.g. `150%`)
- Length units (e.g. `20px`, `2em`)

### Example

#### HTML

```html
<link rel="stylesheet" href="styles.css">

<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

#### CSS

```css
ul {
  line-height: 2;
}
```

---

## `list-style-type` Property

The `list-style-type` property changes the marker (bullet or number) displayed before list items.

### Common values

- `disc` (default)
- `circle`
- `square`
- `decimal`
- `lower-alpha`
- `upper-alpha`
- `lower-roman`
- `upper-roman`
- `none`

### Example

#### HTML

```html
<link rel="stylesheet" href="styles.css">

<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

#### CSS

```css
ul {
  list-style-type: square;
}
```

---

## `list-style-position` Property

The `list-style-position` property determines where the bullet appears relative to the list item's content.

### Values

- `outside` (default)
- `inside`

### Example

#### HTML

```html
<link rel="stylesheet" href="styles.css">

<ul class="inside-list">
  <li>Item with inside position</li>
  <li>Item with inside position</li>
</ul>

<ul class="outside-list">
  <li>Item with outside position</li>
  <li>Item with outside position</li>
</ul>
```

#### CSS

```css
.inside-list {
  list-style-position: inside;
}

.outside-list {
  list-style-position: outside;
}
```

---

## `list-style-image` Property

The `list-style-image` property lets you replace the normal bullet with an image.

### Example

```css
ul {
  list-style-image: url("bullet.png");
}
```

The image must be a valid URL or file path.

---

# Spacing List Items Using `margin`

Besides `line-height`, margins can also improve readability.

Margins create space **outside** each list item.

The most common property is:

```css
margin-bottom: 10px;
```

This creates a **10-pixel gap** below each list item.

### Example

#### HTML

```html
<link rel="stylesheet" href="styles.css">

<ul class="list">
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

#### CSS

```css
.list li {
  margin-bottom: 20px;
}
```

---

# Styling Links

## Pseudo-classes

A pseudo-class is a keyword added to a selector that styles an element in a specific state.

Common pseudo-classes include:

- `:link`
- `:visited`
- `:hover`
- `:focus`
- `:active`

---

## `:link`

Styles links that have **not been visited**.

### Example

#### HTML

```html
<link rel="stylesheet" href="styles.css">

<a href="/">Example Link</a>
```

#### CSS

```css
a:link {
  color: red;
}
```

---

## `:visited`

Styles links that the user has already visited.

### Example

```css
a:visited {
  color: purple;
}
```

---

## `:hover`

Styles an element while the mouse is hovering over it.

### Example

#### HTML

```html
<link rel="stylesheet" href="styles.css">

<a href="/">Hover over me!</a>
```

#### CSS

```css
a:hover {
  color: green;
  text-decoration: underline;
}
```

---

## `:focus`

Styles an element after it receives focus.

Examples include:

- Input fields
- Buttons
- Links
- Select menus

### Example

#### HTML

```html
<link rel="stylesheet" href="styles.css">

<a href="/">Example Link</a>
```

#### CSS

```css
a:focus {
  outline: 2px solid orange;
}
```

---

## `:active`

Styles an element while it is being clicked.

### Example

#### HTML

```html
<link rel="stylesheet" href="styles.css">

<a href="/">Click Me!</a>
```

#### CSS

```css
a:active {
  color: pink;
}
```

---

# Working With Backgrounds and Borders

## `background-size`

Controls how large the background image appears.

### Common values

- `cover`
- `contain`

---

### `background-size: cover`

The image fills the entire element.

Parts of the image may be cropped.

#### Example

```html
<style>
body {
  background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  min-height: 100px;
}
</style>
```

---

### `background-size: contain`

The image is resized until the entire image fits inside the element.

Nothing gets cropped.

#### Example

```html
<style>
body {
  background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
  background-size: contain;
  background-repeat: no-repeat;
  min-height: 100px;
}
</style>
```

---

## `background-repeat`

Determines whether a background image repeats.

### Common values

- `repeat` (default)
- `no-repeat`
- `repeat-x`
- `repeat-y`

### Example

```html
<style>
body {
  background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
  background-size: contain;
  background-repeat: no-repeat;
  min-height: 100px;
}
</style>
```

---

## `background-position`

Controls where the image appears.

### Keywords

- `top`
- `bottom`
- `left`
- `right`
- `center`

You can also use percentages and lengths.

### Example

```html
<style>
body {
  background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center top;
  min-height: 100px;
}
</style>
```

---

## `background-attachment`

Determines whether the image scrolls.

### Values

- `scroll`
- `fixed`

Example:

```css
body {
  background-attachment: fixed;
}
```

---

## `background-image`

Adds a background image.

You can use:

- `url()`
- `linear-gradient()`
- `radial-gradient()`

### Example

```html
<style>
body {
  background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
  min-height: 100px;
}
</style>
```

---

## `background`

Shorthand property.

Instead of writing several properties separately, you can combine them.

### Example

```css
background: center top no-repeat url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
```

---

## Good Contrast

Always choose colors with enough contrast.

WCAG recommends:

- **4.5 : 1** for normal text
- **3 : 1** for large text

This makes text readable for everyone.

---

# Borders

## `border-top`

Adds a border only to the top.

```css
border-top: 3px solid blue;
```

---

## `border-right`

```css
border-right: 2px solid red;
```

---

## `border-bottom`

```css
border-bottom: 1px dashed green;
```

---

## `border-left`

```css
border-left: 4px dotted orange;
```

---

## Example Using Individual Borders

### HTML

```html
<link rel="stylesheet" href="styles.css">

<div class="bordered-box">
  Box with different borders
</div>
```

### CSS

```css
.bordered-box {
  border-top: 3px solid blue;
  border-right: 2px solid red;
  border-bottom: 1px dashed green;
  border-left: 4px dotted orange;
  padding: 20px;
}
```

---

## `border`

The shorthand property.

Instead of writing width, style and color separately:

```css
border: 1px solid black;
```

### Example

#### HTML

```html
<link rel="stylesheet" href="styles.css">

<img
src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg"
alt="A cute cat lying on its back.">
```

#### CSS

```css
img {
  border: 2px solid red;
}
```

---

## `border-radius`

Rounds the corners.

### Example

```css
img {
  border: 2px solid black;
  border-radius: 10px;
}
```

---

## `border-style`

Determines the appearance of the border.

### Common values

- `solid`
- `dashed`
- `dotted`
- `double`

### Example

#### HTML

```html
<link rel="stylesheet" href="styles.css">

<div class="solid-border">
  Solid Border
</div>

<div class="dashed-border">
  Dashed Border
</div>

<div class="dotted-border">
  Dotted Border
</div>

<div class="double-border">
  Double Border
</div>
```

#### CSS

```css
.solid-border {
  border: 3px solid blue;
  margin-bottom: 10px;
  padding: 10px;
}

.dashed-border {
  border: 3px dashed red;
  margin-bottom: 10px;
  padding: 10px;
}

.dotted-border {
  border: 3px dotted green;
  padding: 10px;
}

.double-border {
  border: 3px double blueviolet;
  padding: 10px;
}
```

---

# Gradients

## `linear-gradient()`

Creates a smooth transition between colors in a straight line.

### Example

#### HTML

```html
<link rel="stylesheet" href="styles.css">

<div class="linear-gradient"></div>
```

#### CSS

```css
.linear-gradient {
  background: linear-gradient(to right, red, blue);
  height: 40vh;
}
```

---

## `radial-gradient()`

Creates a gradient that spreads outward from a center point.

### Example

#### HTML

```html
<link rel="stylesheet" href="styles.css">

<div class="radial-gradient"></div>
```

#### CSS

```css
.radial-gradient {
  background: radial-gradient(circle, red, blue);
  height: 40vh;
}
```

---

# Quick Summary

| Property | Purpose |
|----------|---------|
| `line-height` | Space between lines |
| `list-style-type` | Changes bullet style |
| `list-style-position` | Places bullets inside or outside |
| `list-style-image` | Uses an image as the bullet |
| `margin-bottom` | Adds spacing between list items |
| `:link` | Styles unvisited links |
| `:visited` | Styles visited links |
| `:hover` | Styles elements while hovering |
| `:focus` | Styles focused elements |
| `:active` | Styles clicked elements |
| `background-size` | Controls image size |
| `background-repeat` | Controls repetition |
| `background-position` | Controls image position |
| `background-attachment` | Controls scrolling behavior |
| `background-image` | Adds a background image |
| `background` | Shorthand background property |
| `border` | Shorthand border property |
| `border-radius` | Rounds corners |
| `border-style` | Changes border appearance |
| `linear-gradient()` | Straight color transition |
| `radial-gradient()` | Circular color transition |
