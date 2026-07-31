# CSS Repository
# Pseudo-elements

## What Are Pseudo-elements?

One of the most powerful features of CSS is the use of **pseudo-elements**.

The word **"pseudo"** means **"not real"** or **"artificial."**

Pseudo-elements are **virtual elements** created by CSS. They do not exist in the HTML document but allow you to style specific parts of an element or insert additional content without adding extra HTML elements.

Unlike normal HTML elements, pseudo-elements:

* Cannot exist by themselves.
* Must be attached to another element.
* Allow you to style parts of an element's content.
* Allow you to insert content before or after an element.

The element that a pseudo-element is attached to is called the **originating element**.

---

# Syntax

Pseudo-elements use a **double colon (`::`)**.

```css
selector::pseudo-element {
  property: value;
}
```

Example:

```css
p::first-letter {
  color: red;
}
```

---

# Difference Between Pseudo-elements and Pseudo-classes

| Pseudo-elements | Pseudo-classes |
|-----------------|----------------|
| Use a double colon (`::`). | Use a single colon (`:`). |
| Style parts of an element or create virtual elements. | Style an element based on its state. |
| Example: `::before` | Example: `:hover` |
| Example: `::after` | Example: `:focus` |
| Example: `::first-letter` | Example: `:active` |

---

# `::before`

## What It Does

The `::before` pseudo-element inserts content **before** an element's existing content.

The inserted content does **not** appear in the HTML source.

Instead, CSS generates it.

---

## HTML

```html
<button class="cta-button">
  Learn More
</button>
```

---

## CSS

```css
.cta-button {
  background-color: lightseagreen;
  color: white;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
  position: relative;
}

.cta-button::before {
  content: "⭐";
  position: absolute;
  left: 3px;
  top: 8px;
  font-size: 0.75rem;
}
```

---

## Understanding the `content` Property

The `content` property specifies what should appear inside the pseudo-element.

Example:

```css
content: "⭐";
```

This inserts a star before the button text.

Without the `content` property:

```css
content: "";
```

the `::before` and `::after` pseudo-elements will not display anything.

---

## Result

The button appears as if it contains:

```
⭐ Learn More
```

Even though the star does **not** exist in the HTML.

---

# `::after`

## What It Does

The `::after` pseudo-element inserts content **after** an element's existing content.

---

## HTML

```html
<button class="cta-button">
  Learn More
</button>
```

---

## CSS

```css
.cta-button {
  background-color: orange;
  border: none;
  padding: 10px 30px;
  cursor: pointer;
  position: relative;
}

.cta-button::after {
  content: "➡️";
  position: absolute;
  right: 5px;
  bottom: 6px;
  font-size: 1.125rem;
  transition: transform 0.3s ease;
}
```

---

## Result

The button appears as:

```
Learn More ➡️
```

The arrow is created entirely with CSS.

---

# Understanding the `transition` Property

```css
transition: transform 0.3s ease;
```

## What It Does

The `transition` property creates smooth animations whenever a property changes.

This example means:

* Animate the `transform` property.
* Take **0.3 seconds**.
* Use an **ease** timing function.

Instead of changing instantly, the animation becomes smooth.

---

# Combining Pseudo-elements and Pseudo-classes

Pseudo-elements can be combined with pseudo-classes.

Example:

```css
.cta-button:hover::after {
  transform: translateX(2px);
}
```

Here:

* `:hover` detects when the mouse is over the button.
* `::after` selects the inserted arrow.

Only the arrow moves.

---

# Understanding `transform`

```css
transform: translateX(2px);
```

## What It Does

The `transform` property changes an element's appearance or position.

It can:

* Move elements.
* Rotate elements.
* Scale elements.
* Skew elements.

---

## Understanding `translateX()`

```css
translateX(2px)
```

Moves the element:

* **2 pixels to the right.**

If you use:

```css
translateX(-2px)
```

the element moves left.

---

## Example

```css
.cta-button:hover::after {
  transform: translateX(2px);
}
```

Result:

When the mouse hovers over the button:

* The arrow slides slightly to the right.
* The movement is smooth because of the `transition` property.

---

# `::first-letter`

## What It Does

The `::first-letter` pseudo-element selects only the **first letter** of an element.

It is commonly used for:

* Magazine-style articles.
* Decorative first letters.
* Drop caps.

---

## HTML

```html
<p>
  freeCodeCamp lets you learn to code
  without having to pay.
</p>
```

---

## CSS

```css
p::first-letter {
  font-size: 4rem;
}
```

---

## Result

Only the first letter:

```
f
```

becomes much larger.

The rest of the paragraph remains unchanged.

---

# `::marker`

## What It Does

The `::marker` pseudo-element styles list markers.

Markers include:

* Bullet points.
* Numbers.
* Other list symbols.

---

## HTML

```html
<ul>
  <li>Unordered list item 1</li>
  <li>Unordered list item 2</li>
  <li>Unordered list item 3</li>
  <li>Unordered list item 4</li>
</ul>

<ol>
  <li>Ordered list item 1</li>
  <li>Ordered list item 2</li>
  <li>Ordered list item 3</li>
  <li>Ordered list item 4</li>
</ol>
```

---

## CSS

```css
li::marker {
  color: crimson;
  font-size: 1.5em;
  font-weight: bold;
}
```

---

## Result

Every bullet and number becomes:

* Crimson.
* Larger.
* Bold.

Only the markers change.

The list text remains unchanged.

---

# Other Useful Pseudo-elements

## `::placeholder`

### What It Does

Styles placeholder text inside input fields.

Example:

```css
input::placeholder {
  color: gray;
  font-style: italic;
}
```

---

## `::selection`

### What It Does

Styles text that the user highlights.

Example:

```css
::selection {
  background: yellow;
  color: black;
}
```

When users select text, it appears with your chosen colors.

---

## `::spelling-error`

### What It Does

Targets text marked by the browser as having spelling mistakes.

Browser support is currently limited.

---

# Why Use Pseudo-elements?

Pseudo-elements allow you to:

* Add decorative content.
* Style specific parts of text.
* Avoid unnecessary HTML elements.
* Keep HTML cleaner.
* Create icons using only CSS.
* Customize list markers.
* Build modern UI effects.

---

# Comparison of Common Pseudo-elements

| Pseudo-element | Purpose |
|----------------|----------|
| `::before` | Inserts content before an element. |
| `::after` | Inserts content after an element. |
| `::first-letter` | Styles the first letter of text. |
| `::marker` | Styles list bullets or numbering. |
| `::placeholder` | Styles placeholder text in inputs. |
| `::selection` | Styles highlighted text. |
| `::spelling-error` | Styles browser-detected spelling errors (limited support). |

---

# Key Points

* Pseudo-elements are virtual elements created by CSS.
* They use a **double colon (`::`)**.
* They cannot exist without an originating element.
* The `content` property is required for `::before` and `::after`.
* Common pseudo-elements include:
  * `::before`
  * `::after`
  * `::first-letter`
  * `::marker`
  * `::placeholder`
  * `::selection`
  * `::spelling-error`
* Pseudo-elements help create cleaner HTML by allowing decorative content and styling without adding extra elements.
