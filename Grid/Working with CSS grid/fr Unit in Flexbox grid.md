# How Can You Create Flexible Grids with the `fr` Unit?

In the previous lesson, you were introduced to **CSS Grid**, which can be used to create complex and fluid layouts in your web pages.

In this lesson, we will explore how to create flexible grid layouts using the `fr` unit.

## Creating a Grid Container

Let's start with this HTML markup, which is going to represent our grid container:

    <div class="grid-container">
      <div class="col"></div>
      <div class="col"></div>
      <div class="col"></div>
      <div class="col"></div>
    </div>

Inside the CSS, we set the `display` property to `grid` for the container:

    <link rel="stylesheet" href="styles.css" />

    <div class="grid-container">
      <div class="col"></div>
      <div class="col"></div>
      <div class="col"></div>
      <div class="col"></div>
    </div>

    html,
    body {
      width: 90%;
      height: 50%;
    }

    .grid-container {
      display: grid;
      grid-template-columns: 25% 25% 25% 25%;
      gap: 15px;
      background-color: darkgray;
      height: 100%;
    }

    .col {
      background-color: darkslateblue;
    }

The `grid-template-columns` property is used to set the size for each column.

In this case, each column size will be **25% of the container**.

Then the `gap` property is used to create space between each column.

## Using the `fr` Unit

So far, we have been using percentages for the column size, but we can also use the `fr` unit.

The `fr` unit is a **fractional unit** that represents a fraction of the available space for the grid container.

Here is what the code will look like when it is refactored to use `fr` units instead of percentages:

    <link rel="stylesheet" href="styles.css" />

    <div class="grid-container">
      <div class="col"></div>
      <div class="col"></div>
      <div class="col"></div>
      <div class="col"></div>
    </div>

    html,
    body {
      width: 90%;
      height: 50%;
    }

    .grid-container {
      display: grid;
      grid-template-columns: 1fr 1fr 1fr 1fr;
      gap: 15px;
      background-color: darkgray;
      height: 100%;
    }

    .col {
      background-color: darkslateblue;
    }

Each column will take up **one fraction of the available space**.

Since there are four columns, each column will have an equal share of the available space in the grid container.

## Why Use the `fr` Unit?

As you start to build your grid layouts, you will find yourself wanting to use `fr` units more often because they provide a **flexible and proportional way to distribute space**.

This allows you to create **responsive layouts** that adapt to varying screen sizes without needing to manually adjust pixel values.

### Key Points

* `fr` stands for **fractional unit**.
* `1fr` represents one fraction of the available grid space.
* `1fr 1fr 1fr 1fr` creates four equal columns.
* `fr` units make it easier to create flexible and responsive layouts.
* The `gap` property controls the space between grid items.
