# CSS Repository
# Input Pseudo-classes

## What Are Input Pseudo-classes?

The appearance and behavior of input elements play an important role when building web forms.

A form with responsive and interactive input fields improves the user experience by making it easier for users to understand what information is required and how the form is behaving.

CSS provides several *input pseudo-classes* that allow you to style form controls based on their current state without using JavaScript.

These pseudo-classes make forms more intuitive, accessible, and visually appealing.

---

# Common Input Pseudo-classes

* `:focus`
* `:hover`
* `:checked`
* `:required`
* `:valid`
* `:invalid`
* `:disabled`
* `:autofill`
* `:optional`
* `:in-range`
* `:out-of-range`

---

# `:focus`

## What It Does

The `:focus` pseudo-class targets an input element when the user selects it.

An input gains focus when:

* The user clicks inside it.
* The user navigates to it using the `Tab` key.
* It becomes the active field for typing.

This helps users easily identify where they are currently entering information.

---

## HTML

```html
<form>
  <input type="text">
</form>
```

---

## CSS

```css
input:focus {
  border: 2px solid crimson;
  outline: none;
}
```

---

## Result

When the input receives focus:

* The border changes to `crimson`.
* The default browser outline is removed.
* The active field becomes easier to identify.

---

# `:hover`

## What It Does

The `:hover` pseudo-class is triggered when the user places the mouse pointer over an input element.

It provides visual feedback before the user interacts with the field.

---

## HTML

```html
<form>
  <input type="text">
</form>
```

---

## CSS

```css
input:hover {
  background-color: orange;
}
```

---

## Result

When the mouse hovers over the input:

* The background changes to `orange`.
* Users know the field is ready for interaction.

---

# `:checked`

## What It Does

The `:checked` pseudo-class styles checkboxes and radio buttons after they have been selected.

It allows developers to create custom form controls that are more visually appealing than the browser defaults.

---

## HTML

```html
<form>
  <label>
    Agree
    <input class="checkbox" type="checkbox">
  </label>
</form>
```

---

## CSS

```css
.checkbox {
  appearance: none;
  width: 18px;
  height: 18px;
  border: 2px solid #ccc;
  border-radius: 4px;
  display: inline-block;
  position: relative;
  cursor: pointer;
  transition: all 0.25s ease;
  vertical-align: middle;
}

.checkbox:hover {
  border-color: #888;
}

.checkbox:checked {
  background-color: #4caf50;
  border-color: #4caf50;
}

.checkbox:checked::after {
  content: "";
  position: absolute;
  left: 4px;
  top: 0;
  width: 5px;
  height: 10px;
  border: solid white;
  border-width: 0 2px 2px 0;
  transform: rotate(45deg);
}

.checkbox:focus {
  outline: 2px solid #90caf9;
  outline-offset: 2px;
}
```

---

## Result

When the checkbox is unchecked:

* Gray border is displayed.

When hovered:

* Border becomes darker.

When checked:

* Background changes to green.
* A white checkmark appears.

When focused:

* A blue outline appears around the checkbox.

---

## Understanding `appearance: none`

```css
appearance: none;
```

### What It Does

The `appearance` property removes the browser's default styling from form controls.

Setting it to `none` allows you to completely customize:

* Checkboxes
* Radio buttons
* Select menus
* Other form controls

Without this property, browsers apply their own built-in styles.

---

# `:required`

## What It Does

The `:required` pseudo-class targets input elements that have the `required` attribute.

These fields must be completed before the form can be submitted.

---

## HTML

```html
<form action="#">
  <label for="name">Name:</label>
  <input
    type="text"
    id="name"
    name="name"
    required
  >

  <label for="email">Email:</label>
  <input
    type="email"
    id="email"
    name="email"
    required
  >

  <label for="phone">Phone Number:</label>
  <input
    type="tel"
    id="phone"
    name="phone"
  >

  <button type="submit">
    Submit
  </button>
</form>
```

---

## CSS

```css
input:required {
  border: 2px solid orange;
}
```

---

## Result

Only required fields receive:

* An orange border.

This helps users quickly identify fields that must be completed.

---

# `:valid`

## What It Does

The `:valid` pseudo-class styles input fields whose values satisfy the browser's validation rules.

For example:

* A correctly formatted email.
* A number within an allowed range.
* A required field that has been completed.

---

## HTML

```html
<form>
  <label for="email">
    Email:
  </label>

  <input
    type="email"
    id="email"
    name="email"
  >
</form>
```

---

## CSS

```css
input:valid {
  border-color: green;
}
```

---

## Result

When the input contains valid data:

* The border changes to `green`.

This gives users immediate confirmation that their input is acceptable.

---

# `:invalid`

## What It Does

The `:invalid` pseudo-class targets input fields that fail validation.

Examples include:

* An incorrectly formatted email.
* Missing required information.
* Numbers outside an allowed range.

---

## HTML

```html
<form>
  <label for="email">
    Email:
  </label>

  <input
    type="email"
    id="email"
    name="email"
  >
</form>
```

---

## CSS

```css
input:invalid {
  border-color: crimson;
}
```

---

## Result

When the input contains invalid data:

* The border changes to `crimson`.

This alerts users that corrections are needed.

---

# `:disabled`

## What It Does

The `:disabled` pseudo-class targets form controls that have the `disabled` attribute.

Disabled elements:

* Cannot be clicked.
* Cannot receive focus.
* Cannot be edited.
* Cannot be submitted with the form.

---

## HTML

```html
<form>
  <label for="name">
    Name:
  </label>

  <input
    class="text-input"
    type="text"
    id="name"
    name="name"
    disabled
  >
</form>
```

---

## CSS

```css
.text-input:disabled {
  background-color: lightgray;
  cursor: not-allowed;
}
```

---

## Result

The disabled input:

* Has a light gray background.
* Displays the `not-allowed` cursor.
* Cannot be interacted with.

---

# Understanding `cursor: not-allowed`

```css
cursor: not-allowed;
```

## What It Does

Changes the mouse cursor to a **circle with a diagonal slash**.

This indicates that:

* Clicking is not allowed.
* Editing is not allowed.
* The element is currently unavailable.

It provides a clear visual cue that the user cannot interact with the element.

---

# Other Input Pseudo-classes

## `:autofill`

### What It Does

Targets input fields that the browser automatically fills using saved information.

Example uses:

* Email
* Name
* Address
* Credit card information

Developers often use it to customize the browser's autofill appearance.

---

## `:optional`

### What It Does

Targets input fields that are **not required**.

Example:

```css
input:optional {
  background-color: white;
}
```

Only optional fields receive this style.

---

## `:in-range`

### What It Does

Targets input elements whose values fall within the allowed range.

Example:

```css
input:in-range {
  border-color: green;
}
```

Useful for number, date, and range inputs.

---

## `:out-of-range`

### What It Does

Targets input elements whose values fall outside the allowed range.

Example:

```css
input:out-of-range {
  border-color: red;
}
```

This immediately informs users that the entered value is outside the permitted limits.

---

# Why Use Input Pseudo-classes?

Input pseudo-classes improve forms by:

* Giving users immediate visual feedback.
* Highlighting active fields.
* Showing validation results.
* Identifying required inputs.
* Indicating disabled controls.
* Making custom checkboxes and radio buttons.
* Improving accessibility.
* Reducing the need for JavaScript.

---

# Key Points

* Input pseudo-classes style form elements based on their current state.
* They begin with a colon (`:`).
* They make forms more user-friendly and accessible.
* Common input pseudo-classes include:
  * `:focus`
  * `:hover`
  * `:checked`
  * `:required`
  * `:valid`
  * `:invalid`
  * `:disabled`
  * `:autofill`
  * `:optional`
  * `:in-range`
  * `:out-of-range`
* Most form interactions can be enhanced using CSS alone without JavaScript.
