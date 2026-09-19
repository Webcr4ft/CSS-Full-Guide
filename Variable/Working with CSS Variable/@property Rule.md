# What Is the @property Rule, and How Does It Work with Fallbacks?

The `@property` rule is a powerful CSS feature that allows developers to define custom properties with greater control over their behavior, including how they animate and their initial values.

This rule provides a way to enhance the functionality of CSS custom properties and offers more flexibility in their application.

## Basic Syntax

The basic syntax of the `@property` rule is as follows:

`@property --property-name {
  syntax: '<type>';
  inherits: true | false;
  initial-value: <value>;
}`

The `--property-name` is the name of the custom property you're defining. Like all custom properties, it must start with two dashes.

* `syntax` defines the type of the property, which can be things like `<color>`, `<length>`, `<number>`, `<percentage>`, or more complex types.
* `inherits` specifies whether the property should inherit its value from its parent element.
* `initial-value` sets the default value of the property.

## A Practical Example

Here's a practical example of using the `@property` rule:

### HTML

`<link rel="stylesheet" href="styles.css">

<button class="button">Click Me</button>`

### CSS

`@property --main-color {
  syntax: '<color>';
  inherits: false;
  initial-value: #3498db;
}

.button {
  background-color: var(--main-color);
}`

In this example, we're defining a custom property `--main-color` as a color value, setting it to not inherit, and giving it an initial value of `#3498db`.

## Animating Custom Properties

One of the key benefits of the `@property` rule is that it allows for animation of custom properties, which wasn't possible before.

### HTML

`<link rel="stylesheet" href="styles.css">

<div class="gradient-box"></div>`

### CSS

`@property --gradient-angle {
  syntax: '<angle>';
  inherits: false;
  initial-value: 0deg;
}

.gradient-box {
  width: 100px;
  height: 100px;
  background: linear-gradient(var(--gradient-angle), red, blue);
  transition: --gradient-angle 0.5s;
}

.gradient-box:hover {
  --gradient-angle: 90deg;
}`

The code above creates a gradient that smoothly animates when the element is hovered over, something that wasn't achievable with standard custom properties.

## Working with Fallbacks

Fallbacks are crucial in CSS to ensure that styles degrade gracefully in browsers that don't support certain features.

With the `@property` rule, fallbacks work on two levels:

* The fallback for the `@property` rule itself.
* The fallback when using the custom property.

## Fallback for Unsupported Browsers

For browsers that don't support the `@property` rule, you can provide a fallback by declaring the custom property in the traditional way:

### CSS

`:root {
  --main-color: #3498db;
}

@property --main-color {
  syntax: '<color>';
  inherits: false;
  initial-value: #3498db;
}

body {
  background-color: var(--main-color);
}`

In this case, browsers that support `@property` will use the more strictly defined version, while others will fall back to the standard custom property declaration.

## Fallbacks with the var() Function

When using the custom property, you can provide a fallback value using the `var()` function, just as you would with standard custom properties:

### HTML

`<link rel="stylesheet" href="styles.css">

<button class="button">Click Me</button>`

### CSS

`.button {
  background-color: var(--main-color, #3498db);
}`

This ensures that even if the `--main-color` property is not defined or is invalid, the button will still have a background color.

## Type-Safe Fallbacks

The `@property` rule also allows for more complex fallback scenarios.

For instance, you can use it to provide type-safe fallbacks:

### HTML

`<link rel="stylesheet" href="styles.css">

<div class="box">Colored box</div>`

### CSS

`@property --padding {
  syntax: '<length>';
  inherits: false;
  initial-value: 10px;
}

.box {
  width: 100px;
  height: 100px;
  background-color: darkred;
  color: white;
  padding: var(--padding);
}`

In this case, if someone tries to set `--padding` to an invalid value, like a color, the browser will fall back to the initial value of `10px`, maintaining type safety.

## Browser Support

The CSS `@property` rule is considered widely available across all major modern browser engines, such as Chrome, Edge, Opera, Firefox, and Safari, since early 2024.

If you want to support earlier browsers, you need to provide fallback CSS as explained above.

## Conclusion

In conclusion, the `@property` rule represents a significant advancement in how we work with custom properties in CSS.

It provides more control and enables new possibilities like animation of custom properties.

However, it's important to use it judiciously and always provide appropriate fallbacks to ensure a good experience across all browsers.

As with any web technology, the key is to enhance the experience for browsers that support it while ensuring basic functionality for those that don't.
