# What Are the Different Ways You Can Add Borders Around Images?

Borders are a simple but effective way to enhance the appearance of images in CSS. They can help images stand out, create visual separation, or match the overall design of a webpage.

CSS provides several methods for adding and customizing borders around images, each offering different levels of flexibility.

---

## 1. Using the `border` Property

The easiest and most common way to add a border to an image is with the `border` shorthand property.

The `border` property lets you define:

- Border width
- Border style
- Border color

### HTML

```html
<link rel="stylesheet" href="styles.css">

<img
  src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg"
  alt="A cute cat lying on its back."
>
```

### CSS

```css
img {
  border: 2px solid red;
}
```

This creates a **2-pixel solid red border** around every image.

You can easily change:

- Width (`1px`, `5px`, etc.)
- Style (`solid`, `dashed`, `dotted`, `double`)
- Color (red, blue, black, hex values, RGB, etc.)

---

## 2. Styling Individual Border Sides

Sometimes you may want each side of the image to have a different border.

CSS allows you to style each side independently using:

- `border-top`
- `border-right`
- `border-bottom`
- `border-left`

### HTML

```html
<link rel="stylesheet" href="styles.css">

<img
  src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg"
  alt="A cute cat lying on its back."
>
```

### CSS

```css
img {
  border-top: 10px solid red;
  border-right: 10px dashed green;
  border-bottom: 10px dotted blue;
  border-left: 10px double purple;
}
```

This gives every side of the image a completely different style and color.

---

## 3. Using the `outline` Property

Another way to create a border-like effect is with the `outline` property.

Unlike a normal border, an outline **does not change the element's size or layout**.

### HTML

```html
<link rel="stylesheet" href="styles.css">

<img
  src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg"
  alt="A cute cat lying on its back."
>
```

### CSS

```css
img {
  outline: 3px solid gold;
}
```

This adds a **3-pixel gold outline** around the image without affecting its dimensions.

---

## 4. Creating Rounded Borders with `border-radius`

You can make borders look softer and more modern by adding rounded corners.

Use the `border-radius` property together with the `border` property.

### HTML

```html
<link rel="stylesheet" href="styles.css">

<img
  src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg"
  alt="A cute cat lying on its back."
>
```

### CSS

```css
img {
  border: 2px solid black;
  border-radius: 10px;
}
```

This creates a black border with rounded corners.

Increasing the `border-radius` value makes the corners more rounded, while very large values can create circular images.

---

## Summary

CSS offers several ways to add borders around images:

- Use the `border` property for a simple, customizable border.
- Use individual border properties to style each side differently.
- Use the `outline` property when you need a border effect without affecting layout.
- Combine `border` and `border-radius` to create rounded borders.

These techniques can be mixed and customized to create attractive image styles that fit your webpage's design.
