# CSS Repository
# Tree-structural Pseudo-classes

## What Are Tree-structural Pseudo-classes?

Tree-structural pseudo-classes allow you to target and style elements based on their position within the HTML document tree.

The **document tree** is the hierarchical structure of an HTML document. Every HTML element has a relationship with other elements, such as:

* Parent
* Child
* Sibling
* Ancestor
* Descendant

Tree-structural pseudo-classes let you select elements according to these relationships instead of using classes or IDs.

---

# Common Tree-structural Pseudo-classes

* `:root`
* `:empty`
* `:nth-child(n)`
* `:nth-last-child(n)`
* `:first-child`
* `:last-child`
* `:only-child`
* `:nth-of-type(n)`
* `:first-of-type`
* `:last-of-type`
* `:only-of-type`

---

# `:root`

## What It Does

The `:root` pseudo-class selects the highest-level element in the document.

For HTML documents, this is always the:

```html
<html>
```

element.

It is commonly used for:

* Applying styles to the whole page.
* Defining CSS custom properties (variables).

---

## HTML

```html
<h1>Welcome to My Website</h1>

<p>
  This is a sample paragraph to demonstrate
  the :root pseudo-class.
</p>
```

---

## CSS

```css
:root {
  background: black;
  color: aliceblue;
}
```

---

## Result

The entire webpage receives:

* A black background.
* Alice blue text.

Because every element is inside the root element, these styles affect the whole page.

---

# Using `:root` for CSS Variables

## CSS

```css
:root {
  --main-font: Arial, sans-serif;
  --primary-color: blue;
  --secondary-color: green;
}
```

---

## What Are CSS Variables?

CSS variables (also called **custom properties**) store reusable values.

Instead of repeating the same values throughout your stylesheet, you define them once and reuse them.

Example:

```css
:root {
  --primary-color: blue;
}

button {
  background-color: var(--primary-color);
}
```

Benefits include:

* Less repetition.
* Easier maintenance.
* Consistent styling.
* Simple theme switching.

---

# `:empty`

## What It Does

The `:empty` pseudo-class selects elements that have **no child elements and no text content**.

Even whitespace may prevent an element from being considered empty.

---

## HTML

```html
<ul>
  <li>Item 1</li>
  <li></li>
  <li>Item 2</li>
  <li></li>
  <li>Item 3</li>
</ul>
```

---

## CSS

```css
:empty {
  background: black;
}
```

---

## Result

Only the empty `<li>` elements receive:

* A black background.

---

## Hiding Empty Elements

Instead of styling empty elements, developers often remove them from the page.

### CSS

```css
:empty {
  display: none;
}
```

### Result

Empty list items disappear completely.

---

# `:nth-child(n)`

## What It Does

The `:nth-child(n)` pseudo-class selects an element based on its position within its parent.

The value `n` may be:

* A number.
* `odd`
* `even`
* A mathematical formula.

---

## HTML

```html
<table>
  <tr>
    <th>Item</th>
    <th>Price</th>
  </tr>

  <tr>
    <td>Apple</td>
    <td>$1.00</td>
  </tr>

  <tr>
    <td>Banana</td>
    <td>$0.50</td>
  </tr>

  <tr>
    <td>Orange</td>
    <td>$0.80</td>
  </tr>
</table>
```

---

## CSS

```css
th,
td {
  border: 1px solid lightgray;
  padding: 8px;
}

tr:nth-child(even) {
  background-color: orangered;
}

tr:nth-child(odd) {
  background-color: lightgreen;
}
```

---

## Result

Rows alternate colors:

* Odd rows → Light green.
* Even rows → Orange red.

This technique is commonly called **zebra striping**.

---

# `:nth-last-child(n)`

## What It Does

Works exactly like `:nth-child()` except counting begins from the **last child** instead of the first.

Example:

```css
li:nth-last-child(2) {
  color: red;
}
```

This selects the **second item from the bottom**.

---

# `:first-child`

## What It Does

Selects the first child element inside its parent.

---

## HTML

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

---

## CSS

```css
li:first-child {
  background-color: orangered;
}
```

---

## Result

Only:

```
Item 1
```

receives the orange-red background.

---

# `:last-child`

## What It Does

Selects the last child element inside its parent.

---

## CSS

```css
li:last-child {
  background-color: lightgreen;
}
```

---

## Result

Only:

```
Item 3
```

receives the light green background.

---

## Being More Specific

If multiple lists exist on the page:

Instead of:

```css
li:first-child
```

Use:

```css
ul li:first-child
```

or

```css
.menu li:first-child
```

This prevents styling every list on the webpage.

---

# `:only-child`

## What It Does

Selects an element only if it is the **only child** of its parent.

If the parent contains two or more children, nothing is selected.

---

## HTML

```html
<div class="container">
  <div>
    This is the only item in this container.
  </div>
</div>

<div class="container">
  <div>
    This is one of two items.
  </div>

  <div>
    Here is the second item.
  </div>
</div>
```

---

## CSS

```css
.container div:only-child {
  border: 2px solid crimson;
  padding: 10px;
  background-color: lightblue;
}
```

---

## Result

Only the first container receives:

* Crimson border.
* Light blue background.
* Padding.

The second container is ignored because it contains two children.

---

# `:first-of-type`

## What It Does

Selects the first occurrence of a particular element type inside its parent.

Unlike `:first-child`, it only considers elements of the same type.

---

## HTML

```html
<section>
  <h2>Introduction</h2>

  <p>
    First paragraph
  </p>

  <p>
    Second paragraph
  </p>
</section>
```

---

## CSS

```css
section p:first-of-type {
  background-color: lightgreen;
}
```

---

## Result

Only the first paragraph inside each section becomes light green.

---

# `:last-of-type`

## What It Does

Selects the last occurrence of a particular element type inside its parent.

---

## CSS

```css
section p:last-of-type {
  background-color: lightblue;
}
```

---

## Result

Only the final paragraph inside each section becomes light blue.

---

# `:nth-of-type(n)`

## What It Does

Selects an element according to its position **among siblings of the same type**.

---

## HTML

```html
<div class="container">
  <p>First paragraph</p>

  <p>Second paragraph</p>

  <p>Third paragraph</p>
</div>
```

---

## CSS

```css
p:nth-of-type(2) {
  color: red;
  font-weight: bold;
}
```

---

## Result

Only:

```
Second paragraph
```

becomes:

* Red.
* Bold.

---

# `:only-of-type`

## What It Does

Selects an element if it is the **only element of its type** inside its parent.

---

## HTML

```html
<div class="container">
  <p>The only paragraph</p>
</div>

<div class="container">
  <p>The first paragraph</p>

  <p>The second paragraph</p>
</div>
```

---

## CSS

```css
p:only-of-type {
  border: 4px solid green;
}
```

---

## Result

Only:

```
The only paragraph
```

receives the green border.

The paragraphs in the second container are ignored because there are two `<p>` elements.

---

# Difference Between Similar Pseudo-classes

| Pseudo-class | What It Selects |
|--------------|-----------------|
| `:first-child` | The first child of a parent. |
| `:last-child` | The last child of a parent. |
| `:only-child` | The only child of a parent. |
| `:first-of-type` | The first element of a particular type. |
| `:last-of-type` | The last element of a particular type. |
| `:only-of-type` | The only element of its type. |
| `:nth-child(n)` | Child based on overall position. |
| `:nth-of-type(n)` | Child based on position among the same element type. |

---

# Why Use Tree-structural Pseudo-classes?

Tree-structural pseudo-classes help you:

* Style elements without adding extra classes.
* Target elements by their position.
* Build cleaner HTML.
* Reduce repetitive CSS.
* Create zebra-striped tables.
* Highlight first or last items.
* Style only elements that meet specific structural conditions.

---

# Key Points

* Tree-structural pseudo-classes select elements according to their position in the HTML document tree.
* They begin with a colon (`:`).
* They reduce the need for extra classes and IDs.
* Common tree-structural pseudo-classes include:
  * `:root`
  * `:empty`
  * `:nth-child(n)`
  * `:nth-last-child(n)`
  * `:first-child`
  * `:last-child`
  * `:only-child`
  * `:nth-of-type(n)`
  * `:first-of-type`
  * `:last-of-type`
  * `:only-of-type`
* They are especially useful for styling lists, tables, navigation menus, and grouped content based on structure.
