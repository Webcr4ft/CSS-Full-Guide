# CSS Repository

# How Do You Create Good Background and Foreground Contrast in Your Designs?

## *Introduction*

**NOTE:** Some of the interactive examples use CSS properties you may not have learned yet. Don't worry about understanding every line of code. Their purpose is to visually demonstrate the design concepts so you can recognize them when building your own websites.

---

# *What Is Contrast?*

Contrast is the **difference between two colors**. It determines how easy it is for people to distinguish one color from another.

A higher contrast makes content much easier to read, while a lower contrast makes content more difficult to see.

Examples:

* Black text on a white background = **Very High Contrast**
* White text on a black background = **Very High Contrast**
* Light purple text on a light blue background = **Low Contrast**

The greater the difference between the colors, the easier the content is to read.

---

# *Example: High Contrast vs Low Contrast*

```html
<style>
.example {
  padding: 20px;
  margin-bottom: 20px;
  font-size: 18px;
  font-family: sans-serif;
}

.high-contrast {
  background-color: black;
  color: white;
}

.low-contrast {
  background-color: #add8e6;
  color: #dda0dd;
}

.label {
  font-weight: bold;
  margin-bottom: 5px;
}
</style>

<div class="example high-contrast">
  <div class="label">High Contrast</div>
  This text has high contrast (black background and white text).
</div>

<div class="example low-contrast">
  <div class="label">Low Contrast</div>
  This text has low contrast (light blue background and light purple text).
</div>
```

### *Explanation*

The first example is extremely easy to read because the colors are completely different.

The second example is much harder to read because the colors are very similar.

Even if you personally can read the text, many users may struggle because of:

* Poor eyesight
* Color blindness
* Bright sunlight
* Low-quality screens
* Small screen sizes

This is why choosing proper contrast is important.

---

# *Contrast Isn't Only for Backgrounds*

Contrast is especially important for **text**.

Here is another example.

```html
<style>
.text-example {
  padding: 10px;
  margin-bottom: 20px;
  font-size: 18px;
  font-family: sans-serif;
}

.text-high-contrast {
  background-color: white;
  color: black;
}

.text-low-contrast {
  background-color: #add8e6;
  color: #dda0dd;
}

.label {
  font-weight: bold;
  margin-bottom: 5px;
  display: block;
}
</style>

<div class="text-example text-high-contrast">
  <span class="label">High Contrast Text</span>
  This is high contrast text: black text on a white background.
</div>

<div class="text-example text-low-contrast">
  <span class="label">Low Contrast Text</span>
  This is low contrast text: purple text on a light blue background.
</div>
```

## *Explanation*

Black text on white is extremely readable.

Purple text on light blue is difficult to read because the colors are too close together.

Whenever users must read text, your first priority should always be readability.

---

# *How Do We Measure Contrast?*

Instead of guessing whether colors are readable, web developers use **contrast ratios**.

These ratios are defined by the **Web Content Accessibility Guidelines (WCAG).**

There are two important standards.

## *AA Standard*

* Contrast Ratio: **4.5 : 1**
* Minimum accessibility requirement
* Suitable for most websites

## *AAA Standard*

* Contrast Ratio: **7 : 1**
* Highest accessibility level
* Easier for almost everyone to read

Think of it like this:

```
4.5:1  = Minimum Pass (AA)

7:1    = Excellent (AAA)
```

---

# *Example of AA and AAA*

```html
<style>
.contrast-example {
  padding: 15px;
  margin-bottom: 20px;
  font-size: 18px;
  font-family: sans-serif;
}

.aa-contrast {
  background-color: #ffffff;
  color: #4b4b4b;
}

.aaa-contrast {
  background-color: #ffffff;
  color: #1a1a1a;
}

.label {
  font-weight: bold;
  margin-bottom: 8px;
  display: block;
}
</style>

<div class="contrast-example aa-contrast">
  <span class="label">AA Standard (Contrast Ratio ~4.5:1)</span>
  This text meets the minimum accessibility standard for contrast.
</div>

<div class="contrast-example aaa-contrast">
  <span class="label">AAA Standard (Contrast Ratio ~7:1)</span>
  This text meets the highest accessibility standard for contrast.
</div>
```

### *Explanation*

The darker the text becomes against the white background, the easier it becomes to read.

That increases the contrast ratio.

---

# *Checking Contrast Ratios*

Many websites allow you to compare two colors.

However, modern browsers can also calculate contrast directly inside **Developer Tools**, making it easy to test your color choices while building websites.

---

# *Maximum Possible Contrast*

The highest possible contrast ratio is:

```
21 : 1
```

This occurs when using:

* Black (#000000)
* White (#FFFFFF)

Example:

```html
<style>
.contrast-21 {
  background-color: white;
  color: black;
  padding: 15px;
  font-family: sans-serif;
  font-size: 18px;
  margin-bottom: 20px;
}

.label {
  font-weight: bold;
  margin-bottom: 8px;
  display: block;
}
</style>

<div class="contrast-21">
  <span class="label">Contrast Ratio 21:1</span>
  This is black text on a white background, which has the highest contrast ratio of 21:1.
</div>
```

This easily exceeds the AAA accessibility requirement.

---

# *Example of Poor Contrast*

Now compare that with purple text on blue.

```html
<style>
.purple-on-blue {
  background-color: #0000cc;
  color: #800080;
  padding: 15px;
  font-family: sans-serif;
  font-size: 18px;
}
</style>

<div class="purple-on-blue">
  <span class="label">Purple on Blue (Lower Contrast)</span>
  This doesn't meet the AA standard.
</div>
```

This combination has a contrast ratio of only:

```
1.48 : 1
```

That fails accessibility standards.

---

# *How Can You Improve Contrast?*

There are **three main color properties** that affect contrast.

## *1. Hue*

Hue means the basic color family.

Examples include:

* Red
* Blue
* Green
* Yellow
* Orange
* Purple

Changing to a completely different hue can sometimes improve contrast.

Example:

```html
.red-on-blue {
  background-color: #0000cc;
  color: #ff0000;
}
```

Unfortunately, changing only the hue increases the ratio only slightly:

```
1.49 : 1
```

Still not good enough.

---

# *2. Saturation*

Saturation describes how rich or intense a color is.

Low saturation:

* Looks dull
* Looks grayish

High saturation:

* Looks bright
* Looks vibrant

Example:

```html
.low-sat-red-on-blue {
  background-color: #0000cc;
  color: #b23333;
}

.high-sat-red-on-blue {
  background-color: #0000cc;
  color: #ff4d4d;
}
```

Results:

Low saturation:

```
≈1.49 : 1
```

Higher saturation:

```
≈3.54 : 1
```

This is better, but still below the required AA standard.

---

# *3. Lightness*

Lightness measures how much white or black is mixed into a color.

Higher lightness:

* Brighter colors

Lower lightness:

* Darker colors

Changing the lightness often has the biggest effect on readability.

Example:

```html
.dark-red-on-light-blue {
  background-color: #add8e6;
  color: #8b0000;
}
```

Now the contrast ratio becomes:

```
10.34 : 1
```

This easily exceeds the AAA accessibility requirement.

---

# *Complete Comparison*

```html
<style>
.blue-bg {
  background-color: #add8e6;
}

.low-sat-red-on-blue {
  color: #b23333;
}

.high-sat-red-on-blue {
  color: #ff4d4d;
}

.dark-red-on-light-blue {
  background-color: #add8e6;
  color: #8b0000;
}
</style>

<div class="low-sat-red-on-blue blue-bg">
  Low Saturation Red (≈1.49:1)
</div>

<div class="high-sat-red-on-blue blue-bg">
  Higher Saturation Red (≈3.54:1)
</div>

<div class="dark-red-on-light-blue">
  Dark Red on Light Blue (≈10.34:1)
</div>
```

Notice how each adjustment improves readability.

---

# *Key Things to Remember*

* Contrast is the difference between two colors.
* High contrast makes text easier to read.
* Low contrast makes text difficult to read.
* WCAG recommends:
  * AA = 4.5 : 1
  * AAA = 7 : 1
* Black on white has the maximum ratio of **21 : 1**.
* Contrast can be improved by adjusting:
  * Hue
  * Saturation
  * Lightness
* Modern browsers can measure contrast inside Developer Tools.
* Accessibility should always be more important than visual style.

---

# *Repository Summary*

When choosing colors in CSS, don't rely only on what looks attractive. Always think about readability and accessibility. A beautiful design is only successful if every user can comfortably read and interact with it. By understanding **hue**, **saturation**, **lightness**, and **contrast ratios**, you'll create websites that are both visually appealing and accessible to everyone.
