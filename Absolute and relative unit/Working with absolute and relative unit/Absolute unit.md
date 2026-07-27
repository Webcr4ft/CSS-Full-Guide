# CSS Repository: Absolute Units

---

## What Are Absolute Units in CSS?

As you design web pages, you will work with properties like **width**, **height**, **padding**, **margin**, and more. Whenever you define these properties, you must specify a **CSS length unit**.

CSS provides two categories of length units:

- **Absolute units**
- **Relative units**

This note focuses on **absolute units**.

---

## What Are Absolute Units?

**Absolute units** are fixed units of measurement in CSS. Their size does **not** change based on the screen size, the parent element, or any other factor.

Unlike **relative units**, which change depending on their context, **absolute units always represent the same CSS measurement**.

> **Key Point:**
> Absolute units are **fixed**, while relative units are **flexible**.

---

## The Most Common Absolute Unit: `px`

The most commonly used absolute unit in CSS is **`px`** (pixel).

Pixels provide **precise control** over an element's dimensions.

In CSS:

```text
1px = 1/96 of an inch
```

Although CSS defines `1px` as **1/96 of an inch**, the **actual physical size** of a pixel may vary depending on the device's display and pixel density.

---

## Example: Setting Width and Height

### HTML

```html
<link rel="stylesheet" href="styles.css">

<div class="box"></div>
```

### CSS

```css
.box {
  width: 100px;
  height: 100px;
  background-color: red;
}
```

### Explanation

The code above creates a red box that is:

- `100px` wide
- `100px` tall

No matter what device is used:

- A phone
- A tablet
- A laptop
- A desktop

the CSS dimensions remain **100px × 100px**.

---

## When Should You Use Absolute Units?

The answer depends on your design requirements.

Generally, you should use **pixels (`px`)** whenever you need **precise control** over an element's dimensions, spacing, or layout.

Common uses include:

- Width
- Height
- Padding
- Margin
- Borders
- Icons
- Small UI elements
- Precise layout adjustments

---

## Example: Using Pixels for Margin

### HTML

```html
<link rel="stylesheet" href="styles.css">

<div class="box"></div>
<div class="box"></div>
```

### CSS

```css
.box {
  width: 100px;
  height: 100px;
  background-color: red;
  margin: 10px;
}
```

### Explanation

```css
margin: 10px;
```

adds **10 pixels of space outside** each side of the box.

This spacing separates the boxes from one another and from surrounding elements.

Remember:

- **Margin** = Space **outside** an element.
- **Padding** = Space **inside** an element.

---

## Other Absolute Units

Besides `px`, CSS also provides several other absolute units.

| Unit | Meaning | Equivalent |
|------|---------|------------|
| `px` | Pixels | 1/96 inch |
| `in` | Inches | 96px |
| `cm` | Centimeters | 25.2/64 inch |
| `mm` | Millimeters | 1/10 centimeter |
| `q` | Quarter-millimeters | 1/40 centimeter |
| `pc` | Picas | 1/6 inch |
| `pt` | Points | 1/72 inch |

---

## Where Are These Units Commonly Used?

While **`px`** is the most common absolute unit for web development, the remaining absolute units are mostly used for:

- Printing documents
- PDFs
- Books
- Newspapers
- Magazines
- Posters
- Other print media

They are rarely used for designing responsive websites.

---

## Absolute Units vs Relative Units

| Absolute Units | Relative Units |
|---------------|----------------|
| Fixed size | Flexible size |
| Never change based on screen size | Change depending on context |
| Good for precise layouts | Good for responsive layouts |
| Example: `px` | Examples: `%`, `em`, `rem`, `vw`, `vh` |

---

## Best Practices

- Use **`px`** when precise sizing is required.
- Use **`px`** for borders, icons, spacing, and fixed-size UI elements.
- Avoid using only absolute units when building responsive websites.
- Combine `px` with relative units like `rem`, `%`, `vw`, and `vh` for better responsiveness.

---

## Summary

- CSS length units are divided into **absolute** and **relative** units.
- Absolute units always have a **fixed size**.
- The most commonly used absolute unit is **`px`**.
- `1px` is defined as **1/96 of an inch** in CSS.
- Pixels are useful for precise control over dimensions and spacing.
- Other absolute units (`in`, `cm`, `mm`, `q`, `pc`, and `pt`) are mainly intended for print media rather than web pages.

---

## Key Takeaways

- Absolute units are **fixed** measurements.
- Relative units are **flexible** measurements.
- `px` is the most widely used absolute unit in CSS.
- Pixels provide precise control over layouts and spacing.
- Most other absolute units are designed primarily for print rather than screen-based layout.
