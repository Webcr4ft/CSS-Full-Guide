# CSS Repository

---

# What Are Some Best Practices for Styling Text Inputs?

As with all text elements, you need to ensure the styles you apply to text inputs are accessible.

This means:

* The font should be adequately sized.
* Text should have sufficient contrast with the background.
* Placeholder text should be readable.
* Inputs should have a clear focus indicator.
* Textareas should remain resizable.
* Error states should be clearly visible.

---

# 1. Use Accessible Text and Color Contrast

Text inputs should have readable font sizes and sufficient contrast between the text and background.

## HTML

```html
<link rel="stylesheet" href="styles.css">

<form class="accessible-form">
  <label for="username">Username</label>

  <input
    type="text"
    id="username"
    name="username"
    placeholder="Enter your username"
  >

  <button type="submit">Submit</button>
</form>
```

## CSS

```css
body {
  background-color: #f9fafb;
  color: #222;
  padding: 2rem;
}

.accessible-form {
  max-width: 320px;
  margin: 0 auto;
}

label {
  display: block;
  font-weight: 600;
  margin-bottom: 0.5rem;
}

input[type="text"] {
  width: 100%;
  padding: 0.6rem 0.8rem;
  font-size: 1rem;
  border: 2px solid #555;
  border-radius: 4px;
  background-color: #fff;
  color: #111;
}

input[type="text"]:focus {
  outline: 3px solid #1e90ff;
  border-color: #1e90ff;
}

button {
  margin-top: 1rem;
  padding: 0.6rem 1rem;
  font-size: 1rem;
  background-color: #1e90ff;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover,
button:focus {
  background-color: #187bcd;
}
```

---

# 2. Style Placeholder Text

The placeholder is also text, so it should be readable and have sufficient contrast.

## HTML

```html
<link rel="stylesheet" href="styles.css">

<form class="accessible-form">
  <label for="email">Email address</label>

  <input
    type="email"
    id="email"
    name="email"
    placeholder="you@example.com"
  >

  <button type="submit">Submit</button>
</form>
```

## CSS

```css
body {
  background-color: #f9fafb;
  color: #222;
  padding: 2rem;
}

.accessible-form {
  max-width: 320px;
  margin: 0 auto;
}

label {
  display: block;
  font-weight: 600;
  margin-bottom: 0.5rem;
}

input[type="email"] {
  width: 100%;
  padding: 0.6rem 0.8rem;
  font-size: 1rem;
  border: 2px solid #555;
  border-radius: 4px;
  background-color: #fff;
  color: #111;
}

input[type="email"]::placeholder {
  color: #555;
  opacity: 1;
  font-style: italic;
}

input[type="email"]:focus {
  outline: 3px solid #1e90ff;
  border-color: #1e90ff;
}

button {
  margin-top: 1rem;
  padding: 0.6rem 1rem;
  font-size: 1rem;
  background-color: #1e90ff;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover,
button:focus {
  background-color: #187bcd;
}
```

---

# 3. Allow Users to Resize Textareas

When using a `textarea`, do not unnecessarily remove the user's ability to resize it.

The input should also scale properly when the user zooms the page.

## HTML

```html
<form class="accessible-form">
  <label for="message">Your message</label>

  <textarea
    id="message"
    name="message"
    placeholder="Enter your message"
  ></textarea>

  <button type="submit">Send</button>
</form>
```

## CSS

```css
body {
  background-color: #f9fafb;
  color: #222;
  padding: 2rem;
  line-height: 1.5;
}

.accessible-form {
  max-width: 480px;
  margin: 0 auto;
}

label {
  display: block;
  font-weight: 600;
  margin-bottom: 0.5rem;
}

textarea {
  width: 100%;
  min-height: 120px;
  padding: 0.8rem;
  font-size: 1rem;
  border: 2px solid #555;
  border-radius: 4px;
  background-color: #fff;
  color: #111;
  resize: both;
  box-sizing: border-box;
}

textarea::placeholder {
  color: #555;
  opacity: 1;
}

textarea:focus {
  outline: 3px solid #1e90ff;
  border-color: #1e90ff;
}

button {
  margin-top: 1rem;
  padding: 0.6rem 1rem;
  font-size: 1rem;
  background-color: #1e90ff;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover,
button:focus {
  background-color: #187bcd;
}
```

---

# 4. Preserve a Clear Focus Indicator

Input elements are focusable.

When styling them, make sure you preserve a noticeable indicator when an input receives focus.

A visible border or focus ring helps users understand which input they are currently interacting with.

## CSS

```css
input[type="text"],
input[type="email"] {
  width: 100%;
  padding: 0.6rem 0.8rem;
  font-size: 1rem;
  border: 2px solid #666;
  border-radius: 4px;
  background-color: #fff;
  color: #111;
  transition: border-color 0.2s, box-shadow 0.2s;
}

input::placeholder {
  color: #555;
  opacity: 1;
}

input:focus {
  border-color: #1e90ff;
  box-shadow: 0 0 0 3px rgba(30, 144, 255, 0.4);
  outline: none;
}
```

---

# 5. Create a Clear Error State

Another important state to consider is the **error state**.

When the user's input fails validation, there should be a clear visual indication that something is wrong.

An error message should also explain what the user needs to fix.

## HTML

```html
<link rel="stylesheet" href="styles.css">

<form class="accessible-form">
  <label for="email">Email address</label>

  <input
    type="email"
    id="email"
    name="email"
    placeholder="you@example.com"
    aria-describedby="email-error"
    class="error"
  >

  <p id="email-error" class="error-message">
    Please enter a valid email address.
  </p>

  <button type="submit">Submit</button>
</form>

<script src="index.js"></script>
```

## CSS

```css
body {
  background-color: #f9fafb;
  color: #222;
  padding: 2rem;
  font-family: system-ui, sans-serif;
}

.accessible-form {
  max-width: 360px;
  margin: 0 auto;
}

label {
  display: block;
  font-weight: 600;
  margin-bottom: 0.5rem;
}

input[type="email"] {
  width: 100%;
  padding: 0.6rem 0.8rem;
  font-size: 1rem;
  border: 2px solid #666;
  border-radius: 4px;
  background-color: #fff;
  color: #111;
  transition: border-color 0.2s, box-shadow 0.2s;
}

input::placeholder {
  color: #555;
  opacity: 1;
}

input:focus {
  border-color: #1e90ff;
  box-shadow: 0 0 0 3px rgba(30, 144, 255, 0.4);
  outline: none;
}

input.error {
  border-color: #d93025;
  background-color: #fff5f5;
}

input.error:focus {
  border-color: #d93025;
  box-shadow: 0 0 0 3px rgba(217, 48, 37, 0.4);
}

.error-message {
  color: #d93025;
  font-size: 0.95rem;
  margin-top: 0.4rem;
}

button {
  margin-top: 1.5rem;
  padding: 0.6rem 1rem;
  font-size: 1rem;
  background-color: #1e90ff;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover,
button:focus {
  background-color: #187bcd;
}
```

---

# 6. Keep Focus and Error States Different

The focus state and error state should not look too similar.

For example:

* Use a blue border or focus ring for `:focus`.
* Use a different visual style for `.error`.
* Display an error message when validation fails.
* Do not rely on color alone to communicate an error.

This helps users understand whether an input is simply focused or contains invalid information.

---

# Best Practices Summary

* Use readable font sizes.
* Provide sufficient color contrast.
* Style placeholder text so it remains readable.
* Do not remove useful textarea resizing.
* Make inputs responsive when users zoom the page.
* Preserve a visible focus indicator.
* Create a clear error state.
* Provide an understandable error message.
* Use `aria-describedby` to associate an input with its error message.
* Make focus and error states visually distinct.

---

# Key Takeaways

* Accessibility should be considered whenever you style form inputs.
* Input text and placeholder text should be easy to read.
* Users should be able to resize `textarea` elements when appropriate.
* Inputs should scale correctly when the page is zoomed.
* Always provide a noticeable focus indicator.
* Error states should clearly communicate that something is wrong.
* Error messages should tell users how to correct the problem.
* JavaScript can be used to dynamically update validation and error messages.
