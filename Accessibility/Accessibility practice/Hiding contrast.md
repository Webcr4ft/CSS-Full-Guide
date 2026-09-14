# What Are Best Practices for Hiding Content So It Doesn't Become Inaccessible?

## Why Does Hiding Content Matter?

- Hiding content is common in web development.
- However, different hiding techniques affect:
  - Visual users
  - Screen readers
  - Other assistive technologies
  - The accessibility tree

- You should choose a hiding technique based on **who should be able to access the content**.

---

# What Is the Accessibility Tree?

- The **accessibility tree** is a structure that represents webpage content and its meaning in a way that assistive technologies can understand.
- Tools such as screen readers use the accessibility tree to interpret and present webpage content to users.

### Important

If content is removed from the accessibility tree:

- Screen readers cannot access it.
- Other assistive technologies generally cannot access it either.

---

# Method 1: display: none

- `display: none` completely hides an element.
- It also removes the element from the accessibility tree.

Example:

  <link rel="stylesheet" href="styles.css">

  <p class="hidden">Hidden text</p>
  <p>Visible text</p>

CSS:

  .hidden {
    display: none;
  }

### Result

- The hidden text is not visually displayed.
- The hidden text is removed from the accessibility tree.
- Screen readers cannot access it.

### When Should You Use It?

Use `display: none` when you want the content to be completely unavailable to:

- Visual users
- Screen reader users
- Other assistive technologies

### Memory Trick

**display: none = Hide from everyone**

---

# Method 2: visibility: hidden

- `visibility: hidden` hides an element visually.
- Unlike `display: none`, the element still takes up space in the document layout.
- However, it is also removed from the accessibility tree.

Example:

  <link rel="stylesheet" href="styles.css">

  <p class="hidden">Hidden text</p>
  <p>Visible text</p>

CSS:

  .hidden {
    visibility: hidden;
  }

### Important Differences

`visibility: hidden`:

- Hides the content visually.
- Keeps the element's space in the layout.
- Removes it from the accessibility tree.
- Prevents screen readers from accessing it.

### When Should You Use It?

Use it when you want to hide the content from **everyone**, including users of assistive technologies.

### Memory Trick

**visibility: hidden = Invisible + inaccessible**

---

# Method 3: Visually Hidden / Screen Reader Only

Sometimes you want content to:

- Be invisible to visual users.
- Remain accessible to screen readers.

For this situation, you can use a **visually hidden** or **screen reader only** technique.

A common class is called `.sr-only`.

Example HTML:

  <link rel="stylesheet" href="styles.css">

  <p class="sr-only">Hidden text</p>
  <p>Visible text</p>

CSS:

  .sr-only {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border: 0;
  }

### Result

- The content is visually hidden.
- The content remains available to screen readers.
- It does not normally affect the visual layout.

---

# Why Use Visually Hidden Content?

This technique is useful when you want to provide **additional context for screen reader users** without displaying that information visually.

For example, a visually hidden piece of text can provide extra information about a control or element that may not be obvious from the visual design.

### Memory Trick

**Visually hidden = Hidden visually, accessible to screen readers**

---

# Method 4: The hidden Attribute

HTML also provides the `hidden` attribute.

Example:

  <p hidden>This content is hidden</p>
  <p>This content is visible</p>

### What Does hidden Do?

The `hidden` attribute:

- Hides the element visually.
- Removes it from the accessibility tree.
- Is supported by most modern browsers.
- Can easily be toggled using JavaScript.

---

# Toggling hidden with JavaScript

The `hidden` attribute is useful when content needs to be shown or hidden dynamically.

Example:

  <p id="message" hidden>This content is hidden.</p>

JavaScript can change the `hidden` state:

  const message = document.querySelector("#message");

  message.hidden = false;

Now the content can become visible.

To hide it again:

  message.hidden = true;

### Memory Trick

**hidden = Easy HTML/JavaScript visibility control**

---

# Comparing the Main Techniques

| Method | Visually Hidden? | In Accessibility Tree? | Takes Up Space? |
|---|---|---|---|
| `display: none` | Yes | No | No |
| `visibility: hidden` | Yes | No | Yes |
| `.sr-only` / visually hidden | Yes | Yes | No |
| `hidden` attribute | Yes | No | No |

---

# Choosing the Right Method

## Completely Hide Content

Use:

  display: none;

or:

  hidden

Use these when the content should not be available to visual users or assistive technologies.

---

## Hide Content from Everyone but Keep Its Space

Use:

  visibility: hidden;

This hides the content but keeps its space in the document layout.

---

## Hide Content Visually but Keep It Accessible

Use a visually hidden / `.sr-only` technique.

Example:

  .sr-only {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border: 0;
  }

This is useful when screen reader users should still receive the information.

---

# Be Careful With Important Content

- Do not hide important information unnecessarily.
- If information is essential for understanding or using your website, it should generally be:
  - Visible
  - Accessible
  - Available to all users

Only hide content when doing so genuinely improves the user experience.

---

# Key Things to Remember

- **Accessibility tree** → Structure that assistive technologies use to understand webpage content.
- `display: none` → Hides content and removes it from the accessibility tree.
- `visibility: hidden` → Hides content, keeps its layout space, and removes it from the accessibility tree.
- `.sr-only` / visually hidden → Hides content visually while keeping it accessible to screen readers.
- `hidden` → Hides content visually and from the accessibility tree.
- JavaScript can toggle the `hidden` attribute.
- Important content should not be unnecessarily hidden.

# Memory Trick

**Need it hidden from everyone?**
→ `display: none` / `hidden`

**Need it invisible but still taking space?**
→ `visibility: hidden`

**Need it invisible but accessible to screen readers?**
→ `.sr-only`

# Quick Summary

There is no single "best" way to hide content.

Choose the technique based on the intended accessibility:

  display: none;
  → Hidden visually + hidden from assistive technology

  visibility: hidden;
  → Hidden visually + hidden from assistive technology + keeps layout space

  .sr-only;
  → Hidden visually + accessible to screen readers

  hidden;
  → Hidden visually + hidden from assistive technology

The most important rule is:

**Don't hide important information from users who need access to it.**
