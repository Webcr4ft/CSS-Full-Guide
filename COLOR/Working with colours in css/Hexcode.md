# What Are Hex Codes, and How Do They Work in CSS?

**Hex codes** are one of the most common ways to define colors in CSS.

A hex code is a short way of representing a color using the **RGB color model**.

Hex codes are useful when you need **precise and consistent colors** in a website.

---

# What Is a Hex Code?

**Hex** is short for **hexadecimal**.

Hexadecimal is a **base-16 numbering system**.

It uses:

```text
0 1 2 3 4 5 6 7 8 9 A B C D E F
```

The letters `A` to `F` represent values after `9`.

A CSS hex color starts with a **hash symbol (`#`)**, followed by **six characters**.

Example:

```css
#FF5733
```

---

# How Hex Codes Represent RGB

A six-character hex code represents three RGB values:

```text
#RRGGBB
```

Where:

```text
RR = Red
GG = Green
BB = Blue
```

Each color uses **two hexadecimal characters**.

For example:

```text
#FF5733
```

can be broken down into:

```text
FF = Red
57 = Green
33 = Blue
```

---

# Hexadecimal Value Range

Each pair can range from:

```text
00 → Lowest intensity
FF → Highest intensity
```

So:

```text
00 = No or very little of that color
FF = Full intensity of that color
```

The higher the value, the more of that color is present.

---

# Common Hex Colors

## Black

```css
#000000
```

Breakdown:

```text
Red   = 00
Green = 00
Blue  = 00
```

All colors have no intensity, so the result is **black**.

---

## White

```css
#FFFFFF
```

Breakdown:

```text
Red   = FF
Green = FF
Blue  = FF
```

All colors are at full intensity, so the result is **white**.

---

# Using Hex Codes in CSS

The basic syntax is:

```css
element {
  color: #RRGGBB;
}
```

`#RRGGBB` is just a placeholder.

You replace it with the actual hex color you want.

For example:

```css
p {
  color: #FF0000;
}
```

This makes the paragraph text red.

---

# Example With Different Hex Colors

HTML:

```html
<link rel="stylesheet" href="styles.css" />

<h1>This is a heading.</h1>

<p>This is a paragraph.</p>
```

CSS:

```css
h1 {
  color: #FF5733;
}

p {
  background-color: #4CAF50;
}
```

---

# Understanding `#FF5733`

The color:

```css
#FF5733
```

can be broken down into:

```text
FF = Red
57 = Green
33 = Blue
```

So:

- `FF` is the highest value for red.
- `57` is a moderate amount of green.
- `33` is a smaller amount of blue.

The result is a **reddish-orange color**.

---

# Understanding `#4CAF50`

The color:

```css
#4CAF50
```

can be broken down into:

```text
4C = Red
AF = Green
50 = Blue
```

So:

- `4C` is a low amount of red.
- `AF` is a strong amount of green.
- `50` is a moderate amount of blue.

The result is a **shade of green**.

---

# Why Are Hex Codes Popular?

Hex codes are popular because they are:

- **Precise**
- **Consistent**
- **Easy to use**
- **Widely supported**
- Good for controlling exact shades

They allow you to choose a very specific color instead of being limited to predefined named colors.

---

# Hex Codes and Design Software

Design programs such as **Adobe Photoshop** and **Figma** can provide hex codes for the colors you select.

For example, if you choose a specific color in a design program, it may give you:

```text
#007BFF
```

You can copy that value and use it directly in your CSS.

This makes it easy to keep the colors in your website consistent with your design.

---

# Where Can You Use Hex Codes?

Hex codes can be used for many CSS properties that accept colors.

For example:

- Text
- Backgrounds
- Borders
- Buttons
- Headings
- Other visual elements

Example:

```html
<link rel="stylesheet" href="styles.css" />

<button>Example</button>
```

```css
body {
  background-color: #F0F0F0;
}

button {
  background-color: #007BFF;
  color: #FFFFFF;
}
```

Here:

```text
#F0F0F0 = Light gray
#007BFF = Blue
#FFFFFF = White
```

Using the same hex codes throughout your website helps keep the design **consistent**.

---

# Hex Shorthand

Sometimes you will see hex codes written using only **three characters** instead of six.

For example:

```css
#FFF
```

instead of:

```css
#FFFFFF
```

This is called **hex shorthand**.

---

# When Can Hex Shorthand Be Used?

You can only use the three-character shorthand when both characters in each pair are the same.

For example:

```text
#FFFFFF
```

can become:

```text
#FFF
```

because:

```text
FF FF FF
```

has matching characters in every pair.

Similarly:

```text
#000000
```

can become:

```text
#000
```

---

# Examples of Shorthand

Full form:

```css
#FFFFFF
```

Shorthand:

```css
#FFF
```

Both mean **white**.

Full form:

```css
#000000
```

Shorthand:

```css
#000
```

Both mean **black**.

---

# Example Using Shorthand

HTML:

```html
<link rel="stylesheet" href="styles.css" />

<h2>This is a heading.</h2>
```

CSS:

```css
body {
  background-color: #000;
}

h2 {
  color: #FFF;
}
```

Here:

```text
#000 = #000000 = Black
#FFF = #FFFFFF = White
```

---

# When Can't You Use Shorthand?

A six-character hex code cannot always be shortened.

For example:

```text
#FF5733
```

cannot become a three-character hex code because the pairs are:

```text
FF
57
33
```

Only `FF` has matching characters.

The other pairs don't.

Therefore, you must keep:

```css
#FF5733
```

---

# How Many Colors Can Hex Codes Represent?

Hex colors can represent **over 16 million different colors**.

This gives you a huge range of colors to choose from.

That's why hex codes are useful when you need:

- Specific branding colors.
- Exact shades.
- Consistent colors.
- Colors that aren't available as named colors.

---

# Hex Codes vs Named Colors

Named colors use words:

```css
color: red;
```

Hex codes use hexadecimal values:

```css
color: #FF0000;
```

Named colors are easier to remember, but they offer fewer choices.

Hex codes give you much more **precision and control**.

---

# When Should You Use Hex Codes?

Use hex codes when:

- You need a **specific color**.
- You are following a **brand color**.
- You want consistent colors throughout a website.
- You are copying colors from **Figma or Photoshop**.
- A named color isn't close enough to the shade you need.
- You want precise control over your design.

---

# Key Things to Remember

> **A hex code is a six-character hexadecimal value used to represent a color in the RGB color model.**

A hex color starts with:

```text
#
```

Then comes six characters:

```text
#RRGGBB
```

Where:

```text
RR = Red
GG = Green
BB = Blue
```

Each pair ranges from:

```text
00 → Lowest intensity
FF → Highest intensity
```

Examples:

```css
#000000 = Black
#FFFFFF = White
#FF0000 = Red
#00FF00 = Green
#0000FF = Blue
```

Three-character shorthand can be used when each pair contains matching characters:

```text
#FFFFFF → #FFF
#000000 → #000
```

Hex codes are popular because they provide **precision, consistency, and access to over 16 million colors**.

## Main Points

- **Hex** means hexadecimal.
- Hexadecimal uses `0-9` and `A-F`.
- Hex colors start with `#`.
- A full hex color uses **6 characters**.
- `#RRGGBB` represents **Red, Green, and Blue**.
- Each pair ranges from `00` to `FF`.
- Hex codes provide precise color control.
- Hex shorthand uses **3 characters** when possible.
- Hex codes are commonly used for **text, backgrounds, borders, buttons, and branding**.
- Hex codes are especially useful when you need **exact and consistent colors**.
