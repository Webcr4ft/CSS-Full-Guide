# How Do You Style the Different Link States?

There are different states of a link, including `link`, `visited`, `hover`, `focus`, and `active`.

These states are important for helping users recognize links and providing clear feedback after interactions, which improves both usability and accessibility.

Styling these different link states is crucial for usability and accessibility, as it provides visual cues about the current state of the link.

This helps users understand which links they have visited, which link they are interacting with, and what will happen when they click.

For users with visual impairments or cognitive disabilities, these distinct styles can make navigation much easier and more intuitive.

Additionally, clear link states enhance the overall user experience by providing immediate feedback on user interactions, reducing confusion and improving the site's navigability.

---

# Styling Link States with Pseudo-Classes

These states can be styled using something called **pseudo-classes** in CSS.

A pseudo-class is a keyword added to a selector that specifies a special state of the selected element.

For example, `:hover` can change a button's color when the user's pointer hovers over it, while `:visited` can change the color of a link that has already been visited.

Pseudo-classes allow you to style elements based on their state or the user's interaction with them, without the need for additional markup in your HTML.

The syntax of a pseudo-class looks something like this, where `A` is the selector and `:B` is the pseudo-class:

```css
A:B {
  property: value;
}
```

---

# The `:link` Pseudo-Class

The `:link` pseudo-class styles unvisited links, indicating that they are clickable.

Here is an example of targeting an anchor element and using the `:link` pseudo-class.

### HTML

```html
<link rel="stylesheet" href="styles.css">

<a href="/">Example link</a>
```

### CSS

```css
/* Normal state (unvisited link) */
a:link {
  color: red;
}
```

The above example will change the link's default blue color to `red` when it is unvisited.

---

# The `:visited` Pseudo-Class

`:visited` styles links that have already been visited or clicked, helping users track which links they have clicked before.

Here’s an example usage of the `:visited` pseudo-class.

### HTML

```html
<link rel="stylesheet" href="styles.css">

<a href="https://www.freecodecamp.org/learn/" target="_blank">
  freeCodeCamp
</a>
```

### CSS

```css
/* Visited link */
a:visited {
  color: green;
}
```

This code will color the link to `green` when it is clicked.

---

# The `:hover` Pseudo-Class

`:hover` changes the link's style when the user hovers over it, providing a visual cue that the link is interactive.

Here’s an example usage of the `:hover` pseudo-class.

### HTML

```html
<link rel="stylesheet" href="styles.css">

<a href="/">Example link</a>
```

### CSS

```css
/* Hover state */
a:hover {
  color: green;
}
```

This code will color the links to `green` when the mouse is hovered over them.

---

# The `:focus` Pseudo-Class

`:focus` adds styles around the link when it is focused, such as when navigating with a keyboard, enhancing accessibility.

Here is an example using the `outline` property to apply a solid orange outline when the link is focused.

### HTML

```html
<link rel="stylesheet" href="styles.css">

<a href="/">Example link</a>
```

### CSS

```css
/* Focus state */
a:focus {
  outline: 2px solid orange;
}
```

---

# The `:active` Pseudo-Class

`:active` changes the link's styles while the link is being clicked, providing immediate feedback to the user that their action is being registered.

Here’s an example usage of the `:active` pseudo-class.

### HTML

```html
<link rel="stylesheet" href="styles.css">

<a href="/">Example link</a>
```

### CSS

```css
/* Active state */
a:active {
  color: pink;
}
```

This code example will make the link change to the color `pink` immediately when the link is clicked.
