# Font Families

## What Are Font Families and How Do They Work?

A **font family** is a group of fonts that share a common design.

All fonts that belong to the same family are based on the same core typeface, but they can have variations in:

- Style
- Weight
- Width

You can think of fonts in the same family as **siblings**. They share similar characteristics but also have some differences.

### Example

Arial is a font family that includes variations such as:

- Arial
- Arial Bold
- Arial Italic

---

# Setting Font Families in CSS

In CSS, you can set the font family using the **`font-family`** property.

### Example

HTML:

<link rel="stylesheet" href="styles.css">
<p id="arial-font">Example paragraph using Arial font.</p>
<p>Paragraph not using Arial font.</p>

CSS:

#arial-font {
  font-family: Arial;
}

The paragraph with the `id` of `arial-font` will use the **Arial** font.

---

# Fallback Fonts

What happens if the specified font family is not available?

You can specify multiple font families in order of priority, from highest to lowest.

Separate each font family with a comma.

Example:

#specified-font {
  font-family: Arial, Lato;
}

In this example:

- Arial is the primary font.
- Lato is the fallback font.

HTML:

<link rel="stylesheet" href="styles.css">
<p id="specified-font">Example paragraph using specified fonts.</p>
<p>Paragraph not using specified fonts.</p>

CSS:

#specified-font {
  font-family: Arial, Lato;
}

The browser will:

1. Try to use Arial.
2. If Arial is not available, try Lato.

---

# How Font Fallback Works

The font selection process does not simply stop after checking whether the first font is available.

The font family is chosen **one character at a time**.

If a font does not contain a specific character, the browser can look for that character in the lower-priority fonts.

For example:

Arial → Lato

If Arial is missing a particular character:

Character
→ Arial does not have it
→ Browser checks Lato
→ Lato provides the character

This allows text to remain properly displayed even when a particular font does not contain every character needed.

---

# Generic Font Families

In web development, you will also encounter **generic font families**.

A generic font family is a general category of font that tells the browser what type of font should be used when higher-priority fonts are unavailable.

The browser replaces the original font with the most appropriate font it can find based on the generic font family specified.

Common generic font families include:

- `serif`
- `sans-serif`
- `monospace`
- `cursive`
- `fantasy`

There are also other generic options available.

---

# Common Generic Font Families

## `serif`

A font category with decorative strokes at the ends of characters.

Example:

font-family: serif;

---

## `sans-serif`

A font category without decorative strokes at the ends of characters.

Example:

font-family: sans-serif;

---

## `monospace`

A font category where characters generally occupy the same amount of horizontal space.

Example:

font-family: monospace;

Monospace fonts are commonly used for:

- Code
- Programming examples
- Terminal interfaces

---

## `cursive`

A font category designed to resemble handwriting.

Example:

font-family: cursive;

---

## `fantasy`

A decorative font category intended for stylistic or artistic purposes.

Example:

font-family: fantasy;

---

# Using Multiple Font Families

You can combine specific fonts with a generic font family.

Example:

HTML:

<link rel="stylesheet" href="styles.css">
<p id="specified-font">Example paragraph using specified fonts.</p>
<p>Paragraph not using specified fonts.</p>

CSS:

#specified-font {
  font-family: Arial, Lato, sans-serif;
}

The browser follows the font list from left to right.

### Priority

1. Arial
2. Lato
3. sans-serif

The browser first tries to use **Arial**.

If Arial is unavailable, it tries **Lato**.

If neither Arial nor Lato is available, the browser uses an appropriate `sans-serif` font from those installed on the user's system.

---

# Always Include a Generic Font Family

You should always include a **generic font family at the end** of your `font-family` list.

Example:

font-family: Arial, Lato, sans-serif;

Recommended structure:

font-family: Primary Font, Fallback Font, Generic Family;

Example:

font-family: Arial, Lato, sans-serif;

The generic font family acts as the final fallback.

---

# Why Generic Fallbacks Matter

A generic fallback helps ensure that your text can still be displayed if your preferred fonts are unavailable.

However, the generic font may look different from the font you originally intended to use.

For example:

Your design
→ Arial

If Arial is unavailable
→ Lato

If Lato is unavailable
→ sans-serif

Because the final fallback font may look different, it is useful to check how your fallback fonts appear on different browsers.

---

# Web-Safe Fonts

**Web-safe fonts** are font families that are usually installed on most devices.

Because they are available on many systems, they are very likely to be found and rendered correctly for most users.

Using web-safe fonts can help provide a more consistent user experience across different devices.

You will learn more about web-safe fonts in later lessons.

---

# Font-Family Priority

The order of fonts in your CSS matters.

Example:

font-family: Arial, Lato, sans-serif;

The priority is:

1. Arial
2. Lato
3. sans-serif

The browser starts with the highest-priority option and moves down the list when necessary.

---

# Quick Summary

**Font Family**
→ A group of fonts that share a common design.

**Font**
→ A specific variation of a typeface.

**Font Variation**
→ A version of a font with different characteristics such as weight, style, or width.

**`font-family`**
→ The CSS property used to specify which font should be used.

**Fallback Font**
→ An alternative font used when a higher-priority font is unavailable.

**Generic Font Family**
→ A general font category used as a fallback.

Common generic font families:

- `serif`
- `sans-serif`
- `monospace`
- `cursive`
- `fantasy`

**Web-Safe Font**
→ A font commonly installed on many devices, making it more likely to display consistently.

---

# Key Memory Trick

font-family: Arial, Lato, sans-serif;

Means:

Try Arial first
→ If unavailable, try Lato
→ If unavailable, use sans-serif

### Remember

Font Family
= Group of related fonts

font-family
= CSS property for choosing fonts

Fallback
= Backup font

Generic Font
= General category used as a final fallback

Web-Safe Font
= Font commonly available on many devices

Always put the generic font family at the end of the font-family list.

---

# Final Takeaway

Font families are essential in web design.

The CSS `font-family` property allows you to control the appearance of text.

By specifying multiple fonts and including a generic font family as a fallback, you can make your website's typography more reliable across different devices and browsers.
