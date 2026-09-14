# What Is Relative Positioning, and How Does This Differ from Default Static Positioning?

## What Is CSS Positioning?

CSS positioning allows you to control how elements are placed and moved on a webpage.

Two important positioning types are:

- `static` — the default positioning.
- `relative` — allows an element to be moved from its normal position while keeping its original space in the layout.

---

# Static Positioning

Static positioning is the **default positioning for all HTML elements**.

You don't need to write `position: static` because elements are statically positioned by default.

Example:

    <p>This paragraph is statically positioned.</p>

With static positioning:

- The element follows the normal document flow.
- Elements appear one after another.
- Content generally flows from top to bottom and left to right.
- The element stays where it naturally occurs in the document.
- `top`, `right`, `bottom`, and `left` don't move a statically positioned element.

Think of static positioning as:

    "Put the element where it naturally belongs."

---

# Normal Document Flow

The normal document flow determines where elements naturally appear on a webpage.

For example:

    <p>First paragraph</p>
    <p>Second paragraph</p>
    <p>Third paragraph</p>

The browser places them in their normal positions, one after another.

Nothing is manually moved.

---

# Relative Positioning

Relative positioning allows you to move an element **from its normal position**.

You use:

    position: relative;

Example HTML:

    <link rel="stylesheet" href="styles.css">

    <p class="relative">This paragraph is positioned relatively.</p>

Example CSS:

    body {
      border: solid 1px black;
    }

    .relative {
      position: relative;
      top: 30px;
      left: 30px;
    }

The paragraph will be moved:

- `30px` downward because of `top: 30px`.
- `30px` to the right because of `left: 30px`.

---

# The Important Difference

The biggest difference between `static` and `relative` positioning is that relative positioning allows you to move an element while **preserving the space it originally occupied**.

For example:

    .relative {
      position: relative;
      top: 30px;
      left: 30px;
    }

The paragraph visually moves 30px down and 30px right.

However, the browser still keeps the paragraph's original space in the normal document flow.

This means other elements behave as if the paragraph were still in its original position.

---

# How Relative Positioning Works

Think of relative positioning like this:

    Original position
          ↓
    [ Element ]
          ↓
    Move it visually
          ↓
    [ Element ] → 30px right
          ↓
    30px down

The element is moved relative to where it would normally have been.

Its original position is still reserved.

---

# The `top` Property

The `top` property moves a relatively positioned element downward or upward.

Example:

    .box {
      position: relative;
      top: 30px;
    }

This moves the element **30px downward**.

Important:

    top: 30px;

means move down 30px.

A negative value moves it upward:

    top: -30px;

---

# The `left` Property

The `left` property moves a relatively positioned element horizontally.

Example:

    .box {
      position: relative;
      left: 30px;
    }

This moves the element **30px to the right**.

A negative value moves it to the left:

    left: -30px;

---

# `right` and `bottom`

You can also use:

- `top`
- `right`
- `bottom`
- `left`

Example:

    .box {
      position: relative;
      right: 20px;
    }

This moves the element 20px to the left.

Example:

    .box {
      position: relative;
      bottom: 20px;
    }

This moves the element 20px upward.

---

# Static vs Relative

| Feature | Static | Relative |
|---|---|---|
| Default positioning? | Yes | No |
| Follows normal document flow? | Yes | Yes |
| Can use `top`, `right`, `bottom`, `left` to move it? | No | Yes |
| Original space preserved? | Yes | Yes |
| Can visually move from its normal position? | No | Yes |

---

# Simple Example

HTML:

    <div>First</div>
    <div class="relative">Second</div>
    <div>Third</div>

CSS:

    .relative {
      position: relative;
      top: 20px;
      left: 20px;
    }

The second element moves 20px down and 20px right.

However, the space where the second element originally was remains reserved.

The third element does not move into the second element's original position.

---

# Why Use Relative Positioning?

Relative positioning is useful when you want to:

- Move an element slightly from its normal position.
- Adjust the visual position of an element.
- Create small layout adjustments.
- Position other elements relative to it when using more advanced positioning techniques.

It is especially useful when you need to move something without removing its original space from the document flow.

---

# Key Memory Trick

**Static = Stay in the normal position.**

**Relative = Move from the normal position, but keep the original space.**

Think:

    STATIC
    ↓
    Natural position

    RELATIVE
    ↓
    Natural position + visual movement
    ↓
    Original space is still preserved

---

# Quick Summary

- `position: static` is the default positioning for elements.
- Static elements remain in their natural position in the normal document flow.
- `position: relative` allows an element to be moved from its normal position.
- Relative positioning uses properties such as `top`, `right`, `bottom`, and `left`.
- `top: 30px` moves the element 30px downward.
- `left: 30px` moves the element 30px to the right.
- The element's original space is still preserved when using relative positioning.
- Relative positioning is useful for making small position adjustments without disrupting the surrounding layout.
