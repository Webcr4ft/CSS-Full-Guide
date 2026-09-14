# What Is the `z-index` Property, and How Does It Control the Stacking of Positioned Elements?

## What Is `z-index`?

The `z-index` property in CSS controls the **stacking order** of elements that overlap on a webpage.

When multiple elements are placed on top of each other, `z-index` determines which element appears in front and which appears behind.

Think of `z-index` as controlling the **layers** of a webpage.

    Higher z-index → Closer to the viewer → Appears on top

    Lower z-index → Farther from the viewer → Appears behind

---

# Example of Stacking

Imagine three overlapping boxes:

    Box 1
       Box 2
          Box 3

If they overlap, CSS needs to know which box should appear on top.

You can control this using:

    z-index: 1;
    z-index: 2;
    z-index: 3;

The box with `z-index: 3` will generally appear above the box with `z-index: 2`, and the box with `z-index: 2` will appear above the box with `z-index: 1`.

---

# Important Rule: `z-index` and Positioning

`z-index` is commonly used with **positioned elements**.

A positioned element is an element whose `position` is something other than:

    position: static;

For example:

    position: relative;
    position: absolute;
    position: fixed;
    position: sticky;

These positioning methods can be used with `z-index` to control stacking.

---

# Default `z-index` Value

The default value of `z-index` is:

    z-index: auto;

`auto` means the element uses the default stacking order determined by the browser.

You can explicitly specify a `z-index` when you need to control which overlapping element appears on top.

---

# Example with Three Boxes

HTML:

    <div class="container">
      <div class="box1">Box 1</div>
      <div class="box2">Box 2</div>
      <div class="box3">Box 3</div>
    </div>

CSS:

    .container {
      position: relative;
      width: 300px;
      height: 300px;
      border: 1px solid black;
    }

    .box1 {
      position: absolute;
      z-index: 1;
      background: lightcoral;
      top: 20px;
      left: 20px;
      width: 100px;
      height: 100px;
    }

    .box2 {
      position: absolute;
      z-index: 3;
      background: gold;
      top: 40px;
      left: 40px;
      width: 100px;
      height: 100px;
    }

    .box3 {
      position: absolute;
      z-index: 2;
      background: lightgreen;
      top: 60px;
      left: 60px;
      width: 100px;
      height: 100px;
    }

---

# How the Example Works

The container uses:

    position: relative;

This creates a positioned container for the absolutely positioned boxes.

Each box uses:

    position: absolute;

This allows the boxes to be positioned independently and overlap.

Each box also has a different `z-index` value:

    Box 1 → z-index: 1

    Box 3 → z-index: 2

    Box 2 → z-index: 3

Therefore, when the boxes overlap:

    Box 2 → Appears on top
    Box 3 → Appears behind Box 2
    Box 1 → Appears behind both

---

# Why Are the Boxes Overlapping?

The boxes are given different `top` and `left` values.

For example:

    .box1 {
      top: 20px;
      left: 20px;
    }

    .box2 {
      top: 40px;
      left: 40px;
    }

    .box3 {
      top: 60px;
      left: 60px;
    }

Because the boxes are close together and each is 100px by 100px, they overlap.

The `z-index` then controls which overlapping box appears in front.

---

# Higher `z-index` = Higher Layer

For example:

    .box1 {
      z-index: 1;
    }

    .box2 {
      z-index: 5;
    }

    .box3 {
      z-index: 10;
    }

The stacking order is:

    Box 3 → z-index: 10 → Top

    Box 2 → z-index: 5

    Box 1 → z-index: 1 → Bottom

A higher `z-index` places an element higher in the stacking order.

---

# Negative `z-index` Values

`z-index` can also use negative values.

Example:

    .box {
      position: relative;
      z-index: -1;
    }

A negative `z-index` can place an element behind other elements in the stacking order.

Use negative values carefully because the element may end up behind its parent or other page content depending on the stacking context.

---

# `z-index` Does Not Move Elements

An important thing to remember is that `z-index` does **not** control an element's position on the page.

It only controls its stacking order.

For example:

    .box {
      position: absolute;
      top: 20px;
      left: 20px;
      z-index: 5;
    }

These properties do different jobs:

    top: 20px;
    ↓
    Controls vertical position

    left: 20px;
    ↓
    Controls horizontal position

    z-index: 5;
    ↓
    Controls stacking order

---

# `z-index` as Layers

A simple way to understand `z-index` is to imagine your webpage as a stack of transparent sheets.

For example:

    Layer 3 → z-index: 3
    Layer 2 → z-index: 2
    Layer 1 → z-index: 1

The higher layer appears closer to you.

You can think of it like:

    z-index: 10 → Very high layer

    z-index: 5  → Middle layer

    z-index: 1  → Lower layer

---

# Common Uses of `z-index`

`z-index` is especially useful when elements overlap.

Common examples include:

- Modals
- Pop-ups
- Tooltips
- Dropdown menus
- Navigation menus
- Notification badges
- Overlays
- Floating UI elements
- Menus appearing above other content

For example, a modal might need to appear above everything else:

    .modal {
      position: fixed;
      z-index: 1000;
    }

A dropdown menu might use:

    .dropdown {
      position: absolute;
      z-index: 10;
    }

The exact number isn't important by itself. What matters is how it compares with the `z-index` values of the other overlapping elements.

---

# Common Mistake

A common mistake is to use `z-index` without considering positioning.

For example:

    .box {
      z-index: 10;
    }

If the element is still using:

    position: static;

`z-index` may not behave as expected for ordinary stacking control.

A common approach is:

    .box {
      position: relative;
      z-index: 10;
    }

---

# Container and Child Elements

A common CSS pattern is:

    .container {
      position: relative;
    }

    .child {
      position: absolute;
      z-index: 2;
    }

The container establishes the positioning context, while the child can be positioned and layered inside it.

---

# Important Difference: Position vs `z-index`

Don't confuse these properties.

### `position`

Controls how an element is positioned.

Examples:

    position: relative;
    position: absolute;
    position: fixed;
    position: sticky;

### `z-index`

Controls the stacking order of overlapping elements.

Example:

    z-index: 5;

So:

    position → Where/how the element is positioned

    z-index → Which overlapping layer it appears on

---

# Simple Example

HTML:

    <div class="box red">Red</div>
    <div class="box blue">Blue</div>

CSS:

    .box {
      position: absolute;
      width: 100px;
      height: 100px;
    }

    .red {
      z-index: 1;
    }

    .blue {
      z-index: 2;
    }

If the boxes overlap:

    Blue → z-index: 2 → Appears on top

    Red → z-index: 1 → Appears behind

---

# Key Memory Trick

Remember:

**`z-index` = Layer order**

Think about a stack of papers:

    z-index: 3
    ─────────
    z-index: 2
    ─────────
    z-index: 1

The higher number is closer to the viewer.

Another easy way to remember:

    Higher z-index → Higher layer → More in front

    Lower z-index → Lower layer → More behind

---

# Quick Summary

- `z-index` controls the stacking order of overlapping elements.
- A higher `z-index` generally places an element above one with a lower `z-index`.
- `z-index` is commonly used with positioned elements.
- Positioned elements can use:
  - `relative`
  - `absolute`
  - `fixed`
  - `sticky`
- The default `z-index` value is `auto`.
- `z-index` controls stacking, not the element's physical position.
- `top` and `left` control position.
- `z-index` controls which overlapping layer appears on top.
- A common pattern is to use `position: relative` on a container and `position: absolute` on its children.
- `z-index` is useful for modals, pop-ups, tooltips, dropdowns, overlays, and other overlapping UI elements.
