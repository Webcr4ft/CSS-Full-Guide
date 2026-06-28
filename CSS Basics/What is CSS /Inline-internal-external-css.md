# What Are Inline, Internal, and External CSS, and When Should You Use Each One?

CSS can be applied to a webpage in **three main ways**:

1. Inline CSS
2. Internal CSS
3. External CSS

Each method has its own **use case, advantages, and limitations**. Knowing when to use each one is essential for writing **clean, efficient, and maintainable** code.

---

# Inline CSS

**Inline CSS** is written directly inside an HTML element using the `style` attribute. It only affects the specific element it is applied to.

## Syntax

```html
<p style="color: green;">This is an inline-styled paragraph.</p>
```

### Explanation

In this example, the `style` attribute changes the paragraph text color to **green**.

## When to Use Inline CSS

- Quick, one-time styling.
- Testing styles.
- Overriding a style for a single element.

## Advantages

- Easy to apply.
- Affects only one element.
- Useful for quick fixes.

## Disadvantages

- Makes HTML messy.
- Difficult to maintain.
- Cannot be reused.
- Not recommended for large projects.

> **Best Practice:** Avoid inline CSS whenever possible. Use **internal** or **external CSS** instead.

---

# Internal CSS

**Internal CSS** is written inside the `<style>` element, which is placed in the `<head>` section of an HTML document.

It styles the entire webpage.

## Syntax

```html
<head>
  <style>
    p {
      color: blue;
    }
  </style>
</head>

<body>
  <p>This paragraph is styled using internal CSS.</p>
</body>
```

### Explanation

The CSS rule applies the color **blue** to **every `<p>` element** on the page.

## When to Use Internal CSS

- Styling a single webpage.
- Small projects.
- Single-page websites.
- When the styles won't be reused elsewhere.

## Advantages

- Styles an entire page.
- No separate CSS file required.
- Easier than inline CSS for multiple elements.

## Disadvantages

- Cannot be reused on other pages.
- HTML and CSS are mixed together.
- Harder to maintain in large projects.

---

# External CSS

**External CSS** is written inside a separate `.css` file and connected to the HTML document using the `<link>` element inside the `<head>` section.

This is the **recommended** method for professional web development.

## HTML

```html
<head>
  <link rel="stylesheet" href="styles.css">
</head>

<body>
  <p>This paragraph is styled using external CSS.</p>
</body>
```

## CSS (`styles.css`)

```css
p {
  color: red;
}
```

### Explanation

Every `<p>` element linked to `styles.css` will display **red** text.

---

# Understanding the `<link>` Element

The `<link>` element connects an HTML document to external resources.

Example:

```html
<link rel="stylesheet" href="styles.css">
```

## `rel`

The `rel` attribute tells the browser the relationship between the current document and the linked file.

Example:

```html
rel="stylesheet"
```

This means the linked file is a CSS stylesheet.

## `href`

The `href` attribute specifies **where the file is located**.

Example:

```html
href="styles.css"
```

The browser looks for the file named `styles.css` and loads it.

---

# When to Use External CSS

Use external CSS when:

- Building multi-page websites.
- Working on medium or large projects.
- Sharing styles across many pages.
- Keeping HTML and CSS separate.

---

# Advantages of External CSS

- Reusable across multiple pages.
- Cleaner HTML.
- Easier maintenance.
- Better organization.
- Scalable for large projects.
- Promotes separation of concerns.

---

# Separation of Concerns

A professional website separates responsibilities:

- **HTML** → Structure
- **CSS** → Styling
- **JavaScript** → Behavior

Keeping them separate makes projects easier to maintain and scale.

---

# Comparison Table

| CSS Type | Best For | Reusable | Recommended |
|-----------|----------|----------|-------------|
| **Inline CSS** | One element | ❌ No | Rarely |
| **Internal CSS** | One webpage | ❌ No | Sometimes |
| **External CSS** | Multiple webpages | ✅ Yes | ✅ Yes |

---

# Key Takeaways

- Use **Inline CSS** for quick, one-time styling.
- Use **Internal CSS** when styling only one page.
- Use **External CSS** for almost every real-world project.

> **Most of the time, External CSS should be your first choice because it keeps your code clean, organized, reusable, and easy to maintain.**
