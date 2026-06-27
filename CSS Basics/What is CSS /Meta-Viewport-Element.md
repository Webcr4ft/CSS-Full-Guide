# What Is the Meta Viewport Element Used For?

The **meta viewport** element is an important part of **responsive web design**.

It tells the browser **how to display and scale** a web page on different devices, especially:

* Mobile phones
* Tablets
* Other small-screen devices

---

# Basic Syntax

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

This element is usually placed inside the HTML `<head>` section.

---

# Understanding Each Part

## `name="viewport"`

```html
name="viewport"
```

* Identifies this as the **viewport** meta element.
* Tells the browser that the settings inside `content` control the page's viewport.

---

## `width=device-width`

```html
width=device-width
```

This tells the browser to:

* Match the page width to the device's screen width.
* Create responsive layouts that work on different screen sizes.

### Example

* Phone → Uses the phone's width.
* Tablet → Uses the tablet's width.
* Desktop → Uses the desktop's width.

---

## `initial-scale=1.0`

```html
initial-scale=1.0
```

This controls the **default zoom level** when the page first loads.

### `1.0` means:

* 100% zoom
* No automatic scaling

---

# Why Is It Important?

Using the meta viewport element ensures that:

* Web pages display correctly on mobile devices.
* Responsive layouts behave as intended.
* Text remains readable.
* Users have a better browsing experience.

---

# What Happens Without It?

If you don't include the viewport element:

* Mobile browsers treat the page like a desktop website.
* The page is shrunk to fit the screen.
* Text becomes very small.
* Users may struggle to read or navigate the page.

---

# Controlling Zoom

The viewport element can also control whether users can zoom.

### Example (Not Recommended)

```html
<meta name="viewport"
      content="width=device-width, initial-scale=1.0, user-scalable=no">
```

The attribute:

```html
user-scalable=no
```

prevents users from zooming in or out.

---

# Why You Should Avoid `user-scalable=no`

Disabling zoom is **not recommended** because:

* It reduces accessibility.
* Many users rely on zoom for readability.
* People with visual impairments may struggle to use your website.

Instead:

* Build responsive layouts.
* Use readable font sizes.
* Allow users to zoom if needed.

---

# Best Practice

Use this viewport tag:

```html
<meta
  name="viewport"
  content="width=device-width, initial-scale=1.0">
```

This allows your website to:

* Adapt to different screen sizes.
* Display correctly on phones, tablets, and desktops.
* Remain accessible to all users.

---

# Quick Summary

| Part | Purpose |
|------|---------|
| `name="viewport"` | Defines the viewport meta element |
| `width=device-width` | Matches the page width to the device width |
| `initial-scale=1.0` | Sets the initial zoom level to 100% |
| `user-scalable=no` | Disables zoom *(not recommended)* |

---

# Key Takeaways

* The **meta viewport** element is essential for responsive web design.
* Always place it inside the HTML `<head>` section.
* Use `width=device-width` to match the screen width.
* Use `initial-scale=1.0` for the default zoom level.
* Avoid `user-scalable=no` because it reduces accessibility.
* A proper viewport setup improves usability and provides a better experience across all devices.
