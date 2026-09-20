# What Is the Difference Between an Implicit and Explicit Grid?

## Implicit Grid

An **implicit grid** refers to the rows and columns automatically created by the browser when placing items in a grid layout.

These are rows and columns that are **not explicitly defined** using `grid-template-rows` or `grid-template-columns`.

The properties that control the columns and rows created implicitly by the browser are:

* `grid-auto-columns`
* `grid-auto-rows`

Implicit grid also refers to the additional rows and columns the browser automatically generates when you place an item outside the explicitly defined rows and columns.

## Example of an Implicit Grid

For instance, let's say you define only two explicit columns in a grid layout:

    <link rel="stylesheet" href="styles.css">

    <div class="grid-container">
      <div class="grid-item">Item 1</div>
      <div class="grid-item">Item 2</div>
      <div class="grid-item">Item 3</div>
      <div class="grid-item">Item 4</div>
      <div class="grid-item">Item 5</div>
      <div class="grid-item">Item 6</div>
    </div>

    .grid-container {
      display: grid;
      grid-template-columns: 100px 100px; /* Only 2 explicit columns */
    }

    .grid-item {
      background-color: burlywood;
      border: 1px solid orangered;
      padding: 0.5rem;
      margin: 0.5rem;
    }

Two items fill the first row using the two explicit columns:

* `Item 1` goes in the first column.
* `Item 2` goes in the second column.

The next items start a new row:

* `Item 3` goes in the first column of the second row.
* `Item 4` goes in the second column of the second row.
* `Item 5` goes in the first column of the third row.
* `Item 6` goes in the second column of the third row.

The additional rows are automatically created by the browser because we only explicitly defined two columns.

## Explicit Grid

As you've already seen, an **explicit grid** is the area of the grid that you intentionally set up.

That is, the rows and columns you explicitly define for a grid layout using:

* `grid-template-rows`
* `grid-template-columns`

For example:

    .grid-container {
      display: grid;
      grid-template-columns: 100px 100px;
      grid-template-rows: 100px 100px;
    }

Here, both the columns and rows are explicitly defined.

## Implicit vs Explicit Grid

| **Feature** | **Explicit Grid** | **Implicit Grid** |
|---|---|---|
| **Size control** | Fully customizable using `grid-template-rows` and `grid-template-columns`. | Controlled by `grid-auto-rows` and `grid-auto-columns`, or defaults to `auto`. |
| **Default behavior** | Does not change unless explicitly defined. | Automatically adapts to items placed outside the explicit grid. |
| **Complexity** | Requires more planning for layout structure. | Easier to implement for unstructured or variable content. |
| **Flexibility** | Provides a defined structure with specific rows and columns. | Flexible and adapts to dynamically placed content. |
| **Performance** | The predefined structure can make the layout more predictable. | May require additional browser computations when creating implicit tracks. |
| **Use case** | Useful when the grid structure is predictable and defined upfront. | Useful for dynamic layouts where content is unknown or changes frequently. |

## Summary

* **Explicit Grid** → Rows and columns you intentionally define.
* **Implicit Grid** → Rows and columns automatically created by the browser.
* `grid-template-rows` and `grid-template-columns` → Define the explicit grid.
* `grid-auto-rows` and `grid-auto-columns` → Control automatically generated tracks.
* Implicit grids are useful when the amount of content or its structure is not known in advance.
* Explicit grids are useful when you have a predictable layout that can be defined upfront.
