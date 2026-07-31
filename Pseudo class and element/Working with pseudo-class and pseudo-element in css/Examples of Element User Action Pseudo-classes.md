# CSS Repository
# Element User Action Pseudo-classes

## What Are Element User Action Pseudo-classes?

User action pseudo-classes are special CSS keywords that style elements based on how users interact with them.

They provide visual feedback without needing JavaScript.

This feedback helps users know:

* Which button is being clicked.
* Which link has been visited.
* Which input field is currently active.
* Which checkbox is selected.
* Which element is disabled or enabled.

Using these pseudo-classes improves both *user experience (UX)* and *accessibility*.

---

# Common User Action Pseudo-classes

* `:hover`
* `:active`
* `:focus`
* `:visited`
* `:checked`
* `:focus-within`
* `:enabled`
* `:disabled`
* `:target`

---

# `:active`

## What It Does

The `:active` pseudo-class styles an element while it is being activated, usually when the user clicks or presses it.

## HTML

```html
<a href="#">Example Link</a>
```

## CSS

```css
a:active {
  color: crimson;
}
```

## Result

* The link changes to `crimson` while it is being clicked.
* The style only lasts during the click.

---

# `:hover`

## What It Does

The `:hover` pseudo-class styles an element when the mouse pointer is placed over it.

It is commonly used on:

* Buttons
* Links
* Images
* Cards
* Menus

## HTML

```html
<button class="btn">Hover Over Me</button>
```

## CSS

```css
.btn:hover {
  background-color: darkgreen;
  color: white;
  cursor: pointer;
}
```

## Result

When the mouse is over the button:

* Background becomes `darkgreen`.
* Text becomes `white`.
* Cursor changes to a pointer.
* The style disappears when the mouse leaves.

---

# `:focus`

## What It Does

The `:focus` pseudo-class styles an element after it receives focus.

An element gains focus when:

* A user clicks it.
* A user presses the `Tab` key.
* A keyboard user navigates to it.

This is very important for accessibility.

## HTML

```html
<form>
  <input type="text">
</form>
```

## CSS

```css
input:focus {
  outline: 2px solid darkgreen;
  border-radius: 4px;
}
```

## Result

* The input receives a dark green outline.
* Rounded corners are added.
* Keyboard users can easily see which field is active.

---

# `:visited`

## What It Does

The `:visited` pseudo-class styles links the user has already visited.

## HTML

```html
<a href="https://www.example.com" target="_blank">
  Visit Example.com
</a>
```

## CSS

```css
a:visited {
  color: cyan;
}
```

## Result

* After visiting the link, its text becomes `cyan`.
* Helps users distinguish visited pages from unvisited ones.

---

# `:checked`

## What It Does

The `:checked` pseudo-class styles checkboxes and radio buttons after they have been selected.

It is commonly used for custom form controls.

---

## HTML

```html
<form>
  <label>
    Agree
    <input class="checkbox" type="checkbox">
  </label>
</form>
```

---

## CSS

```css
.checkbox {
  appearance: none;
  width: 18px;
  height: 18px;
  border: 2px solid #ccc;
  border-radius: 4px;
  display: inline-block;
  position: relative;
  cursor: pointer;
  transition: all 0.25s ease;
  vertical-align: middle;
}

.checkbox:hover {
  border-color: #888;
}

.checkbox:checked {
  background-color: #4caf50;
  border-color: #4caf50;
}

.checkbox:checked::after {
  content: "";
  position: absolute;
  left: 4px;
  top: 0;
  width: 5px;
  height: 10px;
  border: solid white;
  border-width: 0 2px 2px 0;
  transform: rotate(45deg);
}

.checkbox:focus {
  outline: 2px solid #90caf9;
  outline-offset: 2px;
}
```

---

## Result

When unchecked:

* Gray border.

When hovered:

* Border becomes darker.

When checked:

* Background turns green.
* A white checkmark appears.

When focused:

* A blue outline appears.

---

# Understanding `appearance: none`

```css
appearance: none;
```

## What It Does

Removes the browser's default styling from form controls.

This allows you to completely customize elements like:

* Checkboxes
* Radio buttons
* Select menus

Without this property, browsers use their own default designs.

---

# Other User Action Pseudo-classes

## `:focus-within`

### What It Does

Styles a parent element whenever it or one of its child elements has focus.

Example:

```css
form:focus-within {
  background-color: lightyellow;
}
```

Useful for highlighting an entire form while the user is typing.

---

## `:enabled`

### What It Does

Targets form elements that are currently enabled.

Example:

```css
button:enabled {
  background-color: green;
}
```

---

## `:disabled`

### What It Does

Targets disabled form controls.

Example:

```css
button:disabled {
  background-color: gray;
  cursor: not-allowed;
}
```

---

## `:target`

### What It Does

Styles an element whose `id` matches the URL fragment after the `#`.

Example URL:

```
https://example.com/page.html#about
```

HTML:

```html
<h2 id="about">About Us</h2>
```

CSS:

```css
#about:target {
  background: yellow;
}
```

## Result

When the URL ends with `#about`, the "About Us" section is highlighted.

---

# Why Use User Action Pseudo-classes?

They help create interactive websites by:

* Giving users immediate visual feedback.
* Improving accessibility.
* Making forms easier to use.
* Highlighting selected items.
* Indicating visited links.
* Showing active buttons and inputs.

Most of these effects require only CSS and no JavaScript.

---

# Key Points

* User action pseudo-classes respond to user interactions.
* They begin with a colon (`:`).
* They improve usability and accessibility.
* Common examples include:
  * `:hover`
  * `:active`
  * `:focus`
  * `:visited`
  * `:checked`
  * `:focus-within`
  * `:enabled`
  * `:disabled`
  * `:target`
* They allow websites to feel interactive using only CSS.
