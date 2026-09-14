# How Do You Work with External Fonts Like Font Squirrel and Google Fonts?

## What Are External Fonts?

- An **external font** is a font file that is not included directly inside your project files.
- External fonts are usually hosted on a **separate server**.
- A server is a computer that provides data or services to other computers over a network.
- External fonts give you more flexibility because you can use custom fonts that may not already be installed on the user's device.

### Popular External Font Resources

- **Google Fonts** → Large collection of free and open-source fonts.
- **Font Squirrel** → Resource for finding and downloading custom fonts.

---

# Google Fonts

- Google Fonts is a Google service that provides a large collection of fonts.
- Many of the fonts are designed specifically for web development.
- You can either:
  1. Download the font files and use them locally.
  2. Use the fonts directly from Google's servers as external fonts.

---

# Google Fonts Interface

The Google Fonts website provides several sections:

- **Fonts** → Find, preview, and filter fonts.
- **Noto** → A collection of fonts designed to support many languages and writing systems.
- **Icons** → Find and download icons for web projects.
- **Learn** → Learn about fonts, best practices, and frequently asked questions.

---

# Previewing Google Fonts

Before choosing a font, you can preview it.

You can:

- Enter your own preview text.
- Change the preview font size.
- Filter fonts based on characteristics.
- Compare different font families.

### Why Preview Text?

Using your own text lets you see what the font will actually look like in your website.

For example:

  Preview text: "freeCodeCamp"

You can adjust the font size using the size control/slider.

---

# Viewing Font Information

When you click on a font, you can see information such as:

- Font designer.
- Preview text.
- Different font styles.
- Font weights.
- Type tester.
- Individual glyphs.
- License information.

Common font weights include:

- Thin
- Light
- Regular
- Medium
- Bold
- Black

---

# Selecting a Google Font

When you are ready to use a font:

1. Open the font.
2. Choose the styles/weights you need.
3. Click **Get font**.
4. Review your selected fonts.
5. Choose whether to download the fonts or use them externally.

You can select multiple font families at the same time.

---

# Two Ways to Use Google Fonts

You can use Google Fonts in two main ways:

## 1. Download the Font

- Click **Download all**.
- The font files are downloaded to your computer.
- You can then include them in your project as local font files.
- You can use `@font-face` to define them.

## 2. Use the Font as an External Font

- Click **Get embed code**.
- Google provides the code needed to load the font from Google's servers.
- The font is downloaded when users visit your website.

---

# Linking Google Fonts with HTML

There are two common ways to include Google Fonts:

1. Using the HTML `<link>` element.
2. Using CSS `@import`.

The `<link>` method is generally placed inside the `<head>` of your HTML document.

Example:

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">

  <link rel="stylesheet" href="styles.css">

### What These Do

- `preconnect` helps the browser establish connections to Google's font servers.
- The Google Fonts stylesheet loads the selected font.
- `styles.css` loads your own CSS file.

---

# Using the Google Font in CSS

Once the font is loaded, you can use it with `font-family`.

Example:

  body {
    font-family: "Roboto", sans-serif;
  }

- `"Roboto"` is the custom font.
- `sans-serif` is the fallback font.

### Fallback

If Roboto cannot be loaded, the browser can use another available `sans-serif` font.

---

# Font Weights

Different font weights can be selected from Google Fonts.

Common values:

- `100` → Thin
- `300` → Light
- `400` → Regular
- `500` → Medium
- `700` → Bold
- `900` → Black

Example:

  .regular {
    font-family: "Roboto", sans-serif;
    font-weight: 400;
  }

  .bold {
    font-family: "Roboto", sans-serif;
    font-weight: 700;
  }

---

# Font Styles

Fonts can also have normal and italic versions.

Example:

  .normal {
    font-family: "Roboto", sans-serif;
    font-weight: 400;
    font-style: normal;
  }

  .italic {
    font-family: "Roboto", sans-serif;
    font-weight: 400;
    font-style: italic;
  }

---

# Using @import with Google Fonts

Instead of using `<link>`, you can import the Google Font directly into your CSS file.

Example:

  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

Then use the font normally:

  body {
    font-family: "Roboto", sans-serif;
  }

### Important

The CSS rules for using the font are the same whether you load the font using `<link>` or `@import`.

---

# Choosing Specific Font Styles

You do not have to include every available font weight or style.

For example, if you only need:

- Regular (`400`)
- Bold (`700`)

you can select only those styles.

### Why?

Loading unnecessary font styles can increase the amount of data that needs to be downloaded.

**Rule:** Only load the font weights and styles you actually need.

---

# Google Fonts Example

HTML:

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">

  <p class="regular">Regular text</p>
  <p class="bold">Bold text</p>

CSS:

  .regular {
    font-family: "Roboto", sans-serif;
    font-weight: 400;
  }

  .bold {
    font-family: "Roboto", sans-serif;
    font-weight: 700;
  }

---

# Font Squirrel

- Font Squirrel is another popular resource for finding custom fonts.
- It provides many fonts that can be downloaded and used in web projects.
- It is especially useful when you want to find fonts for your own designs.

---

# Previewing Fonts on Font Squirrel

When you search for a font and open its page, you can find information such as:

- Samples/specimens.
- Test Drive.
- Glyphs.
- License information.
- Webfont Kit.

You can also see different font styles and variations.

Examples:

- Thin
- Light
- Regular
- Medium
- Bold
- Black
- Italic variations

---

# Using Font Squirrel

Once you find a font you want:

1. Open the font's page.
2. Go to the **Webfont Kit** tab.
3. Check the font's license.
4. Make sure the license allows `@font-face` embedding.
5. Choose the desired subset.
6. Choose the desired format.
7. Click **Download @font-face Kit**.

---

# Font Squirrel Webfont Kit

Clicking **Download @font-face Kit** downloads a compressed ZIP file.

After extracting it, you may find:

- A `web fonts` folder.
- A license text file.
- An HTML instruction file.

Example structure:

  webfont-kit/
    web fonts/
    Apache License.txt
    How_to_use_webfonts.html

---

# Web Fonts Folder

The `web fonts` folder contains the font files needed for your project.

Different font styles and weights may be organized into separate folders.

For example:

  web fonts/
    roboto_thin/
    roboto_light/
    roboto_regular/
    roboto_medium/
    roboto_bold/
    roboto_black/

---

# Font Squirrel Instructions

The downloaded HTML instruction file explains how to:

- Add the font files to your project.
- Create an `@font-face` declaration.
- Add the font to your stylesheet.
- Use the font in your CSS rules.

The general idea is:

  @font-face {
    font-family: "MyFont";
    src: url("myfont.woff2") format("woff2");
  }

Then:

  body {
    font-family: "MyFont", sans-serif;
  }

---

# Hosting Fonts Externally

You can also host your custom font files on a separate server.

Then your website can load those fonts as external resources.

This gives you more flexibility over your website's typography and design.

---

# Advantages of External Fonts

External fonts can:

- Give your website a unique appearance.
- Provide access to fonts that users may not have installed.
- Give you more design flexibility.
- Improve the visual identity of your website.

---

# Disadvantages of External Fonts

Using too many external fonts can increase website load time.

This can negatively affect:

- Page loading speed.
- Performance.
- User experience.

### Best Practice

Find a balance between:

**Design + Performance**

Do not load many unnecessary fonts, weights, or styles.

---

# Key Things to Remember

- **External font** → A font hosted outside your project files.
- **Google Fonts** → Popular collection of free/open-source web fonts.
- **Font Squirrel** → Website for finding and downloading custom fonts.
- **Get font** → Used to select fonts on Google Fonts.
- **Download all** → Downloads the selected font files.
- **Get embed code** → Provides code for loading fonts externally.
- `<link>` → One way to load Google Fonts.
- `@import` → Another way to load Google Fonts from CSS.
- `@font-face` → Used to define locally hosted/custom font files.
- `font-weight` → Controls how thick the font appears.
- `font-style` → Controls normal/italic styling.
- `format()` → Tells the browser the font file format.
- **Webfont Kit** → Font Squirrel package containing files/instructions for using a font on the web.
- **License** → Always check whether the font can legally be used and embedded.
- **Performance** → Too many external fonts can increase load time.

# Memory Trick

**Google Fonts → Select → Get Font → Link/Import → Use**

**Font Squirrel → Find → Check License → Webfont Kit → @font-face → Use**

# Quick Summary

External fonts allow websites to use custom fonts that are not necessarily installed on the user's device.

Google Fonts makes it easy to load fonts externally using `<link>` or `@import`.

Font Squirrel allows you to download fonts and generate a Webfont Kit that can be used with `@font-face`.

Always:

1. Choose only the fonts you need.
2. Load only the necessary weights/styles.
3. Check font licenses.
4. Use fallback fonts.
5. Balance visual design with website performance.
