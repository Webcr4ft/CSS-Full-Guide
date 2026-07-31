# CSS Repository
# Pseudo-classes

## What Are Pseudo-classes?

Pseudo-classes are special CSS keywords that allow you to select an element based on its *state* or *position*.

They let you style elements when they are:

* Active (being clicked)
* Hovered over by the mouse
* The first child of a parent
* The last child of a parent
* A visited link
* Disabled
* And many other states

## Syntax

```css
selector:pseudo-class {
  /* CSS properties */
}
```

* `selector` → The HTML element you want to target.
* `:` → Separates the selector from the pseudo-class.
* `pseudo-class` → The specific state or position of the element.

---

# `:active`

## What It Does

The `:active` pseudo-class targets an element while it is being activated, such as when a button is being clicked.

## HTML

```html
<button>Example Button</button>
```

## CSS

```css
button:active {
  background: greenyellow;
}
```

## Result

* The button's background changes to `greenyellow` while it is being clicked.
* The style only lasts during the click.

---

# `:hover`

## What It Does

The `:hover` pseudo-class styles an element when the mouse pointer is placed over it.

## HTML

```html
<a href="#">Hover over me!</a>
```

## CSS

```css
a:hover {
  text-decoration: none;
  color: white;
  background: crimson;
}
```

## Result

* Removes the underline.
* Changes the text color to white.
* Changes the background to crimson.
* The style disappears when the mouse leaves the element.

---

# `:first-child`

## What It Does

The `:first-child` pseudo-class selects the first child element inside its parent.

## HTML

```html
<div class="container">
  <p>First child</p>
  <p>Second child</p>
  <p>Third child</p>
  <p>Last child</p>
</div>
```

## CSS

```css
.container p:first-child {
  background: lightcoral;
  padding: 0.4rem;
}
```

## Result

Only the first `<p>` receives:

* `background: lightcoral`
* `padding: 0.4rem`

---

# `:last-child`

## What It Does

The `:last-child` pseudo-class selects the last child element inside its parent.

## HTML

```html
<div class="container">
  <p>First child</p>
  <p>Second child</p>
  <p>Third child</p>
  <p>Last child</p>
</div>
```

## CSS

```css
.container p:last-child {
  background: lightcoral;
  padding: 0.4rem;
}
```

## Result

Only the last `<p>` receives:

* `background: lightcoral`
* `padding: 0.4rem`

---

# `:visited`

## What It Does

The `:visited` pseudo-class styles links that the user has already visited.

## HTML

```html
<a href="https://www.example.com" target="_blank">
  Visit Example.com
</a>
```

## CSS

```css
a:visited {
  color: purple;
}
```

## Result

* After the user visits the link, its text color becomes purple.

---

# `:disabled`

## What It Does

The `:disabled` pseudo-class targets form controls that are disabled.

## HTML

```html
<button disabled>Disabled Button</button>
```

## CSS

```css
button:disabled {
  background-color: lightgray;
}
```

## Result

* The disabled button gets a light gray background.
* Users cannot interact with the button.

---

# Why Use Pseudo-classes?

Pseudo-classes help make websites more interactive by styling elements based on:

* User interactions
* Element states
* Element positions

Instead of adding JavaScript for simple visual effects, CSS pseudo-classes can handle many common interactions.

---

# Other Common Pseudo-classes

* `:focus`
  * Styles an element when it receives keyboard or mouse focus.

* `:first-of-type`
  * Selects the first element of its type within a parent.

* `:last-of-type`
  * Selects the last element of its type within a parent.

* `:nth-of-type()`
  * Selects specific elements based on their position.

* `:modal`
  * Targets an element displayed as a modal dialog.

* `:enabled`
  * Selects enabled form controls.

* `:checked`
  * Targets checked checkboxes or radio buttons.

* `:required`
  * Targets form fields that must be filled before submission.

---

# Key Points

* Pseudo-classes begin with a colon (`:`).
* They style elements based on their state or position.
* No extra HTML classes or IDs are needed.
* They improve user experience with interactive styling.
* Common examples include:
  * `:hover`
  * `:active`
  * `:visited`
  * `:focus`
  * `:disabled`
  * `:checked`
  * `:first-child`
  * `:last-child`
