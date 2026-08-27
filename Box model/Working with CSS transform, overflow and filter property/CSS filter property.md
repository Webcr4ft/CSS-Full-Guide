# What Is the CSS `filter` Property, and What Are Common Examples?

The CSS `filter` property is a powerful tool that allows you to apply **graphical effects** to elements on a web page.

It's particularly useful for adjusting the visual presentation of:

- **Images**
- **Backgrounds**
- **Text**

without modifying the original asset.

The `filter` property can be used to create various effects, such as:

- **Blurring**
- **Color shifting**
- **Contrast adjustments**
- **Brightness adjustments**
- **Grayscale effects**
- **Sepia effects**

Let's discuss how the `filter` property works and explore some common examples.

## Basic Syntax

The basic syntax for a `filter` property is straightforward:

    selector {
      filter: function(amount);
    }

Here:

- `function` represents the specific filter effect you want to apply.
- `amount` is typically a value that determines the intensity of the effect.

Now let's look at some common filter functions and their uses.

## Using `blur()`

The `blur()` function applies a **Gaussian blur** to the element.

The amount is specified in pixels and represents the radius of the blur.

    <link rel="stylesheet" href="styles.css">

    <img
      src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg"
      alt="A cute orange cat lying on its back."
    >

    img {
      filter: blur(2px);
    }

This CSS rule will apply a **2-pixel blur** to all images on the page.

The `blur()` effect can be useful for:

- Creating depth in your design.
- Obscuring parts of an image.
- Creating visual effects.

## Using `brightness()`

The `brightness()` function adjusts the brightness of the element.

A value of `0%` will make the element completely black, while values over `100%` will increase the brightness.

    <link rel="stylesheet" href="styles.css">

    <img
      src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg"
      alt="A cute orange cat lying on its back."
    >

    img {
      filter: brightness(150%);
    }

This CSS rule increases the brightness of the image element by **50%**.

Brightness adjustments can be used to:

- Make images stand out.
- Make an image appear brighter.
- Create a washed-out effect.

## Using `grayscale()`

The `grayscale()` function converts the element to **grayscale**.

The amount is defined as a percentage, where:

- `100%` is completely grayscale.
- `0%` leaves the image unchanged.

    <link rel="stylesheet" href="styles.css">

    <img
      src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg"
      alt="A cute orange cat lying on its back."
    >

    img {
      filter: grayscale(100%);
    }

This rule will convert the image element to **full grayscale**.

The `grayscale()` function can be used to:

- Create a vintage look.
- De-emphasize certain elements on a page.
- Create a black-and-white appearance.

## Using `sepia()`

The `sepia()` function applies a **sepia tone** to the element.

Like `grayscale()`, it uses a percentage value.

    <link rel="stylesheet" href="styles.css">

    <img
      src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg"
      alt="A cute orange cat lying on its back."
    >

    img {
      filter: sepia(80%);
    }

This rule applies an **80% sepia effect** to the image element.

The `sepia()` effect is great for creating a:

- **Vintage look**
- **Old-timey appearance**

## Using `hue-rotate()`

The `hue-rotate()` function applies a **hue rotation** to the element.

The value is defined in degrees and represents a rotation around the color circle.

    <link rel="stylesheet" href="styles.css">

    <img
      src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg"
      alt="A cute orange cat lying on its back."
    >

    img {
      filter: hue-rotate(90deg);
    }

This rule rotates the hue of the image element by **90 degrees**.

Hue rotation can be used to:

- Create psychedelic effects.
- Adjust the overall color scheme of an image.
- Experiment with different color combinations.

## Combining Multiple Filters

One of the most powerful aspects of the `filter` property is the ability to **combine multiple effects**.

You can apply several filters to the same element by separating them with spaces:

    <link rel="stylesheet" href="styles.css">

    <img
      src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg"
      alt="A cute orange cat lying on its back."
    >

    img {
      filter: contrast(150%) brightness(110%) sepia(30%);
    }

This rule applies:

- Increased contrast.
- Slightly increased brightness.
- A subtle sepia effect.

By combining filters, you can create **complex and unique visual effects** tailored to your design needs.

## Other Common Filter Functions

While we have covered some of the most common filter functions, there are others available, such as:

- `contrast()`
- `invert()`
- `saturate()`

For example:

    img {
      filter: contrast(150%);
    }

Or:

    img {
      filter: invert(100%);
    }

And:

    img {
      filter: saturate(200%);
    }

Each function provides a different way to manipulate the visual appearance of an element.

## Accessibility Considerations

As with any powerful feature, it's important to be careful with how you use filters.

Filters should enhance your design without:

- **Overwhelming your users**
- **Making content difficult to read**
- **Reducing important visual information**
- **Compromising accessibility**

For example, excessive `blur()` or `contrast()` effects could make important content difficult to understand.

Always make sure that essential information remains clear and accessible.

## Conclusion

The CSS `filter` property is a **versatile tool** that allows for creative visual manipulation of web elements.

You can use filters such as:

- `blur()`
- `brightness()`
- `grayscale()`
- `sepia()`
- `hue-rotate()`
- `contrast()`
- `invert()`
- `saturate()`

You can also combine multiple filters to create more complex visual effects.

By understanding how each filter works and using them thoughtfully, you can add creative visual effects to your websites while maintaining a clear, accessible, and user-friendly design.
