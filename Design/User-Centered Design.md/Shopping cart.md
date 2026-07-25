# What Are Best Practices for Designing Shopping Carts?

## Introduction

> **NOTE:** Some of the interactive examples might use CSS that you haven't learned yet. Don't worry about trying to understand all of the code. The goal of the examples is to show you previews of these design concepts so you better understand how they work. To see the previews, you will need to enable the interactive editor.

## Why Shopping Cart Design Matters

There are thousands of e-commerce websites on the internet, and the **shopping cart** is one of the most important parts of the online shopping experience.

A well-designed shopping cart can:

- Improve the user experience.
- Make purchasing easier.
- Increase sales.
- Encourage users to complete their purchases.

A poorly designed shopping cart can:

- Frustrate users.
- Cause abandoned carts.
- Lead to lost sales.

In this lesson, you'll learn some of the best practices for designing shopping carts.

---

# 1. Make the Shopping Cart Visible

The first design consideration is making sure the shopping cart is **visible to users at all times**.

Most websites place the shopping cart in the **upper-right corner** of the page because users have become familiar with this location.

A shopping cart should:

- Be easy to find.
- Be visible throughout the shopping experience.
- Display the number of items currently in the cart.
- Allow users to click the cart to view more details.

---

## Example: Shopping Cart Icon

### HTML

```html
<div class="shopping-cart">
  <button
    id="cart-btn"
    aria-label="Shopping cart"
  >
    <svg
      xmlns="http://www.w3.org/2000/svg"
      width="24"
      height="24"
      fill="none"
      stroke="currentColor"
      stroke-width="2"
      stroke-linecap="round"
      stroke-linejoin="round"
      viewBox="0 0 24 24"
      aria-hidden="true"
    >
      <circle
        cx="9"
        cy="21"
        r="1"
      ></circle>

      <circle
        cx="20"
        cy="21"
        r="1"
      ></circle>

      <path
        d="M1 1h4l2.68
        13.39a2 2 0 0 0
        2 1.61h9.72a2 2
        0 0 0 2-1.61L23
        6H6"
      ></path>
    </svg>

    <span id="item-count">
      2
    </span>
  </button>
</div>
```

### CSS

```css
.shopping-cart {
  position: fixed;
  top: 20px;
  right: 20px;
}

#cart-btn {
  background: none;
  border: none;
  position: relative;
  display: flex;
  align-items: center;
}

#item-count {
  background: red;
  color: white;
  border-radius: 50%;
  padding: 2px 6px;

  position: absolute;
  top: -6px;
  right: -6px;

  font-size: 13px;
}
```

---

## How This Example Works

The shopping cart remains visible in the upper-right corner of the page.

The red badge displays the number of items currently inside the cart.

Example:

```text
🛒 2
```

As users add products, the number should update automatically.

Instead of forcing users to search for their cart, they can immediately see:

- The cart's location.
- How many items have been added.
- Where to click to review their order.

---

## Why This Matters

Keeping the cart visible helps users:

- Track what they've added.
- Quickly review purchases.
- Continue shopping with confidence.

A hidden cart can confuse users and make purchasing more difficult.

---

# 2. Allow Users to Update Item Quantities

Another important consideration is providing a **clear way for users to update the quantity** of items in their shopping cart.

This can be done by placing a **quantity input field** next to each item in the cart.

Users should be able to increase or decrease the quantity without having to remove the item and add it again.

---

## Example: Shopping Cart with Quantity Controls

### HTML

```html
<div class="shopping-cart">
  <h2>Your Cart</h2>

  <ul class="cart-items">
    <li class="cart-item">
      <span class="item-name">
        T-Shirt
      </span>

      <input
        type="number"
        min="1"
        value="2"
        class="quantity-input"
        aria-label="Quantity for T-Shirt"
      >

      <button class="remove-btn">
        Remove
      </button>
    </li>

    <li class="cart-item">
      <span class="item-name">
        Hat
      </span>

      <input
        type="number"
        min="1"
        value="1"
        class="quantity-input"
        aria-label="Quantity for Hat"
      >

      <button class="remove-btn">
        Remove
      </button>
    </li>
  </ul>
</div>
```

### CSS

```css
.shopping-cart {
  max-width: 400px;
  margin: 20px auto;
  border: 1px solid #ccc;
  padding: 15px;
  border-radius: 6px;
}

.cart-items {
  list-style: none;
  padding: 0;
}

.cart-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 10px 0;
}

.quantity-input {
  width: 50px;
  text-align: center;
}

.remove-btn {
  background: #e74c3c;
  color: white;
  border: none;
  padding: 6px 12px;
  border-radius: 4px;
}
```

---

## How This Example Works

Each product includes:

- Product name.
- Quantity input.
- Remove button.

Instead of removing an item and adding it again, users can simply change the quantity.

Example:

```text
T-Shirt

Quantity: 2 → 3
```

This makes updating orders much faster and easier.

---

# 3. Provide a Remove Button

Every item in the shopping cart should include a **Remove** button.

Users should never struggle to remove an unwanted item.

A Remove button allows users to:

- Delete unwanted products.
- Correct shopping mistakes.
- Update their order quickly.

Making it difficult to remove products can frustrate users and may increase the number of abandoned carts.

---

## Why the Remove Button Matters

Imagine a customer accidentally adds the wrong item.

Instead of searching through several pages to remove it, they should simply click:

```text
Remove
```

The item should immediately disappear from the cart.

This creates a smoother shopping experience.

---

# 4. Use a Recognizable Shopping Cart Icon

Another important consideration is the **shopping cart icon itself**.

The icon should be immediately recognizable.

Common choices include:

- 🛒 Shopping cart
- 🛍 Shopping bag
- 🧺 Shopping basket

Avoid icons that are:

- Too abstract.
- Difficult to recognize.
- Unrelated to shopping.

Users should instantly understand:

> "This is where I can view my cart."

---

## Why Recognition Matters

Users should not have to guess what an icon means.

Using familiar icons reduces confusion and makes navigation easier.

Since the shopping cart icon has become a standard across e-commerce websites, using a familiar design helps users feel comfortable and confident.

---

# Best Practices So Far

- ✔ Keep the shopping cart visible.
- ✔ Display the number of items in the cart.
- ✔ Allow users to change item quantities.
- ✔ Include a Remove button for every item.
- ✔ Use a familiar shopping cart icon.

---

# 5. Display the Total Cost Clearly

When users want to review their shopping cart, they should be able to **quickly find the total cost** of all the items they are purchasing.

The total should be displayed **prominently**, so users don't have to search for it.

Displaying the total cost helps users:

- Understand how much they are spending.
- Decide whether to continue shopping.
- Make informed purchasing decisions.

---

## Example: Shopping Cart with Total Cost

### HTML

```html
<div class="shopping-cart">
  <button
    id="cart-btn"
    aria-label="Shopping cart"
  >
    <svg
      xmlns="http://www.w3.org/2000/svg"
      width="28"
      height="28"
      fill="none"
      stroke="currentColor"
      stroke-width="2"
      stroke-linecap="round"
      stroke-linejoin="round"
      viewBox="0 0 24 24"
      aria-hidden="true"
    >
      <circle cx="9" cy="21" r="1"></circle>
      <circle cx="20" cy="21" r="1"></circle>

      <path
        d="M1 1h4l2.68
        13.39a2 2 0 0 0
        2 1.61h9.72a2 2
        0 0 0 2-1.61L23
        6H6"
      ></path>
    </svg>

    <span id="item-count">
      3
    </span>
  </button>

  <div id="cart-details">
    <ul id="cart-items">
      <li>T-Shirt ×2 - $40.00</li>
      <li>Hat ×1 - $15.00</li>
    </ul>

    <div id="cart-total">
      Total:
      <strong>$55.00</strong>
    </div>
  </div>
</div>
```

### CSS

```css
#cart-total {
  font-size: 1.2rem;
  font-weight: 700;
  text-align: right;
  color: #111;
}
```

---

## How This Example Works

The shopping cart displays:

- Every item.
- The quantity of each item.
- The price of each item.
- The total cost.

Example:

```text
T-Shirt ×2 — $40.00
Hat ×1 — $15.00

Total: $55.00
```

Users can immediately see the total amount they will pay without searching through the cart.

---

# 6. Provide a Clear Checkout Button (Call-to-Action)

The final consideration is providing a **clear Call-to-Action (CTA)** button that allows users to proceed to checkout.

The Checkout button should be:

- Easy to find.
- Large enough to notice.
- Visually prominent.
- Clearly labeled.

Example:

```text
Proceed to Checkout
```

---

## Why the CTA Matters

The Checkout button is the most important action in the shopping cart.

Users should instantly know what to do next.

Avoid filling the shopping cart with too many buttons because multiple competing actions can confuse users.

Instead, make the Checkout button the most prominent element.

---

## Use Your Brand's Primary Color

The Checkout button should use your website's **primary brand color**.

This helps it stand out from the rest of the interface and naturally draws the user's attention.

Example CSS:

```css
:root {
  --primary-color: #007bff;
}

#checkout-btn {
  width: 100%;
  background: var(--primary-color);
  color: white;
  border: none;
  padding: 12px 0;
  font-size: 1.1rem;
  font-weight: bold;
  border-radius: 6px;
  cursor: pointer;
}
```

---

# Best Practices Summary

A well-designed shopping cart should:

- ✔ Be visible at all times.
- ✔ Be placed in the upper-right corner of the page.
- ✔ Display the number of items in the cart.
- ✔ Allow users to update item quantities.
- ✔ Include a Remove button for each item.
- ✔ Use a familiar shopping cart icon.
- ✔ Display the total cost prominently.
- ✔ Include a clear and highly visible Checkout button.
- ✔ Use the brand's primary color for the main Call-to-Action button.

---

# Key Takeaway

The shopping cart is one of the most important parts of an e-commerce website. A clear, user-friendly shopping cart makes it easier for customers to review their purchases, update their orders, and complete the checkout process. Following these best practices can improve the overall shopping experience and help reduce abandoned carts while increasing completed purchases.

---
