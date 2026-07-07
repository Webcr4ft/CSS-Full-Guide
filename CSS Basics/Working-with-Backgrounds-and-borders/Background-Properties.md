# 🎨 How Do Background Image Size, Repeat, Position, and Attachment Work?

When working with background images in CSS, you have several properties at your disposal to control how these images are displayed.

The main properties we'll focus on are:

- `background-size`
- `background-repeat`
- `background-position`
- `background-attachment`

Together, these properties allow you to control the size, placement, repetition, and scrolling behavior of background images.

---

# The `background-image` Property

Before using the other background properties, you first need to specify an image using the `background-image` property.

### Example

```css
body {
    background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
}
```

### Explanation

The CSS above applies a cat image as the background of the entire `body` element.

---

# The `background-size` Property

The `background-size` property controls how large the background image appears.

There are two commonly used keyword values:

- `contain`
- `cover`

---

## Using `background-size: contain`

The `contain` value scales the image as large as possible **without cropping or stretching**.

### Example

```css
body {
    background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
    background-size: contain;
    min-height: 100px;
}
```

### Explanation

- The image keeps its original aspect ratio.
- The entire image remains visible.
- Empty space may appear if the image doesn't completely fill the element.

Notice the use of:

```css
min-height: 100px;
```

This ensures the body has enough height for the background image to be visible, even when there's very little content on the page. It also helps maintain a balanced and visually appealing layout.

---

## Using `background-size: cover`

Instead of fitting the whole image inside the element, you can make it completely cover the element.

### Example

```css
body {
    background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
    background-size: cover;
    min-height: 100px;
}
```

### Explanation

With `cover`:

- The image scales to cover the entire element.
- The image maintains its aspect ratio.
- Parts of the image may be cropped.
- No empty background space is left uncovered.

This is one of the most popular values when creating full-screen background images.

---

# The `background-repeat` Property

By default, CSS repeats background images.

If the image is smaller than the element, it repeats both:

- Horizontally
- Vertically

This fills the available space.

---

## Prevent Repeating

To stop the image from repeating, use:

```css
background-repeat: no-repeat;
```

### Example

```css
body {
    background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
    background-size: contain;
    background-repeat: no-repeat;
    min-height: 100px;
}
```

### Result

The image appears only once.

---

## Repeat Horizontally

If you only want the image to repeat from left to right, use:

```css
background-repeat: repeat-x;
```

### Example

```css
body {
    background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
    background-size: contain;
    background-repeat: repeat-x;
    min-height: 100px;
}
```

### Result

The image repeats only across the horizontal axis.

---

## Repeat Vertically

If you want the image to repeat from top to bottom, use:

```css
background-repeat: repeat-y;
```

### Example

```css
body {
    background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
    background-size: contain;
    background-repeat: repeat-y;
    min-height: 100px;
}
```

### Result

The image repeats only along the vertical axis.

---

# The `background-position` Property

The `background-position` property controls where the background image appears inside the element.

You can position the image using:

## Keywords

- `top`
- `bottom`
- `left`
- `right`
- `center`

You can also use:

- Pixel values (`20px`)
- Percentage values (`50%`)

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

The value

```css
background-position: center top;
```

means:

- `center` → horizontally center the image.
- `top` → place the image at the top of the element vertically.

This positions the image at the top-center of the page.

---

# The `background-attachment` Property

The `background-attachment` property determines whether the background image moves when the page is scrolled.

The two main values are:

| Value | Description |
|--------|-------------|
| `scroll` | Default. The background moves together with the page content. |
| `fixed` | The background stays fixed in the viewport while the page scrolls. |

---

## Using `background-attachment: fixed`

### Example

```css
body {
    background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
    background-position: center top;
    background-attachment: fixed;
}
```

### Explanation

Here,

```css
background-attachment: fixed;
```

keeps the background image in a fixed position on the screen.

As the user scrolls:

- The page content moves.
- The background image stays in the same place.

This creates a simple parallax-like visual effect.

---

# The `background` Shorthand Property

Instead of writing several background properties individually, CSS provides the shorthand `background` property.

This allows multiple background properties to be combined into a single declaration.

### Example

```css
body {
    background: center top fixed
        url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
}
```

### Explanation

The shorthand above combines:

- `background-image`
- `background-position`
- `background-attachment`

into one line.

Using shorthand can make your CSS shorter and easier to maintain, especially when multiple background properties are used together.

---

# Summary

Background images become much more powerful when combined with CSS background properties.

- `background-image` sets the image.
- `background-size` controls how large the image appears.
- `background-repeat` determines whether the image repeats.
- `background-position` controls where the image is placed.
- `background-attachment` determines whether the image scrolls with the page or stays fixed.
- `background` provides a convenient shorthand for combining multiple background properties into a single declaration.

By mastering these properties, you'll gain precise control over how background images are displayed in your web designs, helping you create layouts that are both visually appealing and highly functional.
