# How Can You Position Items on the Grid Using the `grid-template-areas` Property?

The `grid-template-areas` property lets you design a visual grid layout by using named labels.

You then assign these labels to specific grid items using the `grid-area` property.

In other words, the named labels are also called **grid area names**.

---

## Basic Syntax of `grid-template-areas`

Here's the basic syntax:

    grid-template-areas:
      'header header header'
      'left-sidebar main right-sidebar'
      'footer footer footer';

There are several important things to understand about this syntax:

* Values like `header` and `main` are the names of the grid areas.
* Each space-separated value within a string corresponds to a **column**.
* Each string represents a **row** in the grid.

In this example:

    'header header header'
    'left-sidebar main right-sidebar'
    'footer footer footer'

There are:

* `3` rows.
* `3` columns.

So, the result is a **3 × 3 grid**.

---

## Grid Area Names

Each name represents a specific area of the grid.

For example:

    grid-template-areas:
      'header header header'
      'left-sidebar main right-sidebar'
      'footer footer footer';

The layout can be visualized as:

    ┌──────────────┬──────────────┬──────────────┐
    │    header    │    header    │    header    │
    ├──────────────┼──────────────┼──────────────┤
    │ left-sidebar │     main     │ right-sidebar│
    ├──────────────┼──────────────┼──────────────┤
    │    footer    │    footer    │    footer    │
    └──────────────┴──────────────┴──────────────┘

Notice that `header` appears three times in the first row.

This means the `header` area spans across all three columns.

The same applies to `footer`, which also spans across all three columns.

---

## Using `grid-area`

After defining the template, you use the `grid-area` property with the named labels as values.

The `grid-area` property connects a grid item to the named region you defined in `grid-template-areas`.

For example:

    .header {
      grid-area: header;
    }

This tells CSS that the `.header` element should be placed in the area named `header`.

Similarly:

    .main {
      grid-area: main;
    }

The `.main` element is placed in the area named `main`.

---

# The Holy Grail Layout

A popular way to demonstrate the capabilities of the `grid-template-areas` property is by creating the classic **Holy Grail layout**.

The Holy Grail layout is a common web design pattern that contains:

* A header.
* A footer.
* A left sidebar.
* A right sidebar.
* A main content area.

It allows the main content to take priority while the sidebars and other sections are arranged around it.

Many solutions exist for creating the Holy Grail layout, but using `grid-template-areas` together with `grid-area` provides a straightforward way to create it.

---

## HTML Example

Here's an example of the Holy Grail layout:

    <link rel="stylesheet" href="styles.css">

    <div class="grid-container">
      <div class="header">
        <h2>Header</h2>
      </div>

      <div class="sidebar-left">
        <h2>Left Sidebar</h2>
      </div>

      <div class="main">
        <h2>Main Content</h2>
      </div>

      <div class="sidebar-right">
        <h2>Right Sidebar</h2>
      </div>

      <div class="footer">
        <h2>Footer</h2>
      </div>
    </div>

---

## CSS Example

    .grid-container {
      display: grid;

      grid-template-areas:
        'header header header'
        'sidebar-left main sidebar-right'
        'footer footer footer';

      gap: 10px;
      background-color: #2196F3;
      padding: 10px;
    }

    .header {
      grid-area: header;
      background-color: rgba(255, 255, 255, 0.8);
      padding: 20px;
      text-align: center;
    }

    .sidebar-left {
      grid-area: sidebar-left;
      background-color: rgba(255, 255, 255, 0.8);
      padding: 20px;
      text-align: center;
    }

    .main {
      grid-area: main;
      background-color: rgba(255, 255, 255, 0.8);
      padding: 20px;
      text-align: center;
    }

    .sidebar-right {
      grid-area: sidebar-right;
      background-color: rgba(255, 255, 255, 0.8);
      padding: 20px;
      text-align: center;
    }

    .footer {
      grid-area: footer;
      background-color: rgba(255, 255, 255, 0.8);
      padding: 20px;
      text-align: center;
    }

---

## How the Layout Works

The grid container defines the overall layout:

    .grid-container {
      display: grid;

      grid-template-areas:
        'header header header'
        'sidebar-left main sidebar-right'
        'footer footer footer';
    }

The first row contains:

    'header header header'

So the `header` area spans all three columns.

The second row contains:

    'sidebar-left main sidebar-right'

This creates three separate areas:

* `sidebar-left` occupies the first column.
* `main` occupies the second column.
* `sidebar-right` occupies the third column.

The third row contains:

    'footer footer footer'

So the `footer` spans all three columns.

---

## Connecting Elements to Grid Areas

Each HTML element is connected to one of the named areas using `grid-area`.

For example:

    .header {
      grid-area: header;
    }

    .sidebar-left {
      grid-area: sidebar-left;
    }

    .main {
      grid-area: main;
    }

    .sidebar-right {
      grid-area: sidebar-right;
    }

    .footer {
      grid-area: footer;
    }

This allows CSS Grid to automatically place each element in the correct area.

---

# `grid-template-areas` vs `grid-area`

Both `grid-template-areas` and `grid-area` can be used independently of each other.

## `grid-template-areas`

The `grid-template-areas` property is specifically used to define a visual layout by mapping out named grid areas within the grid container.

Example:

    .grid-container {
      display: grid;

      grid-template-areas:
        'header header header'
        'sidebar-left main sidebar-right'
        'footer footer footer';
    }

It defines **where the named areas exist** in the grid.

---

## `grid-area`

The `grid-area` property is used to position individual grid items.

It can be used in two ways:

### 1. Using a Named Area

You can reference a named area created with `grid-template-areas`:

    .header {
      grid-area: header;
    }

### 2. Using Row and Column Positions

`grid-area` can also specify row and column positions directly.

For example:

    .item {
      grid-area: 1 / 1 / 2 / 3;
    }

This specifies the item's:

    row-start / column-start / row-end / column-end

So `grid-area` is not limited to named areas.

---

# Key Points

* `grid-template-areas` lets you create a visual grid layout using named areas.
* Each name represents a **grid area**.
* Each space-separated name represents a column.
* Each string represents a row.
* Repeating a name allows that area to span multiple grid cells.
* `grid-area` connects an individual grid item to a named area.
* `grid-template-areas` defines the overall visual layout.
* `grid-area` can reference a named area or specify row and column positions directly.
* The Holy Grail layout is a common example of using `grid-template-areas`.
* Using named grid areas can make complex layouts easier to read and understand.
