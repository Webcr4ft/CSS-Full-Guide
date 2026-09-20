# How Can You Repeat Track Listings in a Grid Layout?

In the previous lessons, we have been working with the `grid-template-columns` property and setting the value to a few fractional units.

For example:

    <link rel="stylesheet" href="styles.css">

    <div class="grid-container">
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
    </div>

    .grid-container {
      display: grid;
      grid-template-columns: 1fr 1fr 1fr 1fr;
      column-gap: 10px;
    }

    .box {
      width: 100px;
      height: 100px;
      background-color: darkblue;
    }

While the following code is completely valid, there is an easier way to repeat a section or all of your track listings.

## The `repeat()` Function

The `repeat()` function is used to repeat a section or all of the tracks for columns or rows.

This function takes in:

* A **repeat count**
* The **tracks you wish to repeat**

The basic syntax is:

    repeat(count, tracks)

Here is a revised version of the earlier example using the `repeat()` function:

    <link rel="stylesheet" href="styles.css">

    <div class="grid-container">
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
    </div>

    .grid-container {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      column-gap: 10px;
    }

    .box {
      width: 100px;
      height: 100px;
      background-color: darkblue;
    }

There won't be a change in the styles displayed in the browser, but this is a more concise way to write repeated values for the columns.

Instead of writing:

    grid-template-columns: 1fr 1fr 1fr 1fr;

You can write:

    grid-template-columns: repeat(4, 1fr);

This tells the browser to repeat `1fr` **four times**.

## Repeating Patterns

The `repeat()` function will accept any valid pattern that you can use for rows or columns.

Here is an example using the `repeat()` function to set the first and third columns to `20px` and the second and fourth columns to one fractional unit:

    <link rel="stylesheet" href="styles.css">

    <div class="grid-container">
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
    </div>

    .grid-container {
      display: grid;
      grid-template-columns: repeat(2, 20px 1fr);
      column-gap: 10px;
    }

    .grid-container div {
      height: 100px;
      background-color: darkblue;
    }

The following:

    repeat(2, 20px 1fr);

produces the same pattern as:

    20px 1fr 20px 1fr

So the `repeat()` function can be useful not only for repeating a single value but also for repeating an entire pattern.

## Summary

Sometimes, you might opt to write out each individual value instead of using the `repeat()` function.

However, there are times when this function comes in handy, especially when you want to repeat a particular pattern for a track listing.

### Key Points

* `repeat()` allows you to repeat columns or rows.
* The first value specifies **how many times** to repeat the pattern.
* The second value specifies **what to repeat**.
* `repeat(4, 1fr)` creates four equal fractional tracks.
* `repeat(2, 20px 1fr)` repeats the `20px 1fr` pattern twice.
* Using `repeat()` makes your CSS more concise and easier to maintain.
