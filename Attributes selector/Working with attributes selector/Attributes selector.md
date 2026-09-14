# What Is the Attribute Selector?

The **attribute selector** in CSS allows you to target HTML elements based on their attributes.

This means you can style elements that:

- Have a specific attribute.
- Have a specific attribute value.
- Have an attribute containing a particular word.
- Have an attribute value that starts with something.
- Have an attribute value that ends with something.
- Have multiple attributes at the same time.

Attribute selectors are useful when class names alone aren't enough to target the elements you want.

---

# Basic Attribute Selector

The basic syntax is:

    element[attribute] {
      property: value;
    }

For example:

    a[href] {
      color: blue;
    }

This targets all `<a>` elements that have an `href` attribute.

---

# Targeting Links with the `href` Attribute

HTML:

    <a href="https://example.com">Example link with an href attribute</a>

    <a>Example link without an href attribute</a>

CSS:

    a {
      display: block;
    }

    a[href] {
      color: blue;
      text-decoration: underline;
    }

The selector:

    a[href]

means:

    "Select all <a> elements that have an href attribute."

Only the first link has an `href`, so only that link receives the styles.

---

# Why Target the `href` Attribute?

The `href` attribute is commonly used on links to specify where the link should go.

For example:

    <a href="https://example.com">Visit Example</a>

You can use:

    a[href]

to target links that actually have an `href` attribute.

This can be useful when you want clickable links to have a consistent style.

---

# Targeting Links with the `title` Attribute

You can also target elements that have a `title` attribute.

HTML:

    <a href="https://example.com" title="Example link with a title attribute">
      Example link with a title attribute
    </a>

    <a>
      Example link without a title or href attribute
    </a>

CSS:

    a {
      display: block;
    }

    a[title] {
      font-weight: bold;
      text-decoration: none;
    }

The selector:

    a[title]

means:

    "Select all <a> elements that have a title attribute."

The link with the `title` attribute becomes bold and loses its underline.

---

# Combining Attribute Selectors

You can combine multiple attribute selectors to target elements that have **multiple attributes**.

Example:

    a[href][title] {
      display: block;
      color: green;
    }

This means:

    Select <a> elements
    AND
    They must have an href attribute
    AND
    They must have a title attribute

HTML:

    <a href="https://example.com" title="Example link with a title attribute">
      Example link with a title attribute
    </a>

    <a>
      Example link without a title or href attribute
    </a>

Only the first link matches both conditions.

---

# Attribute Selector with a Specific Value

You can also target an attribute with a specific value.

Syntax:

    [attr="value"]

Example:

    input[type="text"] {
      border: 1px solid black;
    }

This targets `<input>` elements where:

    type="text"

Another example:

    a[target="_blank"] {
      color: red;
    }

This targets links where:

    target="_blank"

---

# The `[attr~=value]` Syntax

The `~=` syntax targets an attribute containing a **specific word within a space-separated list**.

Syntax:

    [attr~="value"]

This is particularly useful with the `class` attribute.

Example HTML:

    <a href="https://example.com" class="btn primary large">
      Visit Example Site
    </a>

The class attribute contains three separate values:

    btn
    primary
    large

You can target the `primary` class using:

    a[class~="primary"] {
      color: red;
      font-weight: bold;
    }

This means:

    Find an <a> element
    whose class attribute contains the word "primary"

Because the class attribute is:

    class="btn primary large"

the selector matches it.

---

# Why Use `~=`?

The `~=` operator looks for a **complete word** within a space-separated attribute value.

For example:

    class="btn primary large"

contains:

    btn
    primary
    large

So:

    [class~="primary"]

matches.

It is different from simply searching for the characters `primary` anywhere in the attribute.

---

# The `[attr^=value]` Syntax

The `^=` operator targets an attribute whose value **starts with** a specific value.

Syntax:

    [attr^="value"]

Example:

    a[href^="https://"] {
      color: green;
      text-decoration: underline;
    }

This targets anchor elements where the `href` starts with:

    https://

For example:

    <a href="https://example.com">Visit Example Site</a>

The `href` value is:

    https://example.com

It starts with:

    https://

So the selector matches.

---

# Understanding `^=`

Think:

    ^=

    "Starts with"

Example:

    a[href^="https://"]

means:

    "Select links whose href starts with https://."

---

# The `[attr$=value]` Syntax

The `$=` operator targets an attribute whose value **ends with** a specific value.

Syntax:

    [attr$="value"]

Example:

    a[href$=".com"] {
      color: darkgreen;
      text-decoration: underline dotted;
    }

This targets anchor elements where the `href` ends with:

    .com

For example:

    <a href="https://example.com">Visit Example Site</a>

The `href` value ends with:

    .com

Therefore, the selector matches.

---

# Understanding `$=`

Think:

    $=

    "Ends with"

Example:

    a[href$=".com"]

means:

    "Select links whose href ends with .com."

---

# Attribute Selector Operators

Here are some important attribute selector patterns:

| Syntax | Meaning | Example |
|---|---|---|
| `[attr]` | Has the attribute | `a[href]` |
| `[attr="value"]` | Exact value | `input[type="text"]` |
| `[attr~="value"]` | Contains a whole word in a space-separated list | `a[class~="primary"]` |
| `[attr^="value"]` | Starts with the value | `a[href^="https://"]` |
| `[attr$="value"]` | Ends with the value | `a[href$=".com"]` |

---

# Common Link Examples

### Any link with an `href`

    a[href] {
      color: blue;
    }

Targets:

    <a href="https://example.com">Example</a>

---

### Any link with a `title`

    a[title] {
      font-weight: bold;
    }

Targets:

    <a title="More information">Example</a>

---

### Links with both `href` and `title`

    a[href][title] {
      color: green;
    }

Targets:

    <a href="https://example.com" title="Example">
      Example
    </a>

---

### Links whose `href` starts with `https://`

    a[href^="https://"] {
      color: green;
    }

Targets:

    <a href="https://example.com">Example</a>

---

### Links whose `href` ends with `.com`

    a[href$=".com"] {
      color: darkgreen;
    }

Targets:

    <a href="https://example.com">Example</a>

---

# Attribute Selectors vs Classes

Classes are commonly used to target elements:

    .primary {
      color: red;
    }

But attribute selectors allow you to target elements based directly on their HTML attributes.

For example:

    a[href] {
      color: blue;
    }

This doesn't require adding a class like:

    <a class="has-link" href="https://example.com">

Instead, CSS can directly check whether the `href` attribute exists.

---

# Why Attribute Selectors Are Useful

Attribute selectors can be useful when:

- You don't want to add extra classes.
- Elements need to be styled based on their attributes.
- You need more precise targeting.
- You want to style different types of links differently.
- You want to target values that follow a specific pattern.

For example, you could style secure links differently:

    a[href^="https://"] {
      color: green;
    }

Or target links to `.com` domains:

    a[href$=".com"] {
      color: darkgreen;
    }

---

# Accessibility and Attribute Selectors

Attribute selectors can also help make interactive elements more distinguishable based on their attributes.

For example:

    a[title] {
      font-weight: bold;
    }

This can visually differentiate links that provide additional information through a `title` attribute.

However, CSS styling should complement good HTML structure and accessibility practices rather than replace them.

---

# Key Memory Trick

Remember these:

    [attr]
    ↓
    Has the attribute

    [attr="value"]
    ↓
    Exact value

    [attr~="value"]
    ↓
    Contains a whole word

    [attr^="value"]
    ↓
    Starts with

    [attr$="value"]
    ↓
    Ends with

Easy way to remember:

    ^ = START

    $ = END

    ~= = WHOLE WORD

---

# Quick Summary

- Attribute selectors target HTML elements based on their attributes.
- `a[href]` selects links that have an `href` attribute.
- `a[title]` selects links that have a `title` attribute.
- `a[href][title]` selects links that have both attributes.
- `[attr="value"]` selects elements with an exact attribute value.
- `[attr~="value"]` finds a specific whole word within a space-separated attribute value.
- `[attr^="value"]` selects attributes whose values start with a specific value.
- `[attr$="value"]` selects attributes whose values end with a specific value.
- Attribute selectors are useful for precise styling without always needing additional classes.
- They are especially useful for targeting links based on their `href`, `title`, `class`, or other attributes.
