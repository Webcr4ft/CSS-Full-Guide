## What Is CSS Flexbox?

CSS Flexbox is a **one-dimensional layout model** that allows you to arrange elements in:

* Rows
* Columns

You can also control:

* The order of elements
* The orientation of elements
* How elements are aligned
* How elements resize
* How elements are distributed within a container

Web developers use Flexbox to create **responsive websites and web applications** that adapt to different screen sizes and orientations.

### Why Is Flexbox Called One-Dimensional?

Flexbox focuses on arranging elements along **one axis at a time**.

The axis can be:

* Horizontal
* Vertical


# Flex Containers and Flex Items

There are two important concepts to understand before working with Flexbox:

* **Flex container**
* **Flex item**


## Flex Container

A **flex container** is an HTML element that has a flex layout.

You can arrange and align elements in different ways inside a flex container.

To make an HTML element a flex container, use:

`display: flex;`

Example:

`main {
  display: flex;
}`


## Flex Items

**Flex items** are the **direct children** of a flex container.

Example:

`<main>
  <div id="first-div"></div>
  <div id="second-div"></div>
  <div id="third-div"></div>
</main>`

The three `div` elements become flex items when `main` is a flex container.

Flex items can:

* Be arranged within the container
* Be aligned within the container
* Shrink when necessary
* Expand when there is available space


# Flexbox Example

HTML:

`<main>
  <div id="first-div"></div>
  <div id="second-div"></div>
  <div id="third-div"></div>
</main>`

If you only set the width, height, and background colors:

`div {
  width: 80px;
  height: 50px;
}

#first-div {
  background-color: #4d70b2;
}

#second-div {
  background-color: #5c4db2;
}

#third-div {
  background-color: #4da3b2;
}`

The `div` elements will normally appear on separate rows because `main` is **not a flex container by default**.


# Making an Element a Flex Container

If you add:

`main {
  display: flex;
}`

The `div` elements will be arranged along the same row.

Complete example:

`main {
  display: flex;
}

div {
  width: 80px;
  height: 50px;
}

#first-div {
  background-color: #4d70b2;
}

#second-div {
  background-color: #5c4db2;
}

#third-div {
  background-color: #4da3b2;
}`

The three `div` elements now become **flex items**.

They can also shrink if necessary to fit inside the available space.

By default, a flex container is a **block-level element**, meaning the container itself normally occupies its own row relative to other elements and containers.


# Flex Properties

Flex properties determine how flex items are:

* Arranged
* Resized
* Aligned
* Distributed

Some commonly used Flexbox properties are:

* `flex-direction`
* `justify-content`
* `align-items`
* `flex-wrap`


# The Flex Model

The flex model describes how flex items are arranged inside a flex container.

Every flex container has two axes:

* **Main axis**
* **Cross axis**


## Main Axis

The main axis is the primary direction in which flex items are arranged.


## Cross Axis

The cross axis is perpendicular to the main axis.

By default:

* Main axis = horizontal
* Cross axis = vertical

Flex items are arranged along the **main axis**.


# The `flex-direction` Property

The `flex-direction` property determines the direction of the **main axis**.

The default value is:

`flex-direction: row;`

This places all flex items on the same row.

Example:

`main {
  display: flex;
  flex-direction: row;
}`

`row` follows the direction of the browser's default language:

* Left to right
* Right to left


# `row-reverse`

You can reverse the order of the flex items using:

`flex-direction: row-reverse;`

Example:

`main {
  display: flex;
  flex-direction: row-reverse;
}

div {
  width: 80px;
  height: 50px;
}

#first-div {
  background-color: #4d70b2;
}

#second-div {
  background-color: #5c4db2;
}

#third-div {
  background-color: #4da3b2;
}`

This reverses the order of the flex items along the row.


# `column`

If you want the flex items to be arranged vertically, use:

`flex-direction: column;`

Example:

`main {
  display: flex;
  flex-direction: column;
}

div {
  width: 80px;
  height: 50px;
}

#first-div {
  background-color: #4d70b2;
}

#second-div {
  background-color: #5c4db2;
}

#third-div {
  background-color: #4da3b2;
}`

The items will now be arranged vertically.

The axes change:

* Main axis = vertical
* Cross axis = horizontal


# `column-reverse`

You can reverse the vertical order of the flex items using:

`flex-direction: column-reverse;`

Example:

`main {
  display: flex;
  flex-direction: column-reverse;
}

div {
  width: 80px;
  height: 50px;
}

#first-div {
  background-color: #4d70b2;
}

#second-div {
  background-color: #5c4db2;
}

#third-div {
  background-color: #4da3b2;
}`

This arranges the items vertically while reversing their order.


# `flex-direction` Values

## `row`

`flex-direction: row;`

* Default value
* Items are arranged horizontally
* Items follow the default writing direction


## `row-reverse`

`flex-direction: row-reverse;`

* Items are arranged horizontally
* The order is reversed


## `column`

`flex-direction: column;`

* Items are arranged vertically
* The main axis becomes vertical


## `column-reverse`

`flex-direction: column-reverse;`

* Items are arranged vertically
* The order is reversed


# Quick Summary

CSS Flexbox is a **one-dimensional layout system** used to arrange elements along a single axis.

### Important Concepts

* `display: flex` turns an element into a **flex container**.
* The direct children of a flex container become **flex items**.
* Flex items can shrink or expand to fit available space.
* The **main axis** is the primary direction of the flex layout.
* The **cross axis** is perpendicular to the main axis.

### Important Properties

`display: flex;`

Creates a flex container.

`flex-direction: row;`

Arranges items horizontally in the default direction.

`flex-direction: row-reverse;`

Arranges items horizontally in reverse order.

`flex-direction: column;`

Arranges items vertically.

`flex-direction: column-reverse;`

Arranges items vertically in reverse order.

Other important Flexbox properties include:

`justify-content`

Controls how flex items are distributed along the main axis.

`align-items`

Controls how flex items are aligned along the cross axis.

`flex-wrap`

Controls whether flex items are allowed to wrap onto multiple lines.


# Final Takeaway

CSS Flexbox provides a **flexible and efficient way to arrange elements** within a container.

By understanding:

* Flex containers
* Flex items
* Main axis
* Cross axis
* `display: flex`
* `flex-direction`
* `justify-content`
* `align-items`
* `flex-wrap`

You can create dynamic and responsive layouts that adapt to different screen sizes and orientations.
