# Why Are Default Link Styles Important for Usability on the Web?

Default link styles play a crucial role in enhancing usability and accessibility on the web.

These styles, typically **blue** for unvisited links and **purple** for visited links, have become a standard that users have come to expect and rely on when navigating websites.

The primary purpose of default link styles is to provide clear visual cues that help users distinguish between interactive and non-interactive elements on a webpage.

This distinction is fundamental to creating an intuitive and user-friendly browsing experience.

---

# Basic Default Link Styles

### HTML

```html
<link rel="stylesheet" href="styles.css">

<a href="/">Example link</a>
```

### CSS

```css
a:link {
  color: blue;
  text-decoration: underline;
}

a:visited {
  color: purple;
}
```

---

# Why These Default Styles Matter

These styles serve several important functions.

Firstly, the **blue color** for unvisited links stands out against most background colors and text, making links easily identifiable.

This contrast is crucial for users to quickly scan a page and find navigational elements or important information.

The **underline** further emphasizes that the text is clickable, providing an additional visual cue.

This is particularly helpful for users who may be colorblind or have difficulty distinguishing colors.

The change in color for **visited links** (typically to purple) helps users keep track of where they've been.

This feature is invaluable for navigating large websites or conducting research, as it prevents users from inadvertently revisiting the same pages.

---

# Example of Default Browser Behavior

### HTML

```html
<p>
  Learn more about
  <a href="https://www.example.com/cats">cats</a>
  and
  <a href="https://www.example.com/dogs">dogs</a>.
</p>
```

Without any custom CSS, most browsers will render these links in **blue** with an **underline**.

After clicking on one of the links, its color will change to **purple**, providing immediate feedback to the user about their browsing history.

---

# Customizing Link Styles Responsibly

While it's common for designers to modify these default styles to match a website's aesthetic, it's crucial to maintain the core principles behind them.

If you choose to change the default styles, ensure that:

- Links are still clearly distinguishable from regular text.
- There is a visible difference between visited and unvisited links.
- The chosen colors provide sufficient contrast with the background.

---

# Example of Custom Link Styles

### HTML

```html
<link rel="stylesheet" href="styles.css">

<a href="/">Example link</a>
```

### CSS

```css
a:link {
  color: blue;
  text-decoration: none;
  border-bottom: 1px solid blue;
}

a:visited {
  color: purple;
  border-bottom: 1px solid purple;
}
```

This maintains the blue and purple color scheme while replacing the underline with a bottom border for a more modern look.

---

# Link Interaction States

It's also important to consider the different states of links.

In addition to the default and visited states, links typically have **hover** and **active** states.

### HTML

```html
<link rel="stylesheet" href="styles.css">

<a href="/">Example link</a>
```

### CSS

```css
a:hover {
  color: red;
}

a:active {
  color: darkorange;
}
```

These states provide immediate feedback to users as they interact with links, enhancing the overall usability of the site.

---

# Conclusion

While it's possible to customize link styles, the principles behind the default styles should be maintained.

They play a crucial role in creating a usable and accessible web experience, helping users navigate and interact with content effectively.

Always prioritize clarity and user experience when designing link styles for your websites.
