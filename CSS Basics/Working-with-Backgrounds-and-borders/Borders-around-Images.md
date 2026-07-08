# What Are the Different Ways You Can Add Borders Around Images?

CSS provides several ways to add borders around images. These techniques allow you to improve the appearance of images, create visual separation, and match your website's overall design.

Some methods offer simple, consistent borders, while others provide greater flexibility by allowing you to style each side individually or create decorative effects.

The most common techniques include:

- The `border` shorthand property
- Individual border properties
- The `outline` property
- The `border-radius` property

Each approach serves a different purpose depending on your design requirements.

---

# Using the `border` Property

The simplest way to add a border around an image is with the `border` property.

The `border` property is a shorthand that combines three separate properties into a single declaration:

- Border width
- Border style
- Border color

---

## HTML

```html
<link rel="stylesheet" href="styles.css">

<img
    src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg"
    alt="A cute cat lying on its back."
>
```

---

## CSS

```css
img {
    border: 2px solid red;
}
```

---

## Explanation

The declaration

```css
border: 2px solid red;
```

is equivalent to writing:

```css
border-width: 2px;
border-style: solid;
border-color: red;
```

This creates:

- A border width of `2px`
- A `solid` border style
- A `red` border color

The border is applied equally to all four sides of every `img` element.

---

# Border Styles

CSS supports several border styles that can dramatically change an image's appearance.

Some common values include:

| Border Style | Description |
|--------------|-------------|
| `solid` | A continuous line around the element. |
| `dashed` | A border made of short dashes. |
| `dotted` | A border made of small dots. |
| `double` | Two parallel border lines. |

You can freely combine these styles with different colors and widths to achieve the desired effect.

---

# Styling Individual Border Sides

If you need greater control, CSS allows each side of the border to be styled independently.

The available properties are:

- `border-top`
- `border-right`
- `border-bottom`
- `border-left`

---

## HTML

```html
<link rel="stylesheet" href="styles.css">

<img
    src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg"
    alt="A cute cat lying on its back."
>
```

---

## CSS

```css
img {
    border-top: 10px solid red;
    border-right: 10px dashed green;
    border-bottom: 10px dotted blue;
    border-left: 10px double purple;
}
```

---

## Explanation

This example assigns a different border to each side of the image.

| Side | Style |
|------|-------|
| Top | `10px solid red` |
| Right | `10px dashed green` |
| Bottom | `10px dotted blue` |
| Left | `10px double purple` |

Because each side is styled independently, you can create unique and decorative border designs.

---

# Using the `outline` Property

Another way to create a border-like effect is by using the `outline` property.

Although outlines look similar to borders, they behave differently.

One important difference is that an outline **does not affect the element's size or layout**.

Instead, it is drawn outside the element's border.

---

## HTML

```html
<link rel="stylesheet" href="styles.css">

<img
    src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg"
    alt="A cute cat lying on its back."
>
```

---

## CSS

```css
img {
    outline: 3px solid gold;
}
```

---

## Explanation

The declaration

```css
outline: 3px solid gold;
```

creates:

- A `3px` outline
- A `solid` line
- A `gold` color

Unlike a border, the outline does not take up space or change the dimensions of the image.

This makes outlines useful for:

- Keyboard focus indicators
- Accessibility highlights
- Temporary debugging
- Decorative emphasis

---

# Creating Rounded Borders with `border-radius`

If you want softer corners, CSS provides the `border-radius` property.

This property rounds the corners of an element's border.

It is commonly used together with the `border` property.

---

## HTML

```html
<link rel="stylesheet" href="styles.css">

<img
    src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg"
    alt="A cute cat lying on its back."
>
```

---

## CSS

```css
img {
    border: 2px solid black;
    border-radius: 10px;
}
```

---

## Explanation

The border:

```css
border: 2px solid black;
```

creates a solid black border around the image.

The declaration:

```css
border-radius: 10px;
```

rounds each corner by `10px`, giving the image a smoother and more modern appearance.

Increasing the radius creates progressively rounder corners, while using larger values—such as `50%`—can produce circular images when the image has equal width and height.

---

# Combining Border Techniques

These border techniques are not mutually exclusive.

You can combine them to create more advanced designs.

For example, an image can simultaneously have:

- A solid border
- Rounded corners
- An outline
- Different border styles on each side

Combining these properties allows for highly customized image styling while maintaining clean and readable CSS.

---

# Choosing the Right Approach

The best technique depends on your design goals.

Use:

- `border` when you want a simple, consistent border.
- Individual border properties when each side requires a different appearance.
- `outline` when you need a border-like effect that does not affect layout.
- `border-radius` when you want rounded or circular corners.

Understanding when to use each property gives you greater flexibility when styling images.

---

# Summary

CSS offers several effective ways to add borders around images.

The `border` shorthand provides a quick way to define border width, style, and color. Individual border properties allow each side of an image to be customized independently. The `outline` property creates a border-like effect without changing the element's dimensions, while `border-radius` rounds the corners for a softer appearance.

These properties can be used individually or combined to create a wide variety of image border styles, giving you precise control over the presentation of images in your web designs.
