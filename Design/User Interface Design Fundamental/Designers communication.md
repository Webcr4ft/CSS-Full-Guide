# What Are Common Design Terms to Help You Communicate with Designers?

> **NOTE**
>
> Some of the interactive examples in this lesson use CSS properties and techniques that you may not have learned yet. Don't worry if some of the code looks unfamiliar. The purpose of these examples is **not** to teach you every CSS property right now. Instead, they are meant to visually demonstrate important design concepts so you can understand how professional designers think. As you continue learning CSS, you'll naturally understand the code behind these examples.

---

# Why Should Developers Learn Design Terminology?

Many beginners think that web designers and web developers have completely separate jobs. While their responsibilities are different, they work very closely together on almost every project.

- A **designer** focuses on how a website or application should look and feel.
- A **developer** takes the designer's ideas and turns them into a functional website using HTML, CSS, and JavaScript.

Because these two roles work together so often, they need a **shared vocabulary**. If a designer says:

> "The layout needs improvement."

or

> "The hierarchy isn't clear."

or

> "Add more white space."

A developer who understands these terms will immediately know what the designer means. A developer who doesn't understand these terms may become confused or misunderstand the request.

Learning common design terminology helps you:

- Communicate better with designers.
- Understand design documents and mockups.
- Build websites that look more professional.
- Create interfaces that are easier for users to understand.
- Participate more actively during planning and design discussions.

Even if you never become a professional designer, understanding these concepts will make you a much better front-end developer.

---

# Design Term 1: Layout

The first important design term is **Layout**.

## What is Layout?

**Layout** is the way visual elements are arranged on a webpage or application screen.

These visual elements include:

- Headings
- Paragraphs
- Images
- Buttons
- Navigation bars
- Cards
- Icons
- Videos
- Forms
- White space

Think of a layout as the **blueprint** of a building.

Before builders begin constructing a house, an architect decides:

- Where the bedrooms should go.
- Where the kitchen should be.
- Where the living room belongs.
- Where the doors and windows should be placed.

Without a blueprint, everything would be placed randomly.

Website design works exactly the same way.

Before a website is built, designers decide:

- Where the logo should appear.
- Where the navigation menu should be.
- Where the main heading belongs.
- Where product images should appear.
- Where buttons should be placed.
- How much spacing should exist between different sections.

All of these decisions together form the website's **layout**.

---

## Why is Layout Important?

A good layout helps users:

- Find information quickly.
- Understand what is most important.
- Navigate the website easily.
- Enjoy using the website.

A poor layout can:

- Confuse visitors.
- Hide important information.
- Make the page look messy.
- Reduce the overall user experience.

Good layout is one of the foundations of good web design.

---

## Things Designers Consider When Creating a Layout

Designers don't randomly place elements on a page. Every decision has a purpose.

### 1. Placement

They decide where every element should appear.

For example:

- Should the navigation bar be at the top?
- Should the sidebar be on the left?
- Should the footer stay at the bottom?
- Should the call-to-action button appear immediately after the heading?

Every placement decision affects how users interact with the page.

---

### 2. Size

Important elements are usually larger than less important elements.

For example:

A page title is usually much larger than the paragraph below it.

Large elements naturally attract more attention.

---

### 3. Hierarchy

Designers decide which information users should notice first.

For example:

1. Large headline
2. Smaller description
3. Button

This naturally guides the user's eyes from the most important information to the least important information.

We'll study **Hierarchy** in much more detail later.

---

### 4. White Space

Designers also think about the empty space between elements.

Too little spacing makes a page feel crowded.

Too much spacing can make a page feel empty.

Finding the right balance creates a cleaner and more readable design.

---

# Layout Example

The lesson demonstrates layout using a simple online shopping website called **ShopMate**.

The website contains:

- A header
- A navigation menu
- A hero section
- Featured product cards
- A footer

Together, these sections create the overall layout of the webpage.

## HTML Example

```html
<link rel="stylesheet" href="styles.css">

<header>
  <div class="container">
    <h1>ShopMate</h1>

    <nav>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Shop</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Cart (2)</a></li>
      </ul>
    </nav>
  </div>
</header>

<main>

<section class="hero">
<h2>Fall Collection 2025</h2>
<p>Discover the latest trends</p>
<a href="#" class="btn">Shop Now</a>
</section>

<section class="products container">

<h3>Featured Products</h3>

<div class="product-grid">

<div class="product-card">
<img src="https://placehold.co/300x200" alt="Product 1">
<h4>Product 1</h4>
<p>$49.99</p>
<button>Add to Cart</button>
</div>

<div class="product-card">
<img src="https://placehold.co/300x200" alt="Product 2">
<h4>Product 2</h4>
<p>$59.99</p>
<button>Add to Cart</button>
</div>

<div class="product-card">
<img src="https://placehold.co/300x200" alt="Product 3">
<h4>Product 3</h4>
<p>$39.99</p>
<button>Add to Cart</button>
</div>

<div class="product-card">
<img src="https://placehold.co/300x200" alt="Product 4">
<h4>Product 4</h4>
<p>$29.99</p>
<button>Add to Cart</button>
</div>

</div>

</section>

</main>

<footer>
<div class="container">
<p>&copy; 2025 ShopMate. All rights reserved.</p>
</div>
</footer>
```

---

## Understanding the HTML

Let's briefly examine what each major section does.

### `<header>`

The `<header>` element contains introductory content for the webpage.

It commonly contains:

- Website logo
- Website name
- Navigation menu

---

### `<nav>`

The `<nav>` element represents the website's navigation.

Users use this section to move between pages.

---

### `<main>`

The `<main>` element contains the primary content of the webpage.

Search engines and assistive technologies recognize this as the most important content area.

---

### Hero Section

The hero section is usually the first large section visitors see.

It often contains:

- A large heading
- A short description
- A button encouraging users to perform an action

This button is commonly called a **Call-to-Action (CTA)**.

Examples include:

- Shop Now
- Learn More
- Get Started
- Sign Up

---

### Product Grid

Instead of stacking products underneath each other, they're grouped inside a **product grid**.

This creates a cleaner layout and allows multiple products to appear side-by-side on larger screens.

Each product is displayed inside its own **product card**, making the page easier to scan and understand.

---

In the next part, we'll break down the CSS used to build this layout and then move on to the next important design concept: **Alignment**.


# Understanding the CSS Behind the Layout

Now that we've looked at the HTML structure of the ShopMate website, let's examine the CSS that controls its layout.

Remember, **HTML creates the structure**, while **CSS controls the appearance and arrangement** of that structure.

---

## CSS Example

```css
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  line-height: 1.6;
  background: #f9f9f9;
  color: #333;
}

.container {
  width: 90%;
  max-width: 1200px;
  margin: auto;
}

header .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

header {
  background: #fff;
  border-bottom: 1px solid #ddd;
  padding: 1rem 0;
}

header h1 {
  color: #2c3e50;
}

nav ul {
  list-style: none;
  display: flex;
  gap: 1.5rem;
  justify-content: flex-end;
}

nav a {
  text-decoration: none;
  color: #2c3e50;
  font-weight: 500;
}

.hero {
  background-color: lightgrey;
  text-align: center;
  padding: 4rem 1rem;
  margin-bottom: 2rem;
}

.hero h2 {
  font-size: 2.5rem;
  margin-bottom: 0.5rem;
}

.hero .btn {
  display: inline-block;
  margin-top: 1rem;
  padding: 0.75rem 1.5rem;
  background: #2c3e50;
  color: white;
  text-decoration: none;
  border-radius: 4px;
}

.products h3 {
  margin-bottom: 1rem;
  font-size: 1.8rem;
  color: #2c3e50;
}

.product-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 2rem;
}

.product-card {
  background: white;
  padding: 1rem;
  border-radius: 8px;
  text-align: center;
  box-shadow: 0 2px 6px rgba(0,0,0,0.1);
}

.product-card img {
  max-width: 100%;
  border-radius: 6px;
  margin-bottom: 1rem;
}

.product-card h4 {
  margin: 0.5rem 0;
}

.product-card button {
  background: #27ae60;
  color: white;
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
  border-radius: 4px;
}

.product-card button:hover {
  background: #219150;
}

footer {
  background: #2c3e50;
  color: white;
  text-align: center;
  padding: 1rem 0;
  margin-top: 2rem;
}
```

---

# Breaking Down the CSS

Let's understand what each important section does.

## Universal Selector (`*`)

```css
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

The universal selector (`*`) selects **every element** on the page.

### `box-sizing: border-box;`

Normally, an element's width does **not** include its padding and border.

Setting:

```css
box-sizing: border-box;
```

changes this behavior so that:

- Width includes padding.
- Width includes border.

This makes sizing elements much easier and is considered a best practice by many developers.

---

### `margin: 0;`

Browsers automatically add margins to many elements like:

- `<h1>`
- `<p>`
- `<ul>`

This line removes all default margins so the developer has complete control over spacing.

---

### `padding: 0;`

Browsers also add default padding to certain elements.

Resetting it ensures every browser starts with the same spacing.

---

# Styling the `<body>`

```css
body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  line-height: 1.6;
  background: #f9f9f9;
  color: #333;
}
```

### `font-family`

Determines which fonts should be used.

The browser tries them from left to right.

If one font isn't available, it moves to the next.

---

### `line-height`

Controls the vertical spacing between lines of text.

Larger values make text easier to read.

---

### `background`

Sets the page's background color.

---

### `color`

Sets the default text color for the page.

---

# The `.container` Class

```css
.container {
    width: 90%;
    max-width: 1200px;
    margin: auto;
}
```

The `.container` class is one of the most common classes in web development.

Its purpose is to keep content centered while preventing it from becoming too wide.

### `width: 90%`

The container occupies 90% of the available screen width.

---

### `max-width: 1200px`

Even on very large monitors, the container will never become wider than 1200 pixels.

This keeps long lines of text readable.

---

### `margin: auto`

Centers the container horizontally.

---

# Creating the Header Layout

```css
header .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
```

This is where Flexbox is introduced.

### `display: flex`

Places child elements in a flexible row.

Instead of appearing one below another, they sit beside each other.

---

### `justify-content: space-between`

Pushes the first item to the far left and the last item to the far right.

Here:

- ShopMate stays on the left.
- Navigation stays on the right.

---

### `align-items: center`

Centers everything vertically.

The logo and navigation line up perfectly.

---

# Styling the Header

```css
header {
    background: white;
    border-bottom: 1px solid #ddd;
    padding: 1rem 0;
}
```

This gives the header:

- White background
- Thin bottom border
- Vertical spacing

making it look clean and separated from the rest of the page.

---

# Navigation Styling

```css
nav ul {
    list-style: none;
    display: flex;
    gap: 1.5rem;
}
```

### `list-style: none`

Removes the bullet points from the unordered list.

---

### `display: flex`

Places menu items side by side.

---

### `gap`

Adds equal spacing between each navigation link.

This is cleaner than adding margins individually.

---

# Design Term 2: Alignment

Now that you've seen how CSS arranges elements, let's introduce another important design concept.

## What is Alignment?

**Alignment** refers to how elements are positioned relative to one another.

Instead of randomly placing text and images, designers align elements along:

- The left edge
- The center
- The right edge
- Imaginary vertical lines
- Imaginary horizontal lines

Proper alignment makes a design feel:

- Organized
- Professional
- Easy to read
- Visually balanced

Poor alignment makes a design appear messy, confusing, and unprofessional.

Alignment helps users naturally follow information across the page.

In the next part, we'll look at the Alignment example from the lesson, explain its HTML and CSS, and then continue with **Composition** and **Balance**.


# Design Term 2: Alignment

In the previous part, we introduced the concept of **Alignment**. Now let's explore it in greater detail using the example from the lesson.

---

# What is Alignment?

**Alignment** is the way elements are positioned in relation to one another.

In other words, it determines how text, images, buttons, and other elements line up on a webpage.

Good alignment creates order and consistency.

Poor alignment makes a design feel messy and difficult to read.

Imagine opening two websites.

Website A has:

- Text starting at different positions.
- Images placed randomly.
- Buttons that don't line up.
- Uneven spacing.

Website B has:

- Headings perfectly aligned.
- Images lined up evenly.
- Buttons placed consistently.
- Equal spacing between sections.

Most people will naturally find Website B more attractive and easier to use.

That's the power of alignment.

---

# Why is Alignment Important?

Alignment helps:

- Organize information.
- Create visual structure.
- Improve readability.
- Make a website look professional.
- Guide users through the content naturally.

Without alignment, users may struggle to understand where to look next.

---

# Types of Alignment

The lesson demonstrates three common types of alignment.

## 1. Left Alignment

Everything begins from the left edge.

Example:

```
Heading

This paragraph begins from
the same starting point.
```

This is the most common alignment for websites because people who read left-to-right languages naturally begin reading from the left.

Most articles, books, blogs, and documentation use left alignment.

---

## 2. Center Alignment

Everything is centered.

Example:

```
        Heading

    This paragraph
    is centered.
```

Center alignment is commonly used for:

- Hero sections
- Landing pages
- Titles
- Quotes
- Certificates
- Welcome messages

Because everything is centered, it naturally draws attention.

However, large paragraphs should usually **not** be center-aligned because they become harder to read.

---

## 3. Right Alignment

Everything begins from the right side.

Example:

```
          Heading

      This text starts
      from the right.
```

Right alignment is used less frequently.

It may be useful for:

- Certain artistic designs.
- Languages written from right to left.
- Decorative layouts.
- Special emphasis.

Using right alignment for large amounts of text in English usually makes reading more difficult.

---

# HTML Example

```html
<link rel="stylesheet" href="styles.css">

<div class="container">

<section class="alignment left">
<h2>Left-Aligned</h2>

<p>
This content is aligned to the left.
Left alignment is most common for body text because it follows
natural reading flow in left-to-right languages.
</p>

</section>

<section class="alignment center">

<h2>Center-Aligned</h2>

<p>
This content is centered.
Center alignment is useful for titles,
headings, and content that needs to become
the focal point.
</p>

</section>

<section class="alignment right">

<h2>Right-Aligned</h2>

<p>
This content is aligned to the right.
Right alignment can be used for stylistic emphasis
or when aligning content against the right edge
of a container.
</p>

</section>

</div>
```

---

# Understanding the HTML

The HTML creates three sections.

Each section demonstrates one alignment style.

Notice that every section has two classes.

Example:

```html
<section class="alignment left">
```

This means the section belongs to:

- The `.alignment` class.
- The `.left` class.

The browser combines the styles from both classes.

The same idea applies to:

```html
<section class="alignment center">
```

and

```html
<section class="alignment right">
```

This is a common technique in CSS because it allows classes to be reused.

---

# CSS Example

```css
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  line-height: 1.6;
  background: #f4f4f4;
  color: #333;
  padding: 2rem;
}

.container {
  max-width: 800px;
  margin: 0 auto;
}

.alignment {
  background: #fff;
  border-left: 4px solid #3498db;
  padding: 1.5rem;
  margin-bottom: 2rem;
  box-shadow: 0 2px 6px rgba(0,0,0,0.05);
  transition: all 0.3s ease;
}

.alignment:hover {
  transform: scale(1.02);
}

.alignment h2 {
  margin-bottom: 0.5rem;
  color: #3498db;
}

.left {
  text-align: left;
}

.center {
  text-align: center;
}

.right {
  text-align: right;
}
```

---

# Understanding the CSS

## `.container`

```css
.container {
    max-width: 800px;
    margin: 0 auto;
}
```

The container keeps everything centered while preventing the content from becoming too wide.

This makes reading much more comfortable.

---

## `.alignment`

```css
.alignment {
    background: white;
}
```

Adds a white background behind every example.

This separates each example from the gray page background.

---

```css
border-left: 4px solid #3498db;
```

Creates a blue line along the left side.

This acts as a visual accent that makes each section stand out.

---

```css
padding: 1.5rem;
```

Creates empty space inside each section.

Without padding, the text would touch the edges.

---

```css
margin-bottom: 2rem;
```

Creates space below each example.

Without it, every section would touch the next one.

---

```css
box-shadow: 0 2px 6px rgba(0,0,0,0.05);
```

Adds a subtle shadow.

The sections appear slightly raised from the page, giving them a modern card-like appearance.

---

```css
transition: all 0.3s ease;
```

Allows property changes to happen smoothly.

Without a transition, hover effects happen instantly.

With a transition, they animate smoothly.

---

## Hover Effect

```css
.alignment:hover {
    transform: scale(1.02);
}
```

When the mouse moves over a section:

- It becomes slightly larger.
- The animation feels smooth because of the transition property.

Small hover animations make websites feel more interactive.

---

## Changing Text Alignment

```css
.left {
    text-align: left;
}
```

Aligns all text to the left.

---

```css
.center {
    text-align: center;
}
```

Centers all text.

---

```css
.right {
    text-align: right;
}
```

Aligns all text to the right.

Notice that only **one CSS property** changes between these three classes.

That property is:

```css
text-align
```

Changing this single property completely changes how the content is presented.

---

# Design Term 3: Composition

Now that we understand alignment, let's move on to another important design concept called **Composition**.

Many beginners confuse **Layout** and **Composition** because both involve arranging elements.

However, they are **not exactly the same thing**.

- **Layout** focuses on *where* elements are placed.
- **Composition** focuses on *how those elements work together visually and artistically*.

In the next part, we'll explore **Composition** and **Balance**, two concepts that designers use to create visually pleasing and harmonious designs.



Part 3

# Design Term 2: Alignment

In the previous part, we introduced the concept of **Alignment**. Now let's explore it in greater detail using the example from the lesson.

---

# What is Alignment?

**Alignment** is the way elements are positioned in relation to one another.

In other words, it determines how text, images, buttons, and other elements line up on a webpage.

Good alignment creates order and consistency.

Poor alignment makes a design feel messy and difficult to read.

Imagine opening two websites.

Website A has:

- Text starting at different positions.
- Images placed randomly.
- Buttons that don't line up.
- Uneven spacing.

Website B has:

- Headings perfectly aligned.
- Images lined up evenly.
- Buttons placed consistently.
- Equal spacing between sections.

Most people will naturally find Website B more attractive and easier to use.

That's the power of alignment.

---

# Why is Alignment Important?

Alignment helps:

- Organize information.
- Create visual structure.
- Improve readability.
- Make a website look professional.
- Guide users through the content naturally.

Without alignment, users may struggle to understand where to look next.

---

# Types of Alignment

The lesson demonstrates three common types of alignment.

## 1. Left Alignment

Everything begins from the left edge.

Example:

```
Heading

This paragraph begins from
the same starting point.
```

This is the most common alignment for websites because people who read left-to-right languages naturally begin reading from the left.

Most articles, books, blogs, and documentation use left alignment.

---

## 2. Center Alignment

Everything is centered.

Example:

```
        Heading

    This paragraph
    is centered.
```

Center alignment is commonly used for:

- Hero sections
- Landing pages
- Titles
- Quotes
- Certificates
- Welcome messages

Because everything is centered, it naturally draws attention.

However, large paragraphs should usually **not** be center-aligned because they become harder to read.

---

## 3. Right Alignment

Everything begins from the right side.

Example:

```
          Heading

      This text starts
      from the right.
```

Right alignment is used less frequently.

It may be useful for:

- Certain artistic designs.
- Languages written from right to left.
- Decorative layouts.
- Special emphasis.

Using right alignment for large amounts of text in English usually makes reading more difficult.

---

# HTML Example

```html
<link rel="stylesheet" href="styles.css">

<div class="container">

<section class="alignment left">
<h2>Left-Aligned</h2>

<p>
This content is aligned to the left.
Left alignment is most common for body text because it follows
natural reading flow in left-to-right languages.
</p>

</section>

<section class="alignment center">

<h2>Center-Aligned</h2>

<p>
This content is centered.
Center alignment is useful for titles,
headings, and content that needs to become
the focal point.
</p>

</section>

<section class="alignment right">

<h2>Right-Aligned</h2>

<p>
This content is aligned to the right.
Right alignment can be used for stylistic emphasis
or when aligning content against the right edge
of a container.
</p>

</section>

</div>
```

---

# Understanding the HTML

The HTML creates three sections.

Each section demonstrates one alignment style.

Notice that every section has two classes.

Example:

```html
<section class="alignment left">
```

This means the section belongs to:

- The `.alignment` class.
- The `.left` class.

The browser combines the styles from both classes.

The same idea applies to:

```html
<section class="alignment center">
```

and

```html
<section class="alignment right">
```

This is a common technique in CSS because it allows classes to be reused.

---

# CSS Example

```css
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  line-height: 1.6;
  background: #f4f4f4;
  color: #333;
  padding: 2rem;
}

.container {
  max-width: 800px;
  margin: 0 auto;
}

.alignment {
  background: #fff;
  border-left: 4px solid #3498db;
  padding: 1.5rem;
  margin-bottom: 2rem;
  box-shadow: 0 2px 6px rgba(0,0,0,0.05);
  transition: all 0.3s ease;
}

.alignment:hover {
  transform: scale(1.02);
}

.alignment h2 {
  margin-bottom: 0.5rem;
  color: #3498db;
}

.left {
  text-align: left;
}

.center {
  text-align: center;
}

.right {
  text-align: right;
}
```

---

# Understanding the CSS

## `.container`

```css
.container {
    max-width: 800px;
    margin: 0 auto;
}
```

The container keeps everything centered while preventing the content from becoming too wide.

This makes reading much more comfortable.

---

## `.alignment`

```css
.alignment {
    background: white;
}
```

Adds a white background behind every example.

This separates each example from the gray page background.

---

```css
border-left: 4px solid #3498db;
```

Creates a blue line along the left side.

This acts as a visual accent that makes each section stand out.

---

```css
padding: 1.5rem;
```

Creates empty space inside each section.

Without padding, the text would touch the edges.

---

```css
margin-bottom: 2rem;
```

Creates space below each example.

Without it, every section would touch the next one.

---

```css
box-shadow: 0 2px 6px rgba(0,0,0,0.05);
```

Adds a subtle shadow.

The sections appear slightly raised from the page, giving them a modern card-like appearance.

---

```css
transition: all 0.3s ease;
```

Allows property changes to happen smoothly.

Without a transition, hover effects happen instantly.

With a transition, they animate smoothly.

---

## Hover Effect

```css
.alignment:hover {
    transform: scale(1.02);
}
```

When the mouse moves over a section:

- It becomes slightly larger.
- The animation feels smooth because of the transition property.

Small hover animations make websites feel more interactive.

---

## Changing Text Alignment

```css
.left {
    text-align: left;
}
```

Aligns all text to the left.

---

```css
.center {
    text-align: center;
}
```

Centers all text.

---

```css
.right {
    text-align: right;
}
```

Aligns all text to the right.

Notice that only **one CSS property** changes between these three classes.

That property is:

```css
text-align
```

Changing this single property completely changes how the content is presented.

---

# Design Term 3: Composition

Now that we understand alignment, let's move on to another important design concept called **Composition**.

Many beginners confuse **Layout** and **Composition** because both involve arranging elements.

However, they are **not exactly the same thing**.

- **Layout** focuses on *where* elements are placed.
- **Composition** focuses on *how those elements work together visually and artistically*.

In the next part, we'll explore **Composition** and **Balance**, two concepts that designers use to create visually pleasing and harmonious designs.


# Design Term 5: Hierarchy

Hierarchy is another fundamental concept in design. If layout determines **where** elements go and composition determines **how** they work together, hierarchy determines **what users notice first**.

A good visual hierarchy guides the user's eyes through the page in the order the designer intends.

Without hierarchy, users may not know:

- Where to look first.
- What information is most important.
- Which button they should click.
- Which section deserves the most attention.

A page where everything looks equally important is actually difficult to understand because nothing stands out.

---

# What is Hierarchy?

**Hierarchy** is the arrangement of elements according to their importance.

It creates an order that naturally guides the user's attention.

Think of hierarchy like reading a newspaper.

You usually notice:

1. The large headline.
2. The smaller subtitle.
3. The body text.
4. Any images or captions.

You don't read everything at once.

Your eyes naturally follow the hierarchy.

The same idea applies to websites.

---

# Why is Hierarchy Important?

A good hierarchy helps users:

- Quickly understand the page.
- Find important information.
- Complete tasks faster.
- Navigate the interface with less effort.
- Feel less overwhelmed.

Without hierarchy:

- Everything competes for attention.
- Users become confused.
- Important information gets ignored.

---

# How Designers Create Hierarchy

Designers use several techniques to establish hierarchy.

## 1. Size

Larger elements naturally attract more attention than smaller ones.

For example:

```text
BIG HEADING

Small paragraph explaining the heading.
```

The heading immediately catches your eye because of its size.

---

## 2. Color

Bright or bold colors attract attention faster than dull colors.

For example:

```text
Gray text

Bright blue button
```

Most people will notice the blue button first.

---

## 3. Contrast

Elements with strong contrast stand out more.

Example:

Black text on a white background is much easier to notice than light gray text on a white background.

We'll discuss contrast in more detail later.

---

## 4. Alignment

Proper alignment naturally guides users from one section to another.

Poor alignment breaks this visual flow.

---

## 5. White Space

Giving an important element more surrounding space makes it stand out.

This is one reason many modern websites appear spacious.

The extra empty space draws attention to the content.

---

## 6. Typography

Different font sizes, weights, and styles also create hierarchy.

For example:

```text
Main Heading
Subheading
Paragraph
Caption
```

Each level tells the reader how important the information is.

---

# Hierarchy Example

The lesson uses a promotional card advertising a Pro plan.

The design intentionally guides your attention in a specific order.

HTML:

```html
<link rel="stylesheet" href="styles.css">

<div class="card">

<div class="headline">
Upgrade to Pro
</div>

<div class="subheadline">
Get more features and storage
</div>

<div class="body-text">
The Pro plan offers advanced tools,
priority support,
and 10x more storage.
Perfect for professionals and teams
looking to scale their productivity.
</div>

<a href="#" class="call-to-action">
Start Free Trial
</a>

</div>
```

---

# Understanding the HTML

The card contains four important elements.

## `.headline`

This is the largest and most important text.

Users should notice this first.

---

## `.subheadline`

Provides additional information.

It supports the headline but is less important.

---

## `.body-text`

Explains the offer in greater detail.

It contains the largest amount of information but has the lowest visual priority.

---

## `.call-to-action`

This is the button users are expected to click.

Although it appears last in the reading order, its color makes it stand out visually.

This encourages interaction.

---

# CSS Example

```css
body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  background-color: #fefefe;
  margin: 40px;
  line-height: 1.6;
  color: #333;
}

.card {
  max-width: 600px;
  margin: 0 auto;
  background: #ffffff;
  border: 1px solid #ddd;
  border-radius: 10px;
  padding: 30px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.05);
}

.headline {
  font-size: 32px;
  color: #2c3e50;
  font-weight: bold;
  margin-bottom: 10px;
}

.subheadline {
  font-size: 20px;
  color: #555;
  margin-bottom: 20px;
}

.body-text {
  font-size: 16px;
  color: #666;
  margin-bottom: 20px;
}

.call-to-action {
  display: inline-block;
  background-color: #3498db;
  color: white;
  text-decoration: none;
  padding: 12px 24px;
  border-radius: 5px;
  font-weight: bold;
  transition: background 0.3s ease;
}

.call-to-action:hover {
  background-color: #2980b9;
}
```

---

# Understanding the CSS

## `.headline`

```css
font-size: 32px;
```

The large font size immediately attracts attention.

---

```css
font-weight: bold;
```

Makes the heading even more noticeable.

---

```css
color: #2c3e50;
```

Uses a dark color for strong readability.

---

## `.subheadline`

The font size is smaller than the headline.

This tells users it is important but not as important as the headline.

---

## `.body-text`

The paragraph has:

- Smaller font size.
- Softer gray color.

This reduces its visual weight.

It is still readable but doesn't compete with the headline.

---

## `.call-to-action`

The button uses:

- Bright blue background.
- White text.
- Bold font.
- Rounded corners.

These properties help it stand out from the rest of the card.

The hover effect changes the button color slightly, providing visual feedback that it is interactive.

---

# Design Term 6: Contrast

Another essential design principle is **Contrast**.

Contrast is one of the easiest ways to draw attention to important elements.

---

# What is Contrast?

**Contrast** is the difference between two or more visual elements.

The greater the difference, the stronger the contrast.

Contrast can exist in many forms.

For example:

- Light vs dark.
- Large vs small.
- Thick vs thin.
- Bright vs dull.
- Rough vs smooth.
- Bold vs regular text.

Designers use contrast to make important content stand out.

---

# Why is Contrast Important?

Contrast helps:

- Improve readability.
- Guide user attention.
- Separate different sections.
- Highlight buttons.
- Emphasize important information.
- Make interfaces easier to understand.

Poor contrast often makes websites difficult to use.

For example:

Light gray text on a white background has poor contrast and can be difficult to read.

Black text on a white background has excellent contrast and is much easier to read.

---

In the next part, we'll explore the **Contrast** example from the lesson, followed by **White Space**, **UI**, **UX**, and the final summary of all the design terms.
```


# Design Term 6: Contrast

Now that you understand what **contrast** is, let's look at the example from the lesson and understand how CSS is used to create strong and weak contrast.

Remember that contrast isn't only about making things look attractive—it also improves **readability**, **accessibility**, and helps users know what is important.

---

# Contrast Example

The lesson demonstrates contrast using a simple webpage that contains:

- A main heading
- A paragraph
- A highlighted box
- A high-contrast button
- A low-contrast paragraph

Each element demonstrates a different use of contrast.

---

## HTML Example

```html
<link rel="stylesheet" href="styles.css">

<div class="container">

<h1>Contrast in Design</h1>

<p>
Contrast helps draw attention to important elements.
It also makes content easier to read and visually engaging.
</p>

<div class="highlight-box">
This box stands out because of strong color contrast.
</div>

<button class="high-contrast-button">
Example button
</button>

<p class="low-contrast-text">
This text is harder to read due to low contrast with the background.
</p>

</div>
```

---

# Understanding the HTML

Let's examine each element.

## `<h1>`

This is the page heading.

It immediately tells visitors what the page is about.

---

## `<p>`

The paragraph explains why contrast is useful.

It serves as supporting information.

---

## `<div class="highlight-box">`

This box demonstrates **strong contrast**.

Its dark background and white text make it immediately noticeable.

---

## `<button>`

Buttons should always be easy to notice.

The designer therefore uses strong contrast so users immediately recognize it as something they can click.

---

## `.low-contrast-text`

This paragraph intentionally demonstrates **poor contrast**.

Because the text color is very close to the background color, it becomes harder to read.

The example shows what designers should generally avoid.

---

# CSS Example

```css
body {
    font-family: Arial, sans-serif;
    background-color: #f6f6f6;
    margin: 40px;
    color: #333;
}

.container {
    max-width: 700px;
    margin: 0 auto;
    padding: 30px;
    background-color: #ffffff;
    border-radius: 10px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.05);
}

h1 {
    font-size: 36px;
    margin-bottom: 10px;
    color: #111;
}

p {
    font-size: 18px;
    line-height: 1.6;
    margin-bottom: 25px;
}

.highlight-box {
    background-color: #222;
    color: #ffffff;
    padding: 20px;
    border-radius: 8px;
    font-size: 20px;
    font-weight: bold;
    text-align: center;
}

.low-contrast-text {
    color: #999999;
    font-size: 16px;
    margin-top: 30px;
}

.high-contrast-button {
    background-color: #e74c3c;
    color: white;
    border: none;
    padding: 12px 24px;
    font-size: 16px;
    font-weight: bold;
    border-radius: 5px;
    cursor: pointer;
    margin-top: 20px;
    transition: background 0.3s ease;
}

.high-contrast-button:hover {
    background-color: #c0392b;
}
```

---

# Understanding the CSS

## `.highlight-box`

```css
background-color: #222;
color: white;
```

This creates a **very dark background** with **bright white text**.

The difference between these colors is very large.

This is called **high contrast**.

High contrast improves readability and immediately draws attention.

---

## `.low-contrast-text`

```css
color: #999999;
```

This light gray text sits on a nearly white background.

Because the colors are very similar, there is **low contrast**.

Although the text is still visible, it requires more effort to read.

Designers generally avoid this because it hurts readability and accessibility.

---

## `.high-contrast-button`

The button uses:

- Bright red background
- White text
- Bold font

These properties make the button stand out.

Since buttons are interactive elements, users should immediately recognize them.

---

## Hover Effect

```css
.high-contrast-button:hover {
    background-color: #c0392b;
}
```

When the mouse hovers over the button, its background color changes slightly.

This provides visual feedback that the button is interactive.

---

# Accessibility and Contrast

Contrast is not only a design principle.

It is also an important **accessibility** requirement.

People with:

- Low vision
- Color blindness
- Poor eyesight
- Bright screen glare

depend on sufficient contrast to read content comfortably.

Many accessibility guidelines recommend maintaining adequate color contrast between text and its background.

A beautiful design that cannot be read is not a good design.

---

# Design Term 7: White Space

Another important design principle is **White Space**.

White space is one of the most misunderstood concepts among beginners.

Many people think white space means "making the background white."

That is **incorrect**.

---

# What is White Space?

**White Space**, also called **Negative Space**, is the empty space surrounding elements in a design.

It is simply the area where **nothing is placed**.

This space can surround:

- Headings
- Paragraphs
- Images
- Buttons
- Cards
- Icons
- Entire sections

Despite its name, white space does **not** have to be white.

It can be:

- Black
- Gray
- Blue
- Green
- Textured
- Patterned

The important thing is that the area is **empty**, giving surrounding elements room to breathe.

---

# Why is White Space Important?

White space helps:

- Improve readability.
- Reduce visual clutter.
- Separate different sections.
- Create visual hierarchy.
- Draw attention to important content.
- Make designs feel clean and modern.

Without enough white space, a webpage can feel crowded and overwhelming.

Modern websites often use generous white space because it improves the overall user experience.

---

In **Part 7 (Final Part)**, we'll cover:

- The White Space example (HTML and CSS)
- Understanding the CSS behind it
- UI (User Interface)
- UX (User Experience)
- The relationship between UI and UX
- A complete summary of all the design terms covered in this lesson.
# Design Term 7: White Space

In the previous part, we learned that **White Space** (also called **Negative Space**) is the empty space surrounding elements in a design.

Many beginners think empty space is wasted space, but professional designers know the opposite is true.

White space is an important design tool because it helps organize content and makes a design easier to understand.

---

# White Space Example

The lesson demonstrates white space using a simple webpage with two sections.

The first section uses generous white space.

The second section intentionally uses very little white space so you can compare the two designs.

---

## HTML Example

```html
<link rel="stylesheet" href="styles.css">

<div class="container">
  <h1>The Power of White Space</h1>

  <p>
    White space (or negative space) is the empty space around elements.
    It's not just "blank"—it gives your content room to breathe,
    improves focus, and adds elegance to the design.
  </p>

  <a href="#" class="button">Learn More</a>
</div>

<div class="no-whitespace">
  <strong>Without white space:</strong>
  This block has minimal padding, making the content feel cramped,
  harder to read, and less appealing.
</div>
```

---

# Understanding the HTML

Let's look at each section.

## `.container`

This is the main content area.

It contains:

- A heading
- A paragraph
- A button

Notice that these elements have plenty of surrounding space.

This demonstrates **good use of white space**.

---

## `.no-whitespace`

This second section intentionally has very little spacing.

The purpose is to show how content feels when white space is removed.

The text appears more crowded and less comfortable to read.

This comparison helps illustrate why white space is important.

---

# CSS Example

```css
body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f0f0f0;
}

.container {
  max-width: 800px;
  margin: 60px auto;
  background-color: #ffffff;
  padding: 60px;
  border-radius: 10px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.08);
}

h1 {
  font-size: 36px;
  margin-bottom: 20px;
  color: #2c3e50;
}

p {
  font-size: 18px;
  line-height: 1.8;
  color: #555;
  margin-bottom: 30px;
}

.button {
  display: inline-block;
  padding: 14px 28px;
  background-color: #27ae60;
  color: white;
  font-size: 16px;
  font-weight: bold;
  border: none;
  border-radius: 5px;
  text-decoration: none;
  transition: background 0.3s ease;
}

.button:hover {
  background-color: #219150;
}

.no-whitespace {
  background-color: #ffffff;
  padding: 10px;
  margin: 60px auto;
  width: 800px;
  box-shadow: 0 0 0 1px #ccc;
  font-size: 16px;
  color: #222;
}
```

---

# Understanding the CSS

## `.container`

```css
padding: 60px;
```

This large amount of padding creates generous space around the content.

Because the text is not touching the edges, it feels cleaner and easier to read.

---

```css
margin: 60px auto;
```

Creates empty space outside the container.

This separates it from other content on the page.

---

## Paragraph

```css
line-height: 1.8;
```

Increases the spacing between lines.

This improves readability.

---

## `.button`

The button also has generous padding.

This makes it:

- Easier to click.
- More comfortable to look at.
- More noticeable.

---

## `.no-whitespace`

```css
padding: 10px;
```

Notice how much smaller this padding is compared to the main container.

Because there is very little empty space around the text, the content feels cramped.

This demonstrates how removing white space can negatively affect readability.

---

# Software Development Design Terms

Besides general design concepts like layout and contrast, there are two terms that every web developer should know:

- UI (User Interface)
- UX (User Experience)

Although these terms are closely related, they mean different things.

---

# UI (User Interface)

**UI** stands for **User Interface**.

The User Interface is everything a user can **see** and **interact with** on a website or application.

Examples include:

- Buttons
- Navigation bars
- Menus
- Forms
- Text
- Icons
- Images
- Cards
- Sliders
- Checkboxes
- Input fields

In simple terms:

> **UI is the visual part of a website or application.**

A UI designer focuses on questions like:

- What color should the buttons be?
- How large should the headings be?
- Where should the navigation bar go?
- Which icons should be used?
- How should the page look?

Everything related to appearance belongs to the User Interface.

---

# UX (User Experience)

**UX** stands for **User Experience**.

Unlike UI, UX is **not only about appearance**.

UX is about **how users feel while using a product.**

A good user experience means the website is:

- Easy to use.
- Easy to understand.
- Fast.
- Accessible.
- Efficient.
- Enjoyable.

For example, imagine two shopping websites.

### Website A

- Confusing navigation.
- Tiny buttons.
- Slow checkout.
- Difficult forms.

Even if it looks beautiful, users may become frustrated.

This is **poor UX**.

---

### Website B

- Easy navigation.
- Clear buttons.
- Fast checkout.
- Simple forms.
- Logical page flow.

Users can complete their tasks quickly and comfortably.

This is **good UX**.

---

# UI vs UX

Many beginners confuse UI and UX.

Here's an easy way to remember the difference:

| UI | UX |
|----|----|
| How it **looks** | How it **feels** |
| Visual design | Overall experience |
| Colors | Ease of use |
| Buttons | User satisfaction |
| Fonts | User journey |
| Layout | Accessibility |

Think of a car.

- **UI** is the dashboard, steering wheel, buttons, and screen.
- **UX** is how enjoyable and easy the car is to drive.

A car can have a beautiful dashboard (good UI) but still be uncomfortable to drive (poor UX).

Likewise, a website can look amazing but still be frustrating to use.

The best products combine **excellent UI** with **excellent UX**.

---

# Summary

Throughout this lesson, you learned several important design terms that developers commonly use when working with designers.

## Layout

The arrangement of elements on a webpage.

It determines **where** things are placed.

---

## Alignment

The positioning of elements relative to one another.

Proper alignment creates order and improves readability.

---

## Composition

The artistic arrangement of elements so they work together visually.

Composition considers the overall appearance of the design.

---

## Balance

The distribution of visual weight.

A balanced design feels stable and harmonious.

Balance can be:

- Symmetrical
- Asymmetrical

---

## Hierarchy

The order of importance among elements.

Hierarchy guides users toward the most important information first.

---

## Contrast

The difference between visual elements.

Contrast improves readability and helps important content stand out.

---

## White Space

The empty space surrounding elements.

White space improves readability, organization, and visual appeal.

---

## UI (User Interface)

Everything users can see and interact with.

Examples include buttons, menus, forms, images, and text.

---

## UX (User Experience)

The overall experience users have while interacting with a website or application.

Good UX means the product is intuitive, efficient, accessible, and enjoyable to use.

---

# Final Thoughts

Understanding these design concepts will make you a stronger front-end developer because you'll be able to communicate more effectively with designers and make better design decisions in your own projects.

As you continue learning HTML, CSS, and JavaScript, you'll begin applying these principles naturally. Over time, they'll become an essential part of how you build modern, user-friendly websites.
