# What Is Progressive Disclosure?

## Introduction

**Progressive disclosure** is a UX design pattern that displays only the information users need for their current task while hiding additional or advanced content until it is requested. This helps reduce **cognitive load**, keeps interfaces clean, and makes applications easier to navigate.

> **Note:** Some of the interactive examples use CSS and JavaScript concepts you may not have learned yet. Focus on understanding the design concepts rather than the code itself.

---

# Basic Progressive Disclosure Example

A common implementation uses a button to reveal additional information only when the user requests it.

## HTML

```html
<link rel="stylesheet" href="styles.css">

<div class="progressive-disclosure">
  <button
    id="show-details-btn"
    aria-expanded="false"
    aria-controls="extra-content">
    Show More Details
  </button>

  <div
    id="extra-content"
    class="hidden"
    tabindex="-1">

    <p>
      Here are additional details that are revealed only
      when you want to see them. This keeps the interface
      clean and reduces cognitive load.
    </p>

  </div>
</div>

<script src="index.js"></script>
```

## CSS

```css
.progressive-disclosure {
  font-family: sans-serif;
  max-width: 400px;
  margin: 20px auto;
}

#show-details-btn {
  background-color: #007bff;
  color: white;
  border: none;
  padding: 10px 16px;
  border-radius: 5px;
  cursor: pointer;
}

.hidden {
  display: none;
}

#extra-content {
  margin-top: 15px;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}
```

## JavaScript

```javascript
const btn = document.getElementById("show-details-btn");
const content = document.getElementById("extra-content");

btn.addEventListener("click", () => {
  const isHidden = content.classList.toggle("hidden");

  btn.setAttribute("aria-expanded", !isHidden);

  if (!isHidden) {
    content.focus();
  }
});
```

---

# Real-World Examples

Progressive disclosure appears in many popular applications.

## Google Advanced Search

Google keeps its homepage simple because most searches are basic.

Instead of displaying dozens of search options immediately, advanced search settings are hidden until users intentionally open them.

This keeps the interface clean while still providing advanced functionality when needed.

---

## E-Commerce Product Pages

Online stores usually display:

- Product image
- Product name
- Price

Additional information such as:

- Specifications
- Features
- Warranty
- Shipping information

is revealed only after selecting **More Details**.

This prevents users from being overwhelmed with unnecessary information.

---

# Best Practices

## 1. Keep Important Information Visible

Never hide essential information.

Users should immediately see information needed to complete their task.

Hide only:

- Advanced settings
- Extra options
- Secondary information

Example:

An order summary should always display:

- Items purchased
- Total price

Optional features such as:

- Coupon codes
- Gift wrapping
- Shipping preferences

can remain hidden until requested.

---

## Example

A checkout page may always display the order summary while hiding advanced checkout options behind a single button.

---

## 2. Provide One Clear Access Point

Users should always know where to find additional information.

Good examples include:

- "More Info"
- "Show Details"
- "Advanced Options"

Avoid placing multiple buttons that reveal the same information because this creates confusion.

---

## Accessibility

Progressive disclosure should be accessible to every user.

Good accessibility practices include:

- Use `aria-expanded` to indicate whether content is open.
- Use `aria-controls` to associate the button with the content.
- Move keyboard focus into newly displayed content when appropriate.
- Update button text (for example, changing **More Info** to **Hide Info**) so users understand the current state.

---

# Benefits of Progressive Disclosure

Using progressive disclosure can:

- Reduce cognitive load.
- Keep interfaces clean.
- Prevent users from feeling overwhelmed.
- Help users focus on their current task.
- Improve overall usability.
- Make applications easier to learn.
- Create a better user experience.

---

# Summary

Progressive disclosure is a powerful design technique that simplifies interfaces by revealing information only when users need it.

When designing with progressive disclosure:

- Keep important information visible.
- Hide only optional or advanced content.
- Provide one consistent way to reveal additional information.
- Follow accessibility best practices using ARIA attributes and proper keyboard focus management.

When used correctly, progressive disclosure creates interfaces that are cleaner, easier to understand, and more user-friendly.
