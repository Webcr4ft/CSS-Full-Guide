# Web Safe Fonts

## What Are Web Safe Fonts?

**Web-safe fonts** are fonts that are very likely to already be installed on a user's computer or device.

They are widely supported across different:

- Operating systems
- Web browsers
- Devices

Because they are commonly available, they are more likely to be rendered and displayed consistently.

---

# How Browsers Handle Fonts

Browsers are responsible for interpreting and displaying fonts on websites.

When a browser needs to render a font, it tries to find the required font file on the user's system.

The process is roughly:

Browser needs a font
→ Checks the user's system
→ Font is found
→ Browser renders the font

But what happens if the font is not found?

The browser will usually fall back to another available system font.

This ensures that the content remains readable even when the specific font requested by the website is missing.

---

# Why Font Fallback Can Be a Problem

The fallback font selected by the browser may look very different from the font that was originally intended.

For example:

Website design
→ Intended font: Custom Font
→ Custom font is unavailable
→ Browser uses another font

The replacement font might have a different:

- Size
- Shape
- Width
- Spacing
- Overall appearance

This can have a significant impact on:

- Overall design
- Visual consistency
- User experience
- Brand identity

---

# How Web-Safe Fonts Help

Using web-safe fonts can make your website more consistent across different devices and platforms.

You have two main options:

## Option 1: Use Web-Safe Fonts as Primary Fonts

You can use a web-safe font directly as your main font.

Example:

font-family: Arial, sans-serif;

Because Arial is widely available, it is likely to display consistently for many users.

## Option 2: Use a Custom Font With a Web-Safe Fallback

You can use a custom font as the primary font and a web-safe font as a fallback.

Example:

font-family: "Custom Font", Arial, sans-serif;

The browser will:

1. Try to use the custom font.
2. If it is unavailable, try Arial.
3. If Arial is unavailable, use another appropriate `sans-serif` font.

This gives you more control over how your website looks when the custom font cannot be found.

---

# Web-Safe Sans-Serif Fonts

Sans-serif fonts are commonly used in web development.

They do not have the small "feet" or decorative lines at the ends of characters.

This makes them generally easy to read on screens.

Common web-safe sans-serif fonts include:

- Arial
- Verdana
- Trebuchet MS

---

# Arial

**Arial** is a widely supported sans-serif font.

Example:

Hello, World!

It has a clean and simple appearance and is commonly used for websites and other digital content.

---

# Verdana

**Verdana** is a sans-serif font designed with readability in mind.

It has:

- Wide letterforms
- Large open shapes
- A tall x-height

Example:

Hello, World!

---

# Trebuchet MS

**Trebuchet MS** is a humanist sans-serif font.

It has slightly rounded letterforms and provides a distinctive but readable appearance.

Example:

Hello, World!

---

# Web-Safe Serif Fonts

Serif fonts have small "feet" or decorative strokes at the ends of characters.

They are traditionally associated with printed materials.

However, serif fonts can also be used for web development.

Common web-safe serif fonts include:

- Times New Roman
- Georgia

---

# Times New Roman

**Times New Roman** is a classic serif font.

It has strong contrast between:

- Thick strokes
- Thin strokes

Example:

Hello, World!

It is widely available across many systems.

---

# Georgia

**Georgia** is a serif font designed with screen readability in mind.

It has:

- Relatively wide letterforms
- Clear stroke contrast
- Good readability on screens

Example:

Hello, World!

---

# Web-Safe Fonts and Consistency

Using web-safe fonts can help make your design look more consistent across:

- Devices
- Operating systems
- Browsers
- Platforms

Because these fonts are commonly available, there is less chance that a completely different fallback font will be used.

---

# Web-Safe Fonts and Accessibility

Web-safe fonts can also help with accessibility.

Simple and readable fonts can make content easier to read, including for users with visual disabilities.

Good font choices can improve:

- Readability
- Accessibility
- User experience

---

# Web-Safe Fonts and Page Load Time

Web-safe fonts can also help reduce page load time.

If a font is already installed on the user's device, the browser does not need to download that font.

This can reduce the amount of font data that needs to be loaded.

---

# Common Web-Safe Fonts

## Sans-Serif

- Arial
- Verdana
- Trebuchet MS

## Serif

- Times New Roman
- Georgia

---

# Using Web-Safe Fonts in CSS

You can use a web-safe font directly:

font-family: Arial, sans-serif;

Or use a custom font with a web-safe fallback:

font-family: "Custom Font", Arial, sans-serif;

The second example provides a fallback sequence:

Custom Font
→ Arial
→ sans-serif

---

# Quick Summary

**Web-Safe Fonts**
→ Fonts that are very likely to be installed on a user's device.

**Primary Font**
→ The font you want the website to use first.

**Fallback Font**
→ A backup font used when the primary font is unavailable.

**Sans-Serif**
→ Fonts without decorative strokes at the ends of characters.

Common web-safe sans-serif fonts:
- Arial
- Verdana
- Trebuchet MS

**Serif**
→ Fonts with decorative strokes at the ends of characters.

Common web-safe serif fonts:
- Times New Roman
- Georgia

---

# Key Memory Trick

Web-safe fonts
= Commonly installed fonts
= More consistent across devices

Custom font + fallback:

font-family: "Custom Font", Arial, sans-serif;

Means:

1. Try the custom font.
2. If unavailable → Try Arial.
3. If unavailable → Use a generic sans-serif font.

---

# Benefits of Web-Safe Fonts

Web-safe fonts can:

- Improve consistency across devices
- Reduce unexpected font changes
- Improve readability
- Support accessibility
- Reduce the need to download fonts
- Potentially improve page load performance

---

# Final Takeaway

Web-safe fonts are fonts that are widely supported and commonly available on computers and devices.

Using them as primary fonts or as fallback fonts can help create reliable and consistent user experiences across different browsers, operating systems, and devices.

They are especially useful when you want your website's typography to remain predictable even when a custom font is unavailable.
