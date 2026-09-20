# How Do the `grid-column` and `grid-row` Properties Work?

The `grid-column` and `grid-row` properties let you specify the horizontal and vertical placement of grid items within a grid layout.

In other words, they both allow you to control where a grid item begins and ends by referencing **grid lines**.

Grid lines are the boundaries that separate rows and columns that you have already defined using the `grid-template-rows` and `grid-template-columns` properties.

---

## Syntax of `grid-row` and `grid-column`

The syntax of the `grid-row` property is:

    grid-row: <start-line> / <end-line>;

The syntax of the `grid-column` property is:

    grid-column: <start-line> / <end-line>;

* `<start-line>` is the grid line where the item starts.
* `<end-line>` is the grid line where the item ends.
* Grid lines are **1-indexed**, meaning you start counting from `1`, not `0`.

Remember that grid lines for rows are generated based on the number of rows specified in the `grid-template-rows` property.

The same applies to columns with the `grid-template-columns` property.

For example:

    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(3, 100px);

A grid with **4 columns** has **5 vertical grid lines**.

A grid with **3 rows** has **4 horizontal grid lines**.

---

## Basic Grid Example

Here is an example grid with 4 columns and 3 rows:

    <link rel="stylesheet" href="styles.css">

    <div class="grid">
      <div class="item1">1</div>
      <div class="item2">2</div>
      <div class="item3">3</div>
      <div class="item4">4</div>
      <div class="item5">5</div>
      <div class="item6">6</div>
      <div class="item7">7</div>
      <div class="item8">8</div>
      <div class="item9">9</div>
      <div class="item10">10</div>
      <div class="item11">11</div>
      <div class="item12">12</div>
    </div>

    .grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr); /* 4 equal columns */
      grid-template-rows: repeat(3, 100px); /* 3 equal rows */
      gap: 10px;
    }

    .grid > div {
      display: grid;
      place-items: center;
      background: crimson;
      color: white;
      font-size: 4rem;
    }

Inspecting the grid container shows that each row and column is bounded by two lines:

* A **start line** at the beginning of the row or column.
* An **end line** at the end of the row or column.

You can target these grid lines with `grid-row` and `grid-column` to control where an item is placed.

---

## Using `grid-column`

You can use `grid-column` to control how many columns a grid item occupies.

For example, you can make the first grid item occupy the first two columns:

    <link rel="stylesheet" href="styles.css">

    <div class="grid">
      <div class="item1">1</div>
      <div class="item2">2</div>
      <div class="item3">3</div>
      <div class="item4">4</div>
      <div class="item5">5</div>
      <div class="item6">6</div>
      <div class="item7">7</div>
      <div class="item8">8</div>
      <div class="item9">9</div>
      <div class="item10">10</div>
      <div class="item11">11</div>
      <div class="item12">12</div>
    </div>

    .grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr); /* 4 equal columns */
      grid-template-rows: repeat(3, 100px); /* 3 equal rows */
      gap: 10px;
    }

    .grid > div {
      display: grid;
      place-items: center;
      background: crimson;
      color: white;
      font-size: 4rem;
    }

    .item1 {
      grid-column: 1 / 3;
    }

With this:

    grid-column: 1 / 3;

You are saying that the first grid item should:

* Start at grid line `1`.
* End at grid line `3`.
* Occupy the space between those lines.

This means the first item occupies **two columns**.

The fourth item gets pushed to the second row because the first item is now taking up the first two column spaces.

---

## Using `grid-row`

You can also use `grid-row` to control how many rows an item occupies.

For example:

    .item1 {
      grid-column: 1 / 3;
      grid-row: 1 / 3;
    }

The `grid-row` property:

    grid-row: 1 / 3;

means that the item:

* Starts at row grid line `1`.
* Ends at row grid line `3`.
* Occupies the space between those lines.
* Therefore spans **two rows**.

Together:

    .item1 {
      grid-column: 1 / 3;
      grid-row: 1 / 3;
    }

The first item occupies **two columns and two rows**.

---

## Complete Example Using `grid-column` and `grid-row`

    <link rel="stylesheet" href="styles.css">

    <div class="grid">
      <div class="item1">1</div>
      <div class="item2">2</div>
      <div class="item3">3</div>
      <div class="item4">4</div>
      <div class="item5">5</div>
      <div class="item6">6</div>
      <div class="item7">7</div>
      <div class="item8">8</div>
      <div class="item9">9</div>
      <div class="item10">10</div>
      <div class="item11">11</div>
      <div class="item12">12</div>
    </div>

    .grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr); /* 4 equal columns */
      grid-template-rows: repeat(3, 100px); /* 3 equal rows */
      gap: 10px;
    }

    .grid > div {
      display: grid;
      place-items: center;
      background: crimson;
      color: white;
      font-size: 4rem;
    }

    .item1 {
      grid-column: 1 / 3;
      grid-row: 1 / 3;
    }

---

## Using the `span` Keyword

You can also use the `span` keyword to tell a grid item how many rows or columns it should occupy.

For example:

    grid-column: 1 / 3;

is equivalent to:

    grid-column: 1 / span 2;

Both mean that the item starts at grid line `1` and spans **two columns**.

Similarly:

    grid-row: 1 / 3;

is equivalent to:

    grid-row: 1 / span 2;

Both make the item span **two rows**.

---

## Example Using `span`

    <link rel="stylesheet" href="styles.css">

    <div class="grid">
      <div class="item1">1</div>
      <div class="item2">2</div>
      <div class="item3">3</div>
      <div class="item4">4</div>
      <div class="item5">5</div>
      <div class="item6">6</div>
      <div class="item7">7</div>
      <div class="item8">8</div>
      <div class="item9">9</div>
      <div class="item10">10</div>
      <div class="item11">11</div>
      <div class="item12">12</div>
    </div>

    .grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr); /* 4 equal columns */
      grid-template-rows: repeat(3, 100px); /* 3 equal rows */
      gap: 10px;
    }

    .grid > div {
      display: grid;
      place-items: center;
      background: crimson;
      color: white;
      font-size: 4rem;
    }

    .item1 {
      grid-column: 1 / span 2;
      grid-row: 1 / span 2;
    }

Here:

    grid-column: 1 / span 2;

means:

* Start at column grid line `1`.
* Span across `2` columns.

And:

    grid-row: 1 / span 2;

means:

* Start at row grid line `1`.
* Span across `2` rows.

The `span` keyword can make it easier to think about the number of tracks an item should occupy.

---

## Applying the Technique to Other Items

You can continue to apply this technique to any item on the grid and place the items wherever you want.

By changing the starting grid line and the number of rows or columns to span, you can create different layouts.

This technique can also be used to create layouts such as **masonry-style grid layouts**.

---

## Creating a Masonry Layout

Here is a new example:

    <link rel="stylesheet" href="styles.css">

    <div class="grid">
      <div class="item1">1</div>
      <div class="item2">2</div>
      <div class="item3">3</div>
      <div class="item4">4</div>
      <div class="item5">5</div>
      <div class="item6">6</div>
      <div class="item7">7</div>
    </div>

    .grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr); /* 4 equal columns */
      grid-template-rows: repeat(4, 100px); /* 4 equal rows */
      gap: 10px;
    }

    .grid > div {
      display: grid;
      place-items: center;
      background: crimson;
      color: white;
      font-size: 4rem;
    }

    .item1 {
      grid-column: 1 / span 2;
    }

    .item4 {
      grid-column: 1 / span 3;
    }

    .item6 {
      grid-column: 1 / span 2;
    }

    .item7 {
      grid-column: 3 / span 2;
    }

Here, different grid items are given different column spans:

* `.item1` starts at column line `1` and spans `2` columns.
* `.item4` starts at column line `1` and spans `3` columns.
* `.item6` starts at column line `1` and spans `2` columns.
* `.item7` starts at column line `3` and spans `2` columns.

This allows the items to occupy different amounts of space and creates a more varied, masonry-style layout.

---

## Key Points

* `grid-column` controls the horizontal placement of a grid item.
* `grid-row` controls the vertical placement of a grid item.
* Both properties use grid lines to determine where an item starts and ends.
* Grid lines are **1-indexed**, so counting starts from `1`.
* `grid-column: 1 / 3` makes an item span two columns.
* `grid-row: 1 / 3` makes an item span two rows.
* `span` can be used to specify how many tracks an item should occupy.
* `grid-column: 1 / span 2` means start at line `1` and span two columns.
* `grid-row: 1 / span 2` means start at line `1` and span two rows.
* You can combine `grid-column` and `grid-row` to create complex grid layouts.
* These properties can also be used to create masonry-style layouts.
