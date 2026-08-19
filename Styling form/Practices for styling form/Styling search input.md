# When Should You Use `appearance: none` to Deal With Issues Styling Search Inputs and Checkboxes?

The `appearance: none` property can be useful when you need more control over the default appearance of form controls such as:

- Checkboxes
- Radio buttons
- Search inputs
- Other form controls

Browsers apply default styles to many HTML elements. For input elements, these default styles can sometimes limit how much you can customize them with CSS.

Using:

`appearance: none;`

removes the browser's default appearance, allowing you to create your own design.

---

# Why Use `appearance: none`?

The main reason to use `appearance: none` is to gain greater control over the appearance of an interactive element.

For example, a browser normally provides its own appearance for a checkbox.

`<input type="checkbox">`

You can remove that default appearance with:

`.checkbox {
  appearance: none;
}`

You can then build your own checkbox using CSS.

---

# Creating a Custom Checkbox

Here is an example of a custom checkbox.

## HTML

`<link rel="stylesheet" href="styles.css">

<form>
  <label>
    <input class="checkbox" type="checkbox">
    Agree
  </label>
</form>`

## CSS

`.checkbox {
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
}`

---

# How the Custom Checkbox Works

The following rule removes the browser's default checkbox appearance:

`appearance: none;`

The dimensions are controlled manually:

`width: 18px;
height: 18px;`

The border creates the checkbox outline:

`border: 2px solid #ccc;`

The `:checked` pseudo-class changes the appearance when the checkbox is selected:

`.checkbox:checked {
  background-color: #4caf50;
  border-color: #4caf50;
}`

The `::after` pseudo-element creates the check mark:

`.checkbox:checked::after {
  content: "";
  position: absolute;
  left: 4px;
  top: 0;
  width: 5px;
  height: 10px;
  border: solid white;
  border-width: 0 2px 2px 0;
  transform: rotate(45deg);
}`

---

# Styling Search Inputs

Search inputs can also have browser-specific default controls.

For example, WebKit-based browsers may display:

- A search icon
- A cancel button

You can use `appearance: none` to remove the browser's default appearance and create your own design.

Example:

`input[type="search"] {
  appearance: none;
}`

This gives you more control over how the search input looks across different browsers.

---

# What Is WebKit?

**WebKit** is a browser engine used to display and render web pages.

Browsers such as Safari use WebKit to process HTML, CSS, and other web technologies.

Because browsers can apply different default styles to form controls, `appearance: none` can help create a more consistent custom design.

---

# Benefits of `appearance: none`

Using `appearance: none` can help you:

- Create custom checkboxes.
- Create custom radio buttons.
- Customize search inputs.
- Remove browser-specific default controls.
- Create more consistent designs across browsers.
- Make interactive elements easier to match with your website's design.
- Increase the size of touch targets on mobile devices.
- Improve color contrast when designing custom controls.

---

# Important Accessibility Considerations

Removing the browser's default appearance also means that you may remove useful visual indicators.

Interactive form controls normally provide important states such as:

- Focus
- Checked
- Unchecked
- Disabled
- Error
- Hover

When creating custom controls, make sure these states remain visible and understandable.

For example, the custom checkbox above provides a visible focus indicator:

`.checkbox:focus {
  outline: 2px solid #90caf9;
  outline-offset: 2px;
}`

This helps users identify which control currently has keyboard focus.

---

# When Should You Use `appearance: none`?

Use `appearance: none` when you need to replace or significantly customize a browser's default form-control appearance.

Good use cases include:

`input[type="search"] {
  appearance: none;
}`

`input[type="checkbox"] {
  appearance: none;
}`

`input[type="radio"] {
  appearance: none;
}`

However, you should not use it simply because you can. If the browser's default control already provides a good accessible experience, keeping it may be preferable.

---

# Key Points

- `appearance: none` removes the browser's default styling for supported form controls.
- It gives you greater control over the appearance of checkboxes, radio buttons, and search inputs.
- It can help create consistent designs across browsers.
- Custom controls must still provide clear interactive states.
- Do not remove focus indicators without replacing them with an accessible alternative.
- Make sure custom controls have sufficient color contrast.
- Make sure interactive controls are large enough to use comfortably, especially on touch devices.

---

# Summary

The `appearance: none` property is useful when browser-default form controls prevent you from achieving the design you want.

`.checkbox {
  appearance: none;
}`

Once the default appearance is removed, CSS can be used to create a custom control.

However, removing the default appearance also means you are responsible for recreating important visual states such as **focus**, **checked**, **hover**, and **error** states.

Use `appearance: none` when you need customization, but always preserve usability and accessibility.
