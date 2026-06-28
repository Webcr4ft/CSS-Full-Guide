# How Does `inline-block` Work, and How Does It Differ from `inline` and `block` Elements?

When working with CSS, you often encounter three different types of display behaviors for elements:

* `inline`
* `block`
* `inline-block`

Each of these display values affects how elements are positioned and how they interact with other elements on the page.

In this lesson, we will focus on how the `inline-block` property works and how it differs from both `inline` and `block` elements.

---

# Block-Level Elements (`display: block;`)

Block-level elements behave like large containers or **"blocks"** that take up the full width of their parent container.

They:

* Start on a new line.
* Take up the full width available by default.
* Allow you to change their `width` and `height`.

> **Think of them as:** Large boxes that always want their own row.

---

# Inline Elements (`display: inline;`)

Inline elements only take up as much space as they need.

They:

* Stay within the surrounding text.
* Do **not** start on a new line.
* **Do not** properly accept `width` and `height`.

> **Think of them as:** Words inside a sentence.

---

# Inline-Block Elements (`display: inline-block;`)

The `inline-block` property is a **hybrid** of `inline` and `block`.

Like inline elements, `inline-block` elements remain in the normal text flow without starting on a new line.

However, unlike inline elements, you can adjust the `width` and `height` of an `inline-block` element, just as you would with block-level elements.

In short:

* `inline` → Stays on the same line, but you **can't** control its size with `width` and `height`.
* `inline-block` → Stays on the same line **and** allows you to control its `width` and `height`.

---

# Example

## HTML

```html
<link href="styles.css" rel="stylesheet">

<div class="container">
  <span class="inline-block-element element1">
    Inline-Block
  </span>

  <span class="inline-block-element element2">
    Inline-Block
  </span>
</div>
```

## CSS

```css
.inline-block-element {
  display: inline-block;
  width: 150px;
  height: 100px;
}

.element1 {
  background-color: lightblue;
}

.element2 {
  background-color: lightgreen;
}
```

---

## Explanation

In the above example, we have a `div` with a class of `container`.

Inside that `div` element, we have two `span` elements.

Each of the `span` elements is set to `display: inline-block;` and has a `width` and `height` defined.

Because they are `inline-block` elements:

* They appear **side by side** like inline elements.
* They also respect the specified `width` and `height` like block elements.

This is why `inline-block` is considered a combination of `inline` and `block`.

---

# What Happens If You Remove `display: inline-block;`?

If you remove the `display: inline-block;` property, neither the `width` nor the `height` will be applied, even though they are clearly defined.

## HTML

```html
<link href="styles.css" rel="stylesheet">

<div class="container">
  <span class="inline-block-element element1">
    Span element
  </span>

  <span class="inline-block-element element2">
    Span element
  </span>
</div>
```

## CSS

```css
.inline-block-element {
  width: 150px;
  height: 100px;
}

.element1 {
  background-color: lightblue;
}

.element2 {
  background-color: lightgreen;
}
```

---

## Explanation

In this code, we removed the `display: inline-block;` property but kept everything else intact.

Here, the `span` elements return to their default behavior as **inline elements**.

As a result:

* The specified `width` is ignored.
* The specified `height` is ignored.
* The elements only take up the space needed for their content.

---

# Visual Comparison

## `display: inline;`

```text
Span element Span element
```

* Stays on the same line.
* Ignores `width` and `height`.

---

## `display: block;`

```text
+------------------+
|   Span element   |
+------------------+

+------------------+
|   Span element   |
+------------------+
```

* Starts on a new line.
* Accepts `width` and `height`.

---

## `display: inline-block;`

```text
+------------------+  +------------------+
|   Span element   |  |   Span element   |
+------------------+  +------------------+
```

* Stays on the same line.
* Accepts `width` and `height`.

---

# Easy Way to Remember

* **`inline`** = A **word** in a sentence.
* **`block`** = A **large box** that wants its own line.
* **`inline-block`** = A **box** that stays on the same line as other boxes.

> **One sentence to remember:**
>
> **"`display: inline-block;` turns an inline element into a box without forcing it onto a new line."**

---

# Conclusion

Understanding how `inline-block` works is useful because it allows you to create layouts that require both **alignment** and **dimension control** while keeping elements in the normal text flow.

It combines the best features of both `inline` and `block`, making it ideal for buttons, navigation links, badges, and other elements that should stay on the same line while still behaving like boxes.
