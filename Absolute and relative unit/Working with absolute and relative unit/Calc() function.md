# CSS Repository: The `calc()` Function

---

# What Is the `calc()` Function in CSS?

The `calc()` function is a built-in CSS function that allows you to perform mathematical calculations directly inside your stylesheet.

Instead of assigning fixed values, you can calculate values dynamically using different units such as pixels (`px`), percentages (`%`), `em`, `rem`, `vw`, `vh`, and more.

This makes your layouts more **flexible**, **responsive**, and **easier to maintain**.

---

# Why Use `calc()`?

Normally, you might write:

```css
width: 300px;
```

This gives the element a fixed width.

But sometimes you need a value that's based on multiple measurements.

For example:

- Half of the parent's width minus 20 pixels
- Full screen height minus a navigation bar
- Equal spacing between elements
- Responsive layouts that combine different units

This is where `calc()` becomes useful.

---

# What Is a Function?

A function is a reusable block of code that performs a specific task.

CSS includes several built-in functions, and `calc()` is one of them.

Functions are **called** by writing their name followed by parentheses.

General syntax:

```css
function(argument1, argument2)
```

Example:

```css
calc(100% - 20px)
```

Notice that there is **no space** between the function name and the opening parenthesis.

Correct:

```css
calc(...)
```

Incorrect:

```css
calc (...)
```

---

# What Is an Argument?

An **argument** is the value passed into a function.

The `calc()` function only accepts **one argument**.

That argument is an **expression**.

Syntax:

```css
calc(expression)
```

---

# What Is an Expression?

An expression is a combination of values and mathematical operators that produces a result.

Example:

```css
50% - 20px
```

Inside `calc()`:

```css
calc(50% - 20px)
```

The browser evaluates the expression and assigns the result to the CSS property.

---

# Example: Dynamic Width

## HTML

```html
<link rel="stylesheet" href="styles.css">

<div>Hello, World!</div>
```

## CSS

```css
div {
  color: white;
  background-color: #1b1b32;
  width: calc(50% - 20px);
}
```

---

# How It Works

The expression is:

```css
50% - 20px
```

Step 1:

```
Find 50% of the parent's width.
```

Step 2:

```
Subtract 20 pixels.
```

The final value becomes the width of the element.

If the parent changes size, the calculation is performed again automatically.

---

# Mathematical Operators

`calc()` supports four mathematical operators.

## Addition

```css
calc(100% + 20px)
```

---

## Subtraction

```css
calc(100% - 20px)
```

---

## Multiplication

```css
calc(2 * 50px)
```

---

## Division

```css
calc(100% / 2)
```

---

# Supported Value Types

You can calculate values using:

- Pixels (`px`)
- Percentages (`%`)
- `em`
- `rem`
- `vw`
- `vh`
- Angles
- Time values
- Numbers
- Colors (in supported CSS color functions)

You can even combine different units.

Example:

```css
calc(100% - 2rem)
```

---

# Operator Precedence

`calc()` follows normal mathematical rules.

Example:

```css
calc(100% - 20px * 2)
```

Multiplication happens before subtraction.

If you want a different order, use parentheses.

Example:

```css
calc((100% - 20px) * 2)
```

---

# Combining Different Units

One of the biggest advantages of `calc()` is mixing units.

Example:

```css
width: calc(100% - 40px);
```

or

```css
height: calc(100vh - 80px);
```

This would be impossible without `calc()`.

---

# Using CSS Variables

`calc()` also works with CSS variables.

Example:

```css
:root {
  --spacing: 20px;
}

.container {
  width: calc(100% - var(--spacing));
}
```

---

# Best Practice: Spaces Around `+` and `-`

Always leave spaces around addition and subtraction.

Incorrect:

```css
calc(100%-30px)
```

Correct:

```css
calc(100% - 30px)
```

---

# Multiplication and Division

Spaces are not required but are strongly recommended.

Example:

```css
calc(5 * 50px)
```

instead of

```css
calc(5*50px)
```

---

# Using Zero

When zero represents a length, include its unit.

Incorrect:

```css
calc(100% - 0)
```

Correct:

```css
calc(100% - 0px)
```

---

# Multiplication Rules

When using multiplication:

One operand must be **unitless**.

Incorrect:

```css
calc(5px * 50px)
```

Correct:

```css
calc(5 * 50px)
```

or

```css
calc(5px * 50)
```

---

# Division Rules

For division:

The **right operand** must be unitless.

Incorrect:

```css
calc(50% / 5%)
```

Correct:

```css
calc(50% / 5)
```

---

# Nested `calc()` Functions

You can place one `calc()` inside another.

Example:

```css
width: calc(100% - calc(2 * 20px));
```

This is useful for more advanced layouts.

---

# Common Use Cases

Use `calc()` for:

- Responsive layouts
- Dynamic widths
- Dynamic heights
- Flexible spacing
- Full-screen layouts
- Sidebar layouts
- Navigation offsets
- CSS variables
- Grid and Flexbox sizing

---

# Advantages

- Creates dynamic property values
- Supports multiple units
- Makes layouts responsive
- Reduces hard-coded values
- Easy to maintain
- Works with CSS variables
- Automatically recalculates when the viewport changes

---

# Best Practices

- Always leave spaces around `+` and `-`.
- Include units when using zero as a length.
- Ensure one operand is unitless when multiplying or dividing.
- Use parentheses to control calculation order.
- Combine `calc()` with CSS variables for reusable code.
- Use `calc()` when fixed values are too restrictive.

---

# Summary

The `calc()` function allows CSS to perform mathematical calculations directly within property values.

It is especially useful for creating responsive and flexible layouts by combining different units such as percentages, pixels, viewport units, and relative units.

By understanding expressions, operators, arguments, and calculation rules, you can write cleaner, more dynamic CSS that adapts automatically to different screen sizes and layouts.
