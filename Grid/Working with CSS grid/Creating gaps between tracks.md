# How Can You Create Gaps Between Tracks in a Grid?

In the previous lessons, we talked a little bit about how to create space between grid items.

In this lesson, we will dive into more detail about how to use the `row-gap`, `column-gap`, and `gap` properties in a grid layout.

## What Is a Track in CSS Grid?

Before we continue, we need to review what a **track** is in CSS Grid.

A track is the space between two neighboring grid lines. These lines are automatically created when you use CSS Grid.

In this context, tracks generally refer to the **rows and columns** that make up the grid layout.

## The `column-gap` Property

To create gaps between columns in a CSS Grid, you can use the `column-gap` property.

Acceptable values for this property include:

* Pixels, such as `10px`
* The `em` unit
* Percentages, such as `5%`
* The `normal` keyword

If you use the `normal` value for the `column-gap` property, then the result will be `0` for grid layouts.

Here is an example of the markup for a four-column grid layout:

    <div class="grid-container">
      <div></div>
      <div></div>
      <div></div>
      <div></div>
    </div>

For the CSS, we set the `display` property to `grid` and the `column-gap` property to `10px`:

    <link rel="stylesheet" href="styles.css">

    <div class="grid-container">
      <div></div>
      <div></div>
      <div></div>
      <div></div>
    </div>

    .grid-container {
      display: grid;
      height: 100px;
      grid-template-columns: 1fr 1fr 1fr 1fr;
      column-gap: 10px;
    }

    .grid-container div {
      background-color: darkblue;
    }

The `column-gap: 10px` creates a **10-pixel gap between the columns**.

## The `row-gap` Property

If we wanted to change the example to have two rows of blue boxes and create more space between the rows, we can use the `row-gap` property:

    <link rel="stylesheet" href="styles.css">

    <div class="grid-container">
      <div></div>
      <div></div>
      <div></div>
      <div></div>
    </div>

    .grid-container {
      display: grid;
      grid-template-columns: 1fr 1fr;
      column-gap: 10px;
      row-gap: 30px;
    }

    .grid-container div {
      height: 100px;
      background-color: darkblue;
    }

In this revised example, we are setting the `row-gap` property to `30px`.

We are also changing the `grid-template-columns` to use just two `1fr` units instead of four, which creates two columns and allows the four items to form two rows.

Just like the `column-gap` property, acceptable values for the `row-gap` property can include:

* Percentages
* `em`
* Pixels

## The `gap` Shorthand Property

If you want to use a shorthand for creating gaps between rows and columns, you can use the `gap` property.

The basic syntax is:

    gap: row-value optional-column-value;

If you specify **one value** for the `gap` property, then that value will be applied to both rows and columns.

For example:

    gap: 20px;

This creates a `20px` gap between both rows and columns.

If you specify **two values**, then:

* The first value applies to the rows.
* The second value applies to the columns.

For example:

    gap: 30px 10px;

This creates a `30px` gap between rows and a `10px` gap between columns.

Here is a complete example:

    <link rel="stylesheet" href="styles.css">

    <div class="grid-container">
      <div></div>
      <div></div>
      <div></div>
      <div></div>
    </div>

    .grid-container {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 30px 10px;
    }

    .grid-container div {
      height: 100px;
      background-color: darkblue;
    }

## Acceptable Values for `gap`

Acceptable values for the `gap` shorthand property include:

* Percentages
* Pixels
* `em`
* `calc()` values

However, you **cannot use `fr` units** for the `gap` property.

## Summary

The `row-gap`, `column-gap`, and `gap` properties provide flexible ways to control spacing between items in a CSS Grid layout.

### Key Points

* `column-gap` controls the space between **columns**.
* `row-gap` controls the space between **rows**.
* `gap` is a shorthand for controlling both row and column gaps.
* One `gap` value applies to both rows and columns.
* Two `gap` values follow the order: `row-gap column-gap`.
* Gap values can use units such as `px`, `%`, `em`, and `calc()`.
* `fr` units cannot be used for `gap`.

By using these properties, you can easily create visually appealing grids with consistent and adjustable gaps between rows and columns.
