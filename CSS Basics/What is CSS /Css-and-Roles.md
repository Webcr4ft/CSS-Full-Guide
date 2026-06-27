# What Is CSS, and What Is Its Role on the Web?

CSS, which stands for **Cascading Style Sheets**, is a crucial component of modern web development. It's a stylesheet language used to apply styles for HTML.

In simpler terms:

- **HTML** is the structure of a web page.
- **CSS** is what makes it look good.

---

## Example: Styling a Navbar

> **NOTE:** Don't worry about trying to understand the CSS code just yet. You will learn how all of this works in future lessons and workshops. This is just to give you an idea of what you can do with a little bit of CSS.

```html
<link rel="stylesheet" href="styles.css" />

<nav class="navbar">
  <ul class="nav-links">
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Services</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "Segoe UI", sans-serif;
  background-color: #f4f4f4;
}

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #333;
  padding: 1rem 2rem;
  color: white;
}

.navbar .logo {
  font-size: 1.5rem;
  font-weight: bold;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 1.5rem;
}

.nav-links a {
  color: white;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
}

.nav-links a:hover {
  color: #ff9800;
}
</style>
```

---

## The Primary Role of CSS

The primary role of CSS is to separate the content of a web page from its visual presentation.

This separation allows web developers to create more flexible and maintainable websites.

With CSS, you can control:

- Layout
- Colors
- Fonts
- Overall visual appearance

without altering the HTML structure.

---

## A Simple Analogy

Think of a website as a house.

- **HTML** is the foundation and framework.
- **CSS** is the paint, wallpaper, and decorations that make the house visually appealing and unique.

---

## How CSS Works

CSS works by selecting HTML elements and applying styles to them.

The next example shows an unstyled `button` element and a styled one.


---

# Example: Styling a Button

CSS styles can include properties like `color`, `font-size`, `padding`, `border-radius`, and many more.

By changing these properties, you can dramatically alter how a web page looks without changing its content.

The example below shows an unstyled `button` element and a styled one.

```html
<link rel="stylesheet" href="styles.css" />

<button class="regular-btn">Unstyled Button</button>
<button class="round-btn">Round Button</button>

<style>
.round-btn {
  font-size: 1rem;
  font-family: "Segoe UI", sans-serif;
  border: none;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.2s ease;
  background-color: #2ecc71;
  color: white;
  border-radius: 50px;
  padding: 0.6rem 1.6rem;
}

.round-btn:hover {
  background-color: #27ae60;
  transform: translateY(-2px);
}
</style>
```

---

# Responsive Design

One of the most powerful aspects of CSS is its ability to create **responsive designs**.

This means that with CSS, you can make your website look great on any device, whether it's:

- A desktop computer
- A tablet
- A smartphone

CSS allows you to adjust:

- Layouts
- Font sizes
- Spacing
- Other visual elements

based on the screen size of the device viewing the website.

Try enabling the interactive editor and adjust the size of the preview window to see how the layout adapts to the screen size.

```html
<link rel="stylesheet" href="styles.css" />

<header class="header">
  <h1>Welcome to My Responsive Site</h1>
  <p>This layout adapts to your screen size!</p>
</header>

<main class="content">
  <section class="box">Box 1</section>
  <section class="box">Box 2</section>
  <section class="box">Box 3</section>
</main>

<style>
body {
  margin: 0;
  font-family: "Segoe UI", sans-serif;
  background-color: #f9f9f9;
  color: #333;
}

.header {
  background-color: #4CAF50;
  color: white;
  padding: 2rem;
  text-align: center;
}

.content {
  display: flex;
  gap: 1rem;
  padding: 1rem;
  justify-content: center;
}

.box {
  flex: 1;
  min-width: 200px;
  background-color: #ddd;
  padding: 2rem;
  text-align: center;
  font-size: 1.2rem;
  border-radius: 8px;
  transition: background-color 0.3s;
}

.box:hover {
  background-color: #ccc;
}

/* Responsive: for tablets and below (≤ 768px) */
@media (max-width: 768px) {
  .content {
    flex-direction: column;
    align-items: center;
  }

  .box {
    width: 90%;
    font-size: 1.1rem;
  }
}

/* Responsive: for phones (≤ 480px) */
@media (max-width: 480px) {
  .header {
    padding: 1.5rem 1rem;
  }

  .header h1 {
    font-size: 1.5rem;
  }

  .header p {
    font-size: 1rem;
  }

  .box {
    font-size: 1rem;
    padding: 1.5rem;
  }
}
</style>
```


---

# CSS Cascading

Another important feature of CSS is its **cascading** nature, which is where the "**Cascading**" in its name comes from.

This means that styles can be:

- **Inherited**
- **Overridden**

This allows for a hierarchical structure of styling.

> **Note:** You will learn more about how the CSS cascade works in future lessons.

---

# External Stylesheets

CSS also supports the use of **external stylesheets**.

This means you can keep all your styling rules in a separate file, which can then be linked to multiple HTML pages.

For example:

```html
<link rel="stylesheet" href="styles.css">
```

Using external stylesheets provides several benefits:

- Keeps HTML clean and organized.
- Makes code easier to maintain.
- Allows one CSS file to style multiple web pages.
- Saves time by making changes in one place.

Instead of editing the styles on every individual page, you only need to update one CSS file, and every linked page will automatically reflect those changes.

---

# Why CSS Is Important

In the world of web development, CSS plays a vital role in creating:

- Visually appealing websites
- Responsive websites
- User-friendly websites
- Professional web designs

CSS allows developers to transform simple HTML documents into engaging web experiences that capture users' attention and improve their interaction with web content.

---

# Key Takeaways

- **CSS** stands for **Cascading Style Sheets**.
- CSS is responsible for the visual appearance of a website.
- HTML provides the structure, while CSS provides the design.
- CSS separates content from presentation.
- CSS can style colors, fonts, spacing, layouts, and much more.
- CSS makes websites responsive across different screen sizes.
- CSS styles can be inherited and overridden through the cascade.
- External stylesheets make websites easier to maintain.
- One CSS file can style multiple HTML pages.
