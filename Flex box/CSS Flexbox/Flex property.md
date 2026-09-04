# Common CSS Flex Properties

Flex properties control how elements behave inside a **flex container**.

The most common properties are:

* `flex-wrap`
* `flex-flow`
* `justify-content`
* `align-items`
* `align-self`

---

## 1. `flex-wrap`

The `flex-wrap` property controls whether flex items should move onto a new line when there isn't enough space.

### Values

* `nowrap` → Items stay on one line. **Default.**
* `wrap` → Items move to a new line when necessary.
* `wrap-reverse` → Items wrap onto new lines in the reverse direction.

### Example

```css
main {
  display: flex;
  flex-wrap: wrap;
}
```

If the container is too small to fit all the items, `wrap` allows the extra items to move to another row.

### Easy way to remember

> `flex-wrap` = **Should the items wrap to another line?**

---

# 2. `flex-flow`

`flex-flow` is a **shorthand** for:

* `flex-direction`
* `flex-wrap`

Instead of writing:

```css
main {
  flex-direction: column;
  flex-wrap: wrap-reverse;
}
```

You can write:

```css
main {
  flex-flow: column wrap-reverse;
}
```

### Easy way to remember

> `flex-flow` = **direction + wrapping**

---

# 3. `justify-content`

`justify-content` controls how flex items are positioned along the **main axis**.

Remember:

* `row` → main axis is horizontal
* `column` → main axis is vertical

### `flex-start`

Moves items to the **start** of the main axis.

```css
main {
  display: flex;
  justify-content: flex-start;
}
```

### `flex-end`

Moves items to the **end** of the main axis.

```css
main {
  display: flex;
  justify-content: flex-end;
}
```

### `center`

Centers the items along the main axis.

```css
main {
  display: flex;
  justify-content: center;
}
```

### `space-between`

Places the first item at the start and the last item at the end.

The remaining space is placed **between** the items.

```css
main {
  display: flex;
  justify-content: space-between;
}
```

Think:

```text
| ITEM    ITEM    ITEM |
```

### `space-around`

Adds space around each item.

The space at the edges is smaller than the space between items.

```css
main {
  display: flex;
  justify-content: space-around;
}
```

### `space-evenly`

Creates **equal space everywhere**.

```css
main {
  display: flex;
  justify-content: space-evenly;
}
```

Think:

```text
|  ITEM  |  ITEM  |  ITEM  |
```

### Easy way to remember

> `justify-content` = **position items on the main axis**

---

# 4. `align-items`

`align-items` controls how **all flex items** are positioned along the **cross axis**.

The cross axis is perpendicular to the main axis.

For the default `flex-direction: row`:

* Main axis → horizontal
* Cross axis → vertical

### `center`

Centers all items along the cross axis.

```css
main {
  display: flex;
  height: 300px;
  align-items: center;
}
```

### `flex-start`

Moves items to the start of the cross axis.

```css
main {
  display: flex;
  align-items: flex-start;
}
```

### `flex-end`

Moves items to the end of the cross axis.

```css
main {
  display: flex;
  align-items: flex-end;
}
```

### `stretch`

Stretches items across the cross axis.

```css
main {
  display: flex;
  align-items: stretch;
}
```

`stretch` only affects items whose size on the cross axis is `auto`.

For example, with `flex-direction: row`, an item with no fixed `height` can stretch vertically.

### Easy way to remember

> `align-items` = **align all items on the cross axis**

---

# 5. `align-self`

`align-self` works like `align-items`, but it affects **one specific flex item**.

For example:

```css
main {
  display: flex;
  align-items: flex-start;
}

#third-div {
  align-self: center;
}
```

The other items remain at the start, while the third item moves to the center.

### Common values

```css
align-self: flex-start;
align-self: center;
align-self: flex-end;
align-self: stretch;
```

### Easy way to remember

> `align-items` = **all items**  
> `align-self` = **one item**

---

# Quick Review

| Property | What it does |
|---|---|
| `flex-wrap` | Controls whether items wrap |
| `flex-flow` | Shorthand for direction + wrap |
| `justify-content` | Positions items on the main axis |
| `align-items` | Positions all items on the cross axis |
| `align-self` | Positions one item on the cross axis |

---

# The Most Important Difference

```text
MAIN AXIS
    ↓
justify-content
```

```text
CROSS AXIS
    ↓
align-items
align-self
```

### Think of it like this:

* `justify-content` → **Where do the items go along the main axis?**
* `align-items` → **Where do ALL items go along the cross axis?**
* `align-self` → **Where does ONE item go along the cross axis?**
* `flex-wrap` → **Should items move to another line?**
* `flex-flow` → **Direction + wrapping**

# Key Things to Remember

* `flex-wrap` controls wrapping.
* `flex-flow` combines `flex-direction` and `flex-wrap`.
* `justify-content` works on the **main axis**.
* `align-items` works on the **cross axis** for all items.
* `align-self` changes the cross-axis alignment of **one item**.
* The main axis depends on `flex-direction`.
