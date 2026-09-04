# What Is CSS Flexbox?

## What Is Flexbox?

* **CSS Flexbox** is a layout system used to arrange elements inside a container.
* It can arrange elements:
  * Horizontally → in a row.
  * Vertically → in a column.
* Flexbox is called a **one-dimensional layout system** because it mainly works along **one axis at a time**.
* The two possible directions are:
  * Horizontal
  * Vertical

* Flexbox is especially useful for creating **responsive layouts** that adjust to different screen sizes.

---

# Flex Containers and Flex Items

* There are two important concepts in Flexbox:
  * **Flex container**
  * **Flex item**

## Flex Container

* A **flex container** is an HTML element that has:

    display: flex;

### Example

    <main>
      <div>First</div>
      <div>Second</div>
      <div>Third</div>
    </main>

    main {
      display: flex;
    }

* The `<main>` element is now the **flex container**.

---

## Flex Items

* **Flex items** are the **direct children** of a flex container.

### Example

    <main>
      <div>First</div>
      <div>Second</div>
      <div>Third</div>
    </main>

* `<main>` → Flex container.
* The three `<div>` elements → Flex items.

* Flex items can be:
  * Arranged.
  * Aligned.
  * Resized.
  * Distributed inside the flex container.

---

# What Happens Without Flexbox?

* Block-level `<div>` elements normally appear on separate rows.

### Example

    <main>
      <div id="first-div"></div>
      <div id="second-div"></div>
      <div id="third-div"></div>
    </main>

* Without:

    display: flex;

* The elements will normally appear vertically:

    First
    Second
    Third

---

# What Happens With Flexbox?

* If you add:

    main {
      display: flex;
    }

* The direct children are arranged in a row by default:

    First | Second | Third

* If there is not enough space, flex items can shrink to fit the available space.

---

# The Flex Model

* Every flex container has two axes:

  * **Main axis**
  * **Cross axis**

### By Default

    Main axis   → Horizontal
    Cross axis  → Vertical

* Flex items are arranged along the **main axis**.
* The cross axis is perpendicular to the main axis.

### Easy Way to Remember

    Main axis = Direction the items are going

    Cross axis = Direction across the main axis

---

# `flex-direction`

* The `flex-direction` property determines the direction of the **main axis**.

* It has four common values:

  * `row`
  * `row-reverse`
  * `column`
  * `column-reverse`

---

# `row`

* `row` is the default value.

    main {
      display: flex;
      flex-direction: row;
    }

* The items are arranged horizontally.

    First | Second | Third

---

# `row-reverse`

* `row-reverse` reverses the order of the items.

    main {
      display: flex;
      flex-direction: row-reverse;
    }

* The items appear in the opposite horizontal order.

    Third | Second | First

---

# `column`

* `column` changes the main axis from horizontal to vertical.

    main {
      display: flex;
      flex-direction: column;
    }

* The items are arranged vertically.

    First
      ↓
    Second
      ↓
    Third

---

# `column-reverse`

* `column-reverse` arranges the items vertically but reverses their order.

    main {
      display: flex;
      flex-direction: column-reverse;
    }

* The order becomes:

    Third
      ↓
    Second
      ↓
    First

---

# Flexbox Example

### HTML

    <main>
      <div id="first-div"></div>
      <div id="second-div"></div>
      <div id="third-div"></div>
    </main>

### CSS

    main {
      display: flex;
      flex-direction: row;
    }

    div {
      width: 80px;
      height: 50px;
    }

* `main` → Flex container.
* The three `<div>` elements → Flex items.
* `display: flex` → Activates Flexbox.
* `flex-direction: row` → Places the items horizontally.

---

# Important Flexbox Properties

* Some of the most commonly used Flexbox properties are:

  * `flex-direction` → Controls the direction of the main axis.
  * `justify-content` → Controls how items are distributed along the main axis.
  * `align-items` → Controls how items are aligned along the cross axis.
  * `flex-wrap` → Controls whether items can move onto another line.

---

# Quick Review

| Concept | Meaning |
|---|---|
| `display: flex` | Turns an element into a flex container |
| Flex container | Parent element using Flexbox |
| Flex item | Direct child of a flex container |
| Main axis | The primary direction of the flex layout |
| Cross axis | The direction perpendicular to the main axis |
| `row` | Items arranged horizontally |
| `row-reverse` | Items arranged horizontally in reverse |
| `column` | Items arranged vertically |
| `column-reverse` | Items arranged vertically in reverse |
| `justify-content` | Distributes items along the main axis |
| `align-items` | Aligns items along the cross axis |
| `flex-wrap` | Allows items to move onto another line |

---

# Easy Way to Remember

    display: flex
          ↓
    Turns on Flexbox

    flex-direction
          ↓
    Chooses the direction

    row
          ↓
    Horizontal →

    column
          ↓
    Vertical ↓

    row-reverse
          ↓
    Horizontal ←

    column-reverse
          ↓
    Vertical ↑

---

# Key Things to Remember

* Flexbox is used to arrange elements inside a container.
* Flexbox works along **one dimension at a time**.
* `display: flex` turns an element into a flex container.
* The direct children become flex items.
* The default `flex-direction` is `row`.
* `row` → Horizontal.
* `column` → Vertical.
* `row-reverse` → Horizontal and reversed.
* `column-reverse` → Vertical and reversed.
* The **main axis** is the direction in which the flex items are arranged.
* The **cross axis** is perpendicular to the main axis.
* `justify-content` works along the main axis.
* `align-items` works along the cross axis.
* `flex-wrap` controls whether items can move onto another line.
```
