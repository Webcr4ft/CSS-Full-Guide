# What Is a CSS Reset, and What Are Some Common Examples?

A **CSS reset** is a stylesheet that removes all or some of the default formatting that web browsers apply to HTML elements.

For example, you might have noticed that certain elements, like paragraphs and headings, already have margins by default even if you don't define them explicitly in your custom stylesheets.

You will also see this with various properties in a wide range of HTML elements.

Different browsers may also apply different default styles to HTML elements. The default styles in **Google Chrome** may not be exactly the same as in **Mozilla Firefox** or **Microsoft Edge**.

This can result in **inconsistent styles across browsers**, which you should avoid as much as possible.

## Why Use a CSS Reset?

To handle this, a CSS reset removes the default styles.

By removing all or some of the default styles, you can get a **consistent baseline** for your design and minimize potential inconsistencies across browsers and devices.

Removing default styles can also make the styling process easier because you will only see the styles that you have applied explicitly in your custom stylesheets.

There are **two main approaches** to CSS resets:

1. **Custom CSS resets**
2. **Third-party CSS resets**

## Custom CSS Resets

Custom CSS resets are stylesheets that you create from scratch to fit the needs of your project.

This way, you can control the specific styles that will be reset with a lot of room for flexibility.

However, you also need to invest time to **develop and maintain** the stylesheets.

Here's an example of a very common CSS rule for resetting the margin and padding of all HTML elements:

    <link rel="stylesheet" href="styles.css">

    <h1>Example Heading</h1>
    <p>This is a paragraph.</p>

    * {
      margin: 0;
      padding: 0;
    }

It's usually written at the **top of the CSS stylesheet**.

The asterisk (`*`) selector is a **wildcard selector** that matches all HTML elements, so they will have:

- A default margin of `0`.
- A default padding of `0` on all four sides.

This will give you a **starting point**, and then you can customize the elements using more specific CSS selectors further down in the stylesheet.

### Resetting Specific Elements

You can use this approach to select any HTML element and reset its default styles.

Just create a custom stylesheet and use the appropriate CSS selectors to match the elements and set the styles.

For example:

    h1,
    h2,
    h3,
    p {
      margin: 0;
    }

This allows you to reset only the elements you actually need to customize.

## Third-Party CSS Resets

Custom resets can be a **time-intensive process**.

If you want to save time, you can also use a **third-party CSS reset**.

These stylesheets are already pre-built, so you can download them and add them to your project directly.

### Normalize.css

A great example of a third-party CSS reset is **Normalize.css**.

This stylesheet normalizes styles for a wide range of HTML elements while still keeping some useful default styles, especially those that are important for **accessibility**.

It also corrects common bugs and style inconsistencies.

### sanitize.css

Another option is **sanitize.css**.

This is a CSS library that you can use to ensure that default styles will be consistent across all major modern browsers.

This library is developed alongside Normalize.css, so they evolve together.

It also has individual stylesheets that you can download for specific purposes, such as:

- **Normalizing forms**
- **Normalizing typography**

## Choosing a CSS Reset

There are many options available, but you should choose the ones that best fit the needs of your project.

You can also **combine both approaches** by using third-party CSS resets together with your own custom resets.

For example:

    /* Third-party reset */
    /* Your custom reset */
    /* Your project styles */

This gives you the convenience of a pre-built reset while still allowing you to customize specific elements for your project.

## Accessibility Considerations

When working with CSS resets, it's also important to take **accessibility** into account.

Your web application should be accessible to everyone.

So, you shouldn't reset styles that might be helpful for **screen readers or other assistive technologies**.

For example, removing all visual focus styles from interactive elements can make keyboard navigation much harder.

Always make sure that your reset doesn't remove important accessibility features.

## Performance Considerations

You should also consider the impact that additional stylesheets may have on your application's **performance**.

External stylesheets have to be downloaded and processed before the custom styles can be applied.

For smaller projects, this may not be a major concern. However, it's still good practice to avoid including unnecessary styles.

## Conclusion

By removing the default styles, CSS resets give you a **blank starting point** for implementing your design.

This results in a more **uniform and consistent user experience** across browsers and devices.

Whether you choose a custom reset, a third-party reset, or a combination of both, understanding how CSS resets work will help you create more predictable and maintainable stylesheets.
