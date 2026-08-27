# What Is the Difference Between `content-box` and `border-box`?

The `box-sizing` property can be set to either `content-box` or `border-box` to control how the **width and height** of elements are calculated.

This property can be set on the universal selector (`*`) to apply it to all the elements in the document:

    * {
      box-sizing: border-box;
    }

The value of the `box-sizing` property is `content-box` by default, but you can choose `border-box` if you need to.

We will explore `content-box` first and then we will go into `border-box`.

## Reviewing the CSS Box Model

To understand how the models work, you need to be familiar with the four core concepts from the CSS box model.

Let's review them quickly:

- **Content area:** The space occupied by the element's content.
- **Padding:** The space between the content area and the border.
- **Border:** The outline that surrounds the content area and the padding.
- **Margin:** The space outside the border that separates the element from other elements.

## How `content-box` Works

In the `content-box` model, the width and height that you set for an element determine the dimensions of the **content area**, but they don't include the padding, border, or margin.

Use `content-box` when you need precise control over the content area.

When you set `width` and `height`, you're only setting the size of the content itself.

### Calculating the Total Width

To find the total width of the element, you will need to add:

- The content width
- The left and right padding
- The left and right borders

The formula is:

    Total width = content width + left padding + right padding + left border + right border

### Calculating the Total Height

Likewise, the total height of an element can be found by adding:

- The content height
- The top and bottom padding
- The top and bottom borders

The formula is:

    Total height = content height + top padding + bottom padding + top border + bottom border

### Example of `content-box`

For example, here we have a CSS type selector for all the `div` elements.

    <link rel="stylesheet" href="styles.css">
    <div></div>

    div {
      width: 300px;
      height: 200px;
      padding: 20px;
      border: 4px solid black;
    }

In this case, if `content-box` is used, the content area will be **300px by 200px**.

The total rendered size includes the padding and borders.

For example:

    Total width = 300px + 40px + 8px
                = 348px

The total height is calculated in the same way:

    Total height = 200px + 40px + 8px
                 = 248px

So, the final rendered size is:

    Width: 348px
    Height: 248px

> **Remember:** With `content-box`, the specified `width` and `height` apply only to the content area.

## How `border-box` Works

Great! Now let's explore `border-box`.

It's different because the width and height you set **include the element's content, padding, and border**, but **not its margin**.

Use `border-box` when you want the element's **total size to stay fixed** even if padding or borders change.

That's often helpful in **responsive layouts**.

With `border-box`, padding and borders are included inside the element's specified size.

The width and height you set become the element's total dimensions:

    content + padding + border

Margins remain excluded.

For example:

    div {
      width: 300px;
      height: 200px;
      padding: 20px;
      border: 4px solid black;
      box-sizing: border-box;
    }

Here, the entire element remains:

    Width: 300px
    Height: 200px

The padding and border are included inside those dimensions.

The remaining space is used by the content area.

## Comparing `content-box` and `border-box`

In the following example, there are two `div` elements with the same dimensions but different `box-sizing` values.

Notice how this results in different total sizes when viewed in the browser:

    <link rel="stylesheet" href="styles.css">

    <div class="box" id="red-div"></div>
    <div class="box" id="blue-div"></div>

    .box {
      width: 300px;
      height: 200px;
      padding: 20px;
      border: 4px solid black;
      margin: 10px;
    }

    #red-div {
      box-sizing: content-box;
      background-color: red;
    }

    #blue-div {
      box-sizing: border-box;
      background-color: blue;
    }

You can see that they both have the same:

- `width`
- `height`
- `padding`
- `border`
- `margin`

The only differences are the colors and the value of the `box-sizing` property.

This small difference has a **very important impact** on the final dimensions.

### Quick Comparison

| Property | `content-box` | `border-box` |
| --- | --- | --- |
| `width` includes content | Yes | Yes |
| `width` includes padding | No | Yes |
| `width` includes border | No | Yes |
| `width` includes margin | No | No |
| `height` includes padding | No | Yes |
| `height` includes border | No | Yes |

## Choosing Between `content-box` and `border-box`

Choosing between `content-box` and `border-box` really depends on the specific needs of your project.

While `border-box` is becoming increasingly popular for its **simplicity and flexibility**, understanding both models is important for implementing effective CSS layouts.

> **Key takeaway:** `content-box` makes the specified width and height apply to the content area, while `border-box` makes the specified width and height include the content, padding, and border.
