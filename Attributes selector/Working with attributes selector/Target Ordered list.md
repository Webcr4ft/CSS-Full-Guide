# How to Use the Attribute Selector to Target Ordered List Elements with the `type` Attribute

The **attribute selector** can be used to target ordered list (`<ol>`) elements based on their `type` attribute.

The `type` attribute controls the numbering style used by an ordered list.

---

# The `type` Attribute

The `type` attribute can be used on an `<ol>` element to specify how the list items should be numbered.

The main values are:

    type="1"
    ↓
    Numerical: 1, 2, 3, ...

    type="A"
    ↓
    Uppercase letters: A, B, C, ...

    type="a"
    ↓
    Lowercase letters: a, b, c, ...

    type="I"
    ↓
    Uppercase Roman numerals: I, II, III, ...

    type="i"
    ↓
    Lowercase Roman numerals: i, ii, iii, ...

---

# Basic Attribute Selector

The general syntax is:

    element[attribute="value"] {
      property: value;
    }

For an ordered list, you can use:

    ol[type="A"] {
      color: purple;
    }

This means:

    Select <ol> elements
    where type="A"

---

# Targeting Uppercase Alphabetical Lists

HTML:

    <link rel="stylesheet" href="styles.css">

    <ol type="A">
      <li>Item 1</li>
      <li>Item 2</li>
    </ol>

CSS:

    ol[type="A"] {
      color: purple;
      font-weight: bold;
    }

The selector:

    ol[type="A"]

targets ordered lists that use:

    type="A"

The list will use uppercase alphabetical numbering:

    A. Item 1
    B. Item 2

The CSS also makes the text:

- Purple.
- Bold.

---

# Targeting Lowercase Roman Numerals

You can also target ordered lists that use lowercase Roman numerals.

HTML:

    <link rel="stylesheet" href="styles.css">

    <ol type="i">
      <li>Item 1</li>
      <li>Item 2</li>
    </ol>

CSS:

    ol[type="i"] {
      color: green;
    }

The selector:

    ol[type="i"]

targets ordered lists where:

    type="i"

The numbering will use lowercase Roman numerals:

    i. Item 1
    ii. Item 2

The text will also be green.

---

# Targeting Other List Types

You can use the same technique for the other `type` values.

### Numerical

    ol[type="1"] {
      color: blue;
    }

Targets:

    <ol type="1">

Result:

    1. Item 1
    2. Item 2
    3. Item 3

---

### Uppercase Alphabetical

    ol[type="A"] {
      color: purple;
    }

Targets:

    <ol type="A">

Result:

    A. Item 1
    B. Item 2
    C. Item 3

---

### Lowercase Alphabetical

    ol[type="a"] {
      color: orange;
    }

Targets:

    <ol type="a">

Result:

    a. Item 1
    b. Item 2
    c. Item 3

---

### Uppercase Roman Numerals

    ol[type="I"] {
      color: red;
    }

Targets:

    <ol type="I">

Result:

    I. Item 1
    II. Item 2
    III. Item 3

---

### Lowercase Roman Numerals

    ol[type="i"] {
      color: green;
    }

Targets:

    <ol type="i">

Result:

    i. Item 1
    ii. Item 2
    iii. Item 3

---

# Why Use Attribute Selectors with Ordered Lists?

Attribute selectors allow you to style lists based on how they are structured.

For example:

    ol[type="A"] {
      font-weight: bold;
    }

Only ordered lists using uppercase alphabetical numbering will receive the style.

You don't need to add a separate class:

    <ol class="alphabetical">

Instead, CSS can directly check the existing `type` attribute.

---

# Multiple Ordered Lists Example

HTML:

    <ol type="1">
      <li>Numerical list</li>
      <li>Another item</li>
    </ol>

    <ol type="A">
      <li>Alphabetical list</li>
      <li>Another item</li>
    </ol>

    <ol type="i">
      <li>Roman numeral list</li>
      <li>Another item</li>
    </ol>

CSS:

    ol[type="1"] {
      color: blue;
    }

    ol[type="A"] {
      color: purple;
    }

    ol[type="i"] {
      color: green;
    }

Each ordered list receives a different style based on its `type` attribute.

---

# Attribute Selector Pattern

The important pattern to remember is:

    ol[type="value"]

For example:

    ol[type="A"]

means:

    Select <ol>
    where type equals "A"

And:

    ol[type="i"]

means:

    Select <ol>
    where type equals "i"

---

# Attribute Value Must Match

Attribute selectors can distinguish between uppercase and lowercase values.

For example:

    ol[type="A"]

and:

    ol[type="a"]

target different values.

`A` means uppercase alphabetical numbering.

`a` means lowercase alphabetical numbering.

Similarly:

    ol[type="I"]

and:

    ol[type="i"]

are different.

`I` means uppercase Roman numerals.

`i` means lowercase Roman numerals.

---

# Key Memory Trick

Remember:

    type="1"
    → Numbers

    type="A"
    → Uppercase letters

    type="a"
    → Lowercase letters

    type="I"
    → Uppercase Roman numerals

    type="i"
    → Lowercase Roman numerals

And the CSS pattern is:

    ol[type="value"]

Think:

    <ol>
      ↓
    Check its type attribute
      ↓
    Find the matching value
      ↓
    Apply the CSS

---

# Quick Summary

- The `type` attribute on an `<ol>` controls the numbering style.
- `type="1"` creates numerical numbering.
- `type="A"` creates uppercase alphabetical numbering.
- `type="a"` creates lowercase alphabetical numbering.
- `type="I"` creates uppercase Roman numeral numbering.
- `type="i"` creates lowercase Roman numeral numbering.
- Attribute selectors can target ordered lists based on their `type`.
- `ol[type="A"]` targets ordered lists with uppercase alphabetical numbering.
- `ol[type="i"]` targets ordered lists with lowercase Roman numeral numbering.
- The general syntax is:

    element[attribute="value"] {
      property: value;
    }

- Using attribute selectors gives you more control over styling lists based on their HTML attributes.
