# CSS Repository
# Functional Pseudo-classes

## What Are Functional Pseudo-classes?

Functional pseudo-classes are CSS pseudo-classes that allow you to select elements based on more advanced conditions or relationships.

Unlike regular pseudo-classes such as:

* `:hover`
* `:focus`
* `:active`

functional pseudo-classes **accept one or more arguments inside parentheses `()`**.

This makes them more powerful because they can match multiple selectors, exclude selectors, or even target parent elements based on their children.

---

# Common Functional Pseudo-classes

* `:is()`
* `:where()`
* `:has()`
* `:not()`

---

# `:is()`

## What It Does

The `:is()` pseudo-class groups multiple selectors into one.

Instead of writing the same CSS rule for several selectors, you place all the selectors inside `:is()`.

This makes your CSS:

* Shorter.
* Easier to read.
* Easier to maintain.

---

## Without `:is()`

### HTML

```html
<button>Example Button</button>

<a href="#" class="button">
  Link styled like a button
</a>

<input
  type="submit"
  value="Submit"
>

<input
  type="reset"
  value="Reset"
>
```

---

### CSS

```css
button,
a.button,
input[type="submit"],
input[type="reset"] {
  background-color: darkblue;
  color: white;
  border: 1px solid darkblue;
  padding: 10px 20px;
  text-decoration: none;
  border-radius: 5px;
  cursor: pointer;
  display: inline-block;
  margin: 5px;
  font-size: 16px;
  text-align: center;
}

button:hover,
a.button:hover,
input[type="submit"]:hover,
input[type="reset"]:hover {
  background-color: blue;
  border-color: blue;
}
```

This works, but the selector is long and repetitive.

---

## With `:is()`

### HTML

```html
<button>Example Button</button>

<a href="#" class="button">
  Link styled like a button
</a>

<input
  type="submit"
  value="Submit"
>

<input
  type="reset"
  value="Reset"
>
```

---

### CSS

```css
:is(
  button,
  a.button,
  input[type="submit"],
  input[type="reset"]
) {
  background-color: darkblue;
  color: white;
  border: 1px solid darkblue;
  padding: 10px 20px;
  text-decoration: none;
  border-radius: 5px;
  cursor: pointer;
  display: inline-block;
  margin: 5px;
  font-size: 16px;
  text-align: center;
}

:is(
  button,
  a.button,
  input[type="submit"],
  input[type="reset"]
):hover {
  background-color: blue;
  border-color: blue;
}
```

---

## Result

All of these elements receive the same styles:

* `<button>`
* Button-styled links
* Submit buttons
* Reset buttons

The CSS is cleaner and much easier to manage.

---

# `:where()`

## What It Does

The `:where()` pseudo-class works almost exactly like `:is()`.

The important difference is:

**`:where()` has zero specificity.**

This means it does not make your selector harder to override later.

It is commonly used for:

* CSS resets.
* Base styles.
* Global styling.

---

## HTML

```html
<h1>Page Title</h1>

<h2>Subtitle</h2>

<h3>A Point</h3>

<p>Example paragraph.</p>

<p>Example paragraph.</p>

<p>Example paragraph.</p>
```

---

## CSS

```css
:where(h1, h2, h3) {
  margin: 0;
  padding: 0;
}
```

---

## Result

Every heading receives:

* `margin: 0`
* `padding: 0`

Because `:where()` has zero specificity, other heading styles can easily override these values.

---

# Difference Between `:is()` and `:where()`

| `:is()` | `:where()` |
|----------|------------|
| Groups selectors. | Groups selectors. |
| Keeps selector specificity. | Always has zero specificity. |
| Good for general styling. | Best for resets and base styles. |

---

# `:has()`

## What It Does

The `:has()` pseudo-class selects a parent element based on its children.

Before `:has()` existed, CSS could only style child elements.

Now CSS can also style parents if they contain certain elements.

This makes `:has()` one of the most powerful CSS selectors.

---

## HTML

```html
<article>
  <h2>Subheading</h2>

  <p>
    Lorem ipsum dolor sit amet.
  </p>
</article>

<article>
  <h3>A Point</h3>

  <p>
    Lorem ipsum dolor sit amet.
  </p>

  <p>
    Lorem ipsum dolor sit amet.
  </p>
</article>
```

---

## CSS

```css
article:has(h2) {
  border: 2px solid hotpink;
}
```

---

## Result

Only the first `<article>` receives:

* A hot pink border.

The second article is ignored because it contains an `<h3>` instead of an `<h2>`.

---

## Why `:has()` Is Useful

It allows you to style parents based on:

* Child elements.
* Checked checkboxes.
* Focused inputs.
* Images.
* Headings.
* Forms containing errors.

Example:

```css
form:has(input:invalid) {
  border: 2px solid red;
}
```

If any input inside the form is invalid, the entire form gets a red border.

---

# `:not()`

## What It Does

The `:not()` pseudo-class selects every matching element **except** the selector inside the parentheses.

It is useful when you want to exclude one or more elements.

---

## HTML

```html
<button class="primary">
  Primary Button
</button>

<button class="secondary">
  Secondary Button
</button>

<button class="danger">
  Another Secondary Button
</button>
```

---

## CSS

```css
button {
  padding: 10px 20px;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
  border: none;
  color: white;
}

button.primary {
  background-color: deepskyblue;
}

button:not(.primary) {
  background-color: grey;
}
```

---

## Result

Primary button:

* Deep sky blue background.

Every other button:

* Gray background.

Instead of styling each non-primary button individually, `:not()` excludes only the primary button.

---

# Why Use Functional Pseudo-classes?

Functional pseudo-classes help you:

* Write shorter CSS.
* Reduce repeated selectors.
* Improve readability.
* Apply complex conditions.
* Select parent elements.
* Exclude specific elements.
* Create cleaner, easier-to-maintain stylesheets.

---

# Comparison of Functional Pseudo-classes

| Pseudo-class | Purpose |
|--------------|----------|
| `:is()` | Groups multiple selectors into one. |
| `:where()` | Groups selectors without adding specificity. |
| `:has()` | Selects a parent element based on its children or their state. |
| `:not()` | Selects everything except the specified selector. |

---

# Key Points

* Functional pseudo-classes accept arguments inside parentheses `()`.
* They are more powerful than regular pseudo-classes because they allow complex selections.
* Common functional pseudo-classes include:
  * `:is()`
  * `:where()`
  * `:has()`
  * `:not()`
* `:is()` reduces repetitive selectors.
* `:where()` is ideal for CSS resets because it has zero specificity.
* `:has()` allows parent elements to be styled based on their children.
* `:not()` excludes specific elements from a selector.
* Functional pseudo-classes make CSS cleaner, shorter, and easier to maintain.
