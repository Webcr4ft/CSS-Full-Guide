# What Is the text-shadow Property, and How Does It Work?

## What Is text-shadow?

- CSS does **not** add shadows to text by default.
- The `text-shadow` property allows you to add one or more shadows to text.
- You can control:
  - Horizontal position (X offset)
  - Vertical position (Y offset)
  - Blur
  - Color

Basic syntax:

  text-shadow: /* Values */

---

# The Basic text-shadow Syntax

The common structure is:

  text-shadow: X-offset Y-offset blur-radius color;

Example:

  p {
    text-shadow: 3px 2px 3px #00ffc3;
  }

The values mean:

- `3px` → X offset
- `2px` → Y offset
- `3px` → Blur radius
- `#00ffc3` → Shadow color

---

# X and Y Offset Values

The first two values control the position of the shadow.

## X Offset

- Controls the **horizontal** position.
- Positive value → moves the shadow **right**.
- Negative value → moves the shadow **left**.

## Y Offset

- Controls the **vertical** position.
- Positive value → moves the shadow **down**.
- Negative value → moves the shadow **up**.

### Important

The X and Y offsets are **required**.

Example:

  p {
    text-shadow: 3px 2px;
  }

Here:

- `3px` → X offset → right
- `2px` → Y offset → down

---

# Adding a Color

You can add a color to the shadow.

Example:

  p {
    text-shadow: 3px 2px #00ffc3;
  }

The color can be written after the offsets.

You can also write the color before the offsets:

  p {
    text-shadow: #00ffc3 3px 2px;
  }

Both are equivalent.

### Color Formats

You can use any valid CSS color format, such as:

- Hexadecimal
- `rgb()`
- `rgba()`
- Named colors
- `hsl()`

Example:

  p {
    text-shadow: 3px 2px red;
  }

---

# Positive and Negative Offsets

Positive and negative values change the direction of the shadow.

## Positive Values

  p {
    text-shadow: 3px 2px #00ffc3;
  }

- `3px` X offset → shadow moves right.
- `2px` Y offset → shadow moves down.

## Negative Values

  p {
    text-shadow: -3px -2px #00ffc3;
  }

- `-3px` X offset → shadow moves left.
- `-2px` Y offset → shadow moves up.

### Memory Trick

**X:**
- `+` → Right
- `-` → Left

**Y:**
- `+` → Down
- `-` → Up

---

# The Blur Radius

- The third value controls the **blur radius**.
- Blur radius is optional.
- Its default value is `0`.

Example without blur:

  p {
    text-shadow: 3px 2px #00ffc3;
  }

- With no blur, the shadow can look like an exact copy of the text behind the original.

Example with blur:

  p {
    text-shadow: 3px 2px 3px #00ffc3;
  }

Here:

- `3px` → X offset
- `2px` → Y offset
- `3px` → Blur radius
- `#00ffc3` → Color

---

# How Blur Radius Works

- `0` → No blur.
- Small value → Slight blur.
- Larger value → More blur.
- More blur makes the shadow softer and lighter.

Example:

  text-shadow: 3px 2px 1px black;

  text-shadow: 3px 2px 5px black;

  text-shadow: 3px 2px 10px black;

As the blur radius increases, the shadow becomes more spread out and subtle.

---

# Complete text-shadow Example

HTML:

  <p>Hello, World!</p>

CSS:

  p {
    text-shadow: 3px 2px 3px #00ffc3;
  }

This creates a shadow that is:

- 3px to the right.
- 2px downward.
- Blurred by 3px.
- Colored `#00ffc3`.

---

# Adding Multiple Shadows

- You can apply **multiple shadows** to the same text.
- Separate each shadow with a comma.

Example:

  p {
    text-shadow:
      3px 2px 3px #00ffc3,
      -3px -2px 3px #0077ff,
      5px 4px 3px #dee7e5;
  }

This creates three different shadows.

### Structure

  text-shadow:
    shadow-1,
    shadow-2,
    shadow-3;

Each shadow can have its own:

- X offset
- Y offset
- Blur radius
- Color

---

# Shadow Layering

Multiple shadows are applied in layers.

- The **first shadow** is at the top/front.
- Later shadows are placed behind it.

Example:

  p {
    text-shadow:
      3px 2px 3px #00ffc3,
      -3px -2px 3px #0077ff,
      5px 4px 3px #dee7e5;
  }

The first shadow is rendered above the following shadows.

---

# text-shadow Values

The basic pattern to remember is:

  text-shadow: X Y BLUR COLOR;

Example:

  text-shadow: 3px 2px 3px #00ffc3;

Meaning:

  X → 3px
  Y → 2px
  Blur → 3px
  Color → #00ffc3

---

# Quick Direction Guide

  text-shadow: 3px 2px;
                  ↑    ↑
                  X    Y

X offset:

  3px  → Right
  -3px → Left

Y offset:

  2px  → Down
  -2px → Up

Blur:

  0px → Sharp
  3px → Slightly blurred
  10px → Very blurred

---

# Key Things to Remember

- `text-shadow` adds shadows to text.
- X and Y offsets are required.
- X controls horizontal movement.
- Y controls vertical movement.
- Positive X → Right.
- Negative X → Left.
- Positive Y → Down.
- Negative Y → Up.
- Blur radius is optional.
- Blur radius defaults to `0`.
- A larger blur radius creates a softer, more spread-out shadow.
- Color can be placed before or after the offset values.
- Multiple shadows are separated by commas.
- The first shadow is rendered at the top/front of the shadow layers.

# Memory Trick

**text-shadow = X + Y + Blur + Color**

  text-shadow: 3px 2px 3px #00ffc3;

Think:

**Where? → X/Y**  
**How soft? → Blur**  
**What color? → Color**

# Quick Summary

The `text-shadow` property lets you create different shadow effects for text.

Basic:

  text-shadow: 3px 2px;

With color:

  text-shadow: 3px 2px #00ffc3;

With blur:

  text-shadow: 3px 2px 3px #00ffc3;

With multiple shadows:

  text-shadow:
    3px 2px 3px #00ffc3,
    -3px -2px 3px #0077ff,
    5px 4px 3px #dee7e5;

The main values to master are:

**X offset → Y offset → Blur → Color**
