# How Do Background Image Size, Repeat, Position, and Attachment Work?

When working with **background images** in CSS, several properties allow you to control how those images appear inside an element.

The four main properties are:

- `background-size`
- `background-repeat`
- `background-position`
- `background-attachment`

Before learning these properties, let's first look at the `background-image` property.

---

# `background-image`

The `background-image` property is used to add an image as the background of an element.

### Syntax

```css
body {
  background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
}
```

### Explanation

- `background-image` tells the browser to place an image behind the content of the selected element.
- `url()` specifies the location of the image.
- In this example, the image is applied to the entire `<body>` element, making it the page's background.

---

# `background-size`

Once a background image is added, you can control its size using the `background-size` property.

## Using `contain`

```css
body {
  background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
  background-size: contain;
  min-height: 100px;
}
```

### Explanation

`background-size: contain;`

- Scales the image as large as possible.
- Keeps the image's original aspect ratio.
- Prevents stretching or cropping.
- Ensures the entire image is visible inside the element.

Because the image is completely visible, there may be empty space around it if the element is larger than the image.

---

## Why is `min-height: 100px` used?

```css
min-height: 100px;
```

This creates a minimum height for the element so the background image has space to appear.

Without a height (or content inside the element), the element might collapse to zero height, making the background impossible to see.

Giving it a minimum height ensures:

- The background remains visible.
- The layout keeps a consistent appearance.
- Even empty elements still occupy space.

---

## Using `cover`

```css
body {
  background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
  background-size: cover;
  min-height: 100px;
}
```

### Explanation

`background-size: cover;`

- Enlarges the image until it completely covers the element.
- Maintains the original aspect ratio.
- Prevents distortion.

Unlike `contain`, `cover` may crop part of the image so that no empty spaces remain.

---

# `contain` vs `cover`

## `contain`

✔ Entire image is visible.

✔ No cropping.

✔ Empty space may appear.

```css
background-size: contain;
```

---

## `cover`

✔ Entire element is covered.

✔ No empty space.

✔ Some parts of the image may be cropped.

```css
background-size: cover;
```


# `background-repeat`

By default, CSS repeats background images to fill the available space.

That means the image repeats:

- Horizontally
- Vertically

until the entire element is covered.

---

## Preventing repetition

```css
body {
  background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
  background-size: contain;
  background-repeat: no-repeat;
  min-height: 100px;
}
```

### Explanation

```css
background-repeat: no-repeat;
```

This tells the browser to display only one copy of the image.

The image will not repeat in any direction.

---

## Repeating horizontally

```css
body {
  background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
  background-size: contain;
  background-repeat: repeat-x;
  min-height: 100px;
}
```

### Explanation

```css
background-repeat: repeat-x;
```

The image repeats from left to right.

It only repeats along the horizontal (x) axis.

---

## Repeating vertically

```css
body {
  background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
  background-size: contain;
  background-repeat: repeat-y;
  min-height: 100px;
}
```

### Explanation

```css
background-repeat: repeat-y;
```

The image repeats from top to bottom.

It only repeats along the vertical (y) axis.

---

# Summary of `background-repeat`

## `repeat`

(Default)

Repeats horizontally and vertically.

```css
background-repeat: repeat;
```

---

## `no-repeat`

Displays only one image.

```css
background-repeat: no-repeat;
```

---

## `repeat-x`

Repeats only from left to right.

```css
background-repeat: repeat-x;
```

---

## `repeat-y`

Repeats only from top to bottom.

```css
background-repeat: repeat-y;
```


# `background-position`

The `background-position` property controls where the background image appears inside an element.

You can position it using:

- `top`
- `bottom`
- `left`
- `right`
- `center`

You can also use pixel (`px`) values or percentages (`%`).

---

## Example

```css
body {
  background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center top;
  min-height: 100px;
}
```

### Explanation

```css
background-position: center top;
```

This places the image:

- Horizontally in the center.
- Vertically at the top.

---

# `background-attachment`

The `background-attachment` property determines how the background behaves when the page scrolls.

The two most common values are:

## `scroll`

(Default)

The background moves along with the page content.

```css
background-attachment: scroll;
```

---

## `fixed`

The background remains fixed in the browser window while the content scrolls over it.

```css
body {
  background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
  background-position: center top;
  background-attachment: fixed;
}
```

### Explanation

```css
background-attachment: fixed;
```

This keeps the image in the same position on the screen even as the user scrolls.

It creates a simple parallax-like effect because the content moves while the background stays still.

---

# The `background` Shorthand Property

Instead of writing several background properties separately, CSS allows you to combine them into a single `background` declaration.

## Example

```css
body {
  background: center top fixed
    url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
}
```

### Explanation

This shorthand combines:

- `background-position`
- `background-attachment`
- `background-image`

into one line.

This makes your CSS shorter and easier to read.

---

# Quick Recap

## `background-image`

Adds a background image.

```css
background-image: url(...);
```

---

## `background-size`

Controls the size of the image.

```css
background-size: contain;
background-size: cover;
```

---

## `background-repeat`

Controls whether the image repeats.

```css
background-repeat: repeat;
background-repeat: no-repeat;
background-repeat: repeat-x;
background-repeat: repeat-y;
```

---

## `background-position`

Controls where the image appears.

```css
background-position: center top;
background-position: left center;
background-position: right bottom;
```

---

## `background-attachment`

Controls how the background behaves while scrolling.

```css
background-attachment: scroll;
background-attachment: fixed;
```

---

# Conclusion

By mastering these properties, you'll gain full control over how background images appear in your web pages.

Whether you want an image to fill the screen, repeat like a pattern, stay fixed while scrolling, or appear in a specific location, these properties give you the flexibility to create visually appealing and responsive web designs.
