# What Is the @font-face At-Rule, and How Does It Work?

## What Is an At-Rule?

- An **at-rule** is a CSS statement that gives instructions to the browser.
- At-rules can be used for things such as:
  - Media queries
  - Keyframes
  - Custom fonts
  - Other stylesheet instructions

- At-rules begin with the `@` symbol.

Examples:
  @font-face
  @media
  @keyframes

---

# What Is @font-face?

- The `@font-face` at-rule allows you to define and use a **custom font** in your website.
- You can specify:
  - The font file
  - Font format
  - Font family name
  - Font weight
  - Font style
  - Font technology

Basic syntax:

  @font-face {
    /* Descriptors */
  }

- The information inside `{ }` is made up of **descriptors**.
- Descriptors tell the browser how the custom font should be used.

---

# The font-family Descriptor

- The `font-family` descriptor gives your custom font a name.
- You use this name later in your CSS to apply the font.

Example:

  @font-face {
    font-family: "MyCustomFont";
  }

- Here, `"MyCustomFont"` is the name of the custom font.

You can then use it like this:

  body {
    font-family: "MyCustomFont";
  }

### Important

The name you give to `font-family` inside `@font-face` is the name you use when applying the font elsewhere in your stylesheet.

---

# The src Descriptor

- For an `@font-face` rule to be valid, you also need to specify the `src` descriptor.
- `src` tells the browser where to find the font resources.
- It can contain:
  - URLs pointing to font files
  - Locally installed font face names
  - Information about the font format
  - Information about the font technology

Example:

  @font-face {
    font-family: "MyCustomFont";
    src: url("path/to/font.woff2"),
      url("path/to/font.woff"),
      url("path/to/font.otf");
  }

- Multiple font resources can be separated by commas.
- Putting each resource on a separate line makes the CSS easier to read.

---

# The url() Function

- The `url()` function is used to reference a file or resource in CSS.
- With `@font-face`, it is commonly used to reference font files.

Example:

  src: url("path/to/font.woff2");

- The file path goes inside the parentheses.
- The path is normally written inside quotation marks.
- Include the file extension, such as:
  - `.woff2`
  - `.woff`
  - `.otf`

---

# Font Formats

- You can optionally specify the format of each font resource.
- The format acts as a **hint to the browser** about the type of font file.

Example:

  url("path/to/font.woff2") format("woff2")

- If the format is omitted:
  - The browser downloads the resource.
  - The browser determines the format after downloading it.

- If the format is invalid:
  - The browser will not download the resource.

---

# Common Font Formats

Some possible font formats include:

- `collection`
- `embedded-opentype`
- `opentype`
- `svg`
- `truetype`
- `woff`
- `woff2`

---

# Using format()

You can specify the format using the `format()` function.

Example:

  @font-face {
    font-family: "MyCustomFont";
    src: url("path/to/font.woff2") format("woff2"),
      url("path/to/font.otf") format("opentype"),
      url("path/to/font.woff") format("woff");
  }

This example provides three font resources:

1. A WOFF2 font
2. An OpenType font
3. A WOFF font

---

# WOFF and WOFF2

## WOFF

- WOFF stands for **Web Open Font Format**.
- It is designed for use with web fonts.

## WOFF2

- WOFF2 is a newer version of the WOFF format.
- The main difference between WOFF and WOFF2 is the **compression algorithm** used to compress the font data.

---

# OpenType

- OpenType is a scalable computer font format.
- It was developed by **Microsoft and Adobe**.
- It supports additional font features.
- It is widely supported across major operating systems.

---

# Font Technology

- You can also specify the **technology** used by a font resource.
- This is optional.

Example:

  @font-face {
    font-family: "MyCustomFont";
    src: url("path/to/font.woff2") format("woff2"),
      url("path/to/font.otf") format("opentype") tech(color-COLRv1),
      url("path/to/font.woff") format("woff");
  }

- In this example, the second font resource specifies:
  `tech(color-COLRv1)`

---

# Complete Example

  @font-face {
    font-family: "MyCustomFont";
    src: url("path/to/font.woff2") format("woff2"),
      url("path/to/font.woff") format("woff"),
      url("path/to/font.otf") format("opentype");
  }

  body {
    font-family: "MyCustomFont";
  }

### What happens?

1. `@font-face` defines a custom font.
2. `font-family` gives the font the name `"MyCustomFont"`.
3. `src` tells the browser where the font files are.
4. `format()` tells the browser what format each file uses.
5. `body` uses `"MyCustomFont"` as its font.

---

# Why Use @font-face?

`@font-face` allows you to use fonts that may not already be installed on the user's device.

This gives you more control over the typography and visual design of your website.

---

# Key Things to Remember

- `@font-face` → defines a custom font.
- `font-family` → gives the custom font a name.
- `src` → specifies where the font resources are located.
- `url()` → references the font file.
- `format()` → tells the browser the font format.
- `tech()` → optionally specifies the font technology.
- `woff` → Web Open Font Format.
- `woff2` → newer WOFF format with a different compression algorithm.
- `opentype` → scalable font format developed by Microsoft and Adobe.

# Memory Trick

**@font-face → Name + Source + Format + Technology**

  @font-face {
    font-family: "MyCustomFont";        /* Name */
    src: url("font.woff2") format("woff2"); /* Source + Format */
  }

  body {
    font-family: "MyCustomFont";
  }

# Quick Summary

`@font-face` lets you define a custom font and use it on your website.

The basic structure is:

  @font-face {
    font-family: "MyCustomFont";
    src: url("font.woff2") format("woff2");
  }

Then apply it normally:

  body {
    font-family: "MyCustomFont";
  }

The most important descriptors to understand are:

- `font-family`
- `src`
- `format()`
- `tech()`
