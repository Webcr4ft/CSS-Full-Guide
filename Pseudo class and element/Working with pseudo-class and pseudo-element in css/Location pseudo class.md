# CSS Repository
# Location Pseudo-classes

## What Are Location Pseudo-classes?

Location pseudo-classes are CSS pseudo-classes that style links and elements based on their location within a document or based on the current URL.

They are mainly used for:

* Styling visited and unvisited links.
* Styling all links.
* Styling internal document links.
* Highlighting elements targeted by a URL fragment (`#id`).

These pseudo-classes help users navigate websites more easily by providing visual feedback about links and page locations.

---

# Common Location Pseudo-classes

* `:link`
* `:visited`
* `:any-link`
* `:local-link`
* `:target`

---

# `:link`

## What It Does

The `:link` pseudo-class targets **unvisited links**.

It only applies to anchor (`<a>`) elements that have an `href` attribute and have **not** been visited by the user.

This allows developers to style new links differently from visited ones.

---

## HTML

```html
<a
  target="_blank"
  href="https://www.example.com"
>
  Visit Example.com
</a>
```

---

## CSS

```css
a:link {
  color: magenta;
}
```

---

## Result

Before the user clicks the link:

* The text appears **magenta**.

After the link is visited:

* The `:link` style no longer applies.
* The `:visited` pseudo-class takes over (if defined).

---

# `:visited`

## What It Does

The `:visited` pseudo-class targets links that the user has already visited.

This helps users distinguish between pages they have already opened and those they have not.

---

## HTML

```html
<a
  target="_blank"
  href="https://www.example.com"
>
  Visit Example.com
</a>
```

---

## CSS

```css
a:visited {
  color: purple;
}
```

---

## Result

After the user visits the link:

* The text color changes to **purple**.

This provides clear visual feedback that the page has already been visited.

---

# `:any-link`

## What It Does

The `:any-link` pseudo-class matches **all links** that have an `href` attribute.

It combines the behavior of:

* `:link`
* `:visited`

This means it styles both visited and unvisited links.

---

## HTML

```html
<a
  target="_blank"
  href="https://www.example.com"
>
  Visit Example.com
</a>
```

---

## CSS

```css
a:any-link {
  color: crimson;
}
```

---

## Result

Whether the link has been visited or not:

* Its text color will be **crimson**.

This is useful when you want the same styling for every link.

---

# `:local-link`

## What It Does

The `:local-link` pseudo-class targets links that point to the **same document**.

These are commonly called **internal links**.

Example:

```html
<a href="#about">
  About
</a>
```

Unlike external links, internal links navigate to another section within the same webpage.

---

## Browser Support

At the moment:

* No major browser supports the `:local-link` pseudo-class.

Because of this, it is rarely used in real-world projects.

---

# `:target`

## What It Does

The `:target` pseudo-class selects the element whose `id` matches the current URL fragment identifier.

A URL fragment is the part after the `#` symbol.

Example:

```
https://example.com/page.html#section1
```

In this example:

```
#section1
```

is the fragment identifier.

---

## HTML

```html
<nav id="table-of-contents">
  <ul>
    <li>
      <a href="#section1">
        Introduction
      </a>
    </li>

    <li>
      <a href="#section2">
        Features
      </a>
    </li>
  </ul>
</nav>

<section id="section1">
  <h2>Introduction</h2>
  <p>This is the introduction section.</p>
</section>

<section id="section2">
  <h2>Features</h2>
  <p>This section describes the features.</p>
</section>
```

---

## CSS

```css
section:target {
  background-color: green;
  border: 2px solid green;
  padding: 10px;
}
```

---

## Result

When the user clicks:

```html
<a href="#section1">
```

The browser scrolls to:

```html
<section id="section1">
```

Because that section becomes the current target:

* Its background changes to **green**.
* A green border appears.
* Padding is added.

If the user clicks:

```html
<a href="#section2">
```

Then the second section receives those same styles instead.

---

# Understanding URL Fragments

A URL fragment is everything after the `#` symbol.

Example:

```
https://example.com/index.html#contact
```

Here:

* `https://example.com/index.html` → The webpage.
* `#contact` → The fragment identifier.

The browser searches for:

```html
id="contact"
```

When it finds that element:

* It scrolls to it.
* The `:target` pseudo-class becomes active.

---

# Why Use Location Pseudo-classes?

Location pseudo-classes improve website navigation by:

* Distinguishing visited and unvisited links.
* Styling all links consistently.
* Highlighting sections users navigate to.
* Improving in-page navigation.
* Providing better visual feedback.

They help users understand where they are and where they have been while browsing.

---

# Comparison of Location Pseudo-classes

| Pseudo-class | Purpose |
|--------------|----------|
| `:link` | Targets unvisited links. |
| `:visited` | Targets links that have already been visited. |
| `:any-link` | Targets all links with an `href` attribute. |
| `:local-link` | Targets links pointing to the same document (currently unsupported by browsers). |
| `:target` | Targets the element whose `id` matches the current URL fragment. |

---

# Key Points

* Location pseudo-classes style links and elements based on their location or URL state.
* They begin with a colon (`:`).
* They improve website navigation and usability.
* Common location pseudo-classes include:
  * `:link`
  * `:visited`
  * `:any-link`
  * `:local-link`
  * `:target`
* `:target` is especially useful for single-page websites and table-of-contents navigation.
* `:local-link` currently has **no browser support**.
