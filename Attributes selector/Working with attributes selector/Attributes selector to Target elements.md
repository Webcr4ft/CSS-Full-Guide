# How to Use the Attribute Selector to Target Elements with the `lang` and `data-lang` Attributes

Attribute selectors can be used to target HTML elements based on their attributes.

This is especially useful when working with:

- Multiple languages.
- The `lang` attribute.
- Custom `data-*` attributes.
- Language-specific styling.
- Content that needs different styles based on stored metadata.

---

# The `lang` Attribute

The `lang` attribute is used in HTML to specify the language of an element's content.

For example:

    <p lang="en">This is an English paragraph.</p>

    <p lang="fr">Ceci est un paragraphe en français.</p>

Here:

    lang="en"

means the content is in English.

And:

    lang="fr"

means the content is in French.

---

# Targeting a Specific `lang` Value

You can use an attribute selector to target elements with a specific `lang` value.

Syntax:

    element[lang="value"] {
      property: value;
    }

Example:

    p[lang="en"] {
      font-style: italic;
    }

This selector means:

    Select <p> elements
    where lang="en"

---

# Complete `lang` Example

HTML:

    <link rel="stylesheet" href="styles.css">

    <p lang="en">This is an English paragraph.</p>

    <p lang="fr">Ceci est un paragraphe en français.</p>

CSS:

    p[lang="en"] {
      font-style: italic;
    }

Only the English paragraph will receive the italic style.

The French paragraph will remain unaffected.

---

# Why Use `lang` Attribute Selectors?

This can be useful on multilingual websites.

For example, a webpage could contain:

    <p lang="en">Hello, welcome to our website.</p>

    <p lang="fr">Bonjour, bienvenue sur notre site.</p>

    <p lang="es">Hola, bienvenido a nuestro sitio web.</p>

You could style each language differently:

    p[lang="en"] {
      font-style: italic;
    }

    p[lang="fr"] {
      color: blue;
    }

    p[lang="es"] {
      font-weight: bold;
    }

This allows CSS to apply different styles depending on the language specified in the HTML.

---

# The `data-lang` Attribute

`data-lang` is a **custom data attribute**.

HTML allows developers to create custom attributes that begin with:

    data-

For example:

    data-lang

can be used to store language-related information on an element.

Example:

    <p data-lang="fr">Ceci est un paragraphe en français.</p>

    <p data-lang="en">This is a paragraph in English.</p>

The values stored in `data-lang` can then be targeted using CSS.

---

# Targeting `data-lang`

You can use:

    element[data-lang="value"] {
      property: value;
    }

Example:

    p[data-lang="fr"] {
      color: blue;
    }

This means:

    Select <p> elements
    where data-lang="fr"

---

# Complete `data-lang` Example

HTML:

    <link rel="stylesheet" href="styles.css">

    <p data-lang="fr">Ceci est un paragraphe en français.</p>

    <p data-lang="en">This is a paragraph in English.</p>

CSS:

    p[data-lang="fr"] {
      color: blue;
    }

Only the paragraph with:

    data-lang="fr"

will have blue text.

---

# `lang` vs `data-lang`

Although they may look similar, they serve different purposes.

### `lang`

    <p lang="fr">Bonjour</p>

The `lang` attribute is a standard HTML attribute used to identify the language of an element's content.

### `data-lang`

    <p data-lang="fr">Bonjour</p>

The `data-lang` attribute is a custom data attribute that stores additional information.

Think of it as:

    lang
    ↓
    Standard HTML language information

    data-lang
    ↓
    Custom data stored by the developer

---

# Attribute Selectors Are Based on the HTML Attribute

CSS doesn't need to know what the attribute means.

It simply looks for the specified attribute and value.

For example:

    p[lang="en"] {
      font-style: italic;
    }

CSS checks:

    Is this a <p>?
    ↓
    Does it have lang="en"?
    ↓
    Yes → Apply the style
    No → Don't apply the style

The same principle works with:

    p[data-lang="fr"] {
      color: blue;
    }

---

# Targeting the Attribute Without a Specific Value

You can also target elements that have the attribute, regardless of its value.

For `lang`:

    p[lang] {
      font-weight: bold;
    }

This targets:

    <p lang="en">English</p>

    <p lang="fr">Français</p>

    <p lang="es">Español</p>

because all of them have a `lang` attribute.

Similarly:

    p[data-lang] {
      font-weight: bold;
    }

targets any `<p>` that has a `data-lang` attribute.

---

# Targeting Multiple Language Values

You can create separate selectors for different languages.

Example:

    p[lang="en"] {
      font-style: italic;
    }

    p[lang="fr"] {
      color: blue;
    }

    p[lang="es"] {
      font-weight: bold;
    }

Each selector targets a different language.

---

# Why `data-*` Attributes Are Useful

Custom `data-*` attributes allow developers to store extra information directly on HTML elements.

Examples:

    data-lang
    data-category
    data-id
    data-type
    data-status

For example:

    <div data-category="technology">Technology</div>

    <div data-category="sports">Sports</div>

You can target them with CSS:

    div[data-category="technology"] {
      font-weight: bold;
    }

The same attribute-selector principle used with `data-lang` can be applied to other `data-*` attributes.

---

# Dynamic and Context-Aware Styling

Attribute selectors allow CSS to apply styles based on information stored in HTML.

For example:

    p[lang="en"] {
      font-style: italic;
    }

    p[data-lang="fr"] {
      color: blue;
    }

The HTML contains the information, and CSS uses that information to determine which styles should be applied.

This makes attribute selectors useful for creating more context-aware webpages.

---

# Key Memory Trick

Remember:

    [lang="en"]
    ↓
    Find elements where lang equals "en"

    [data-lang="fr"]
    ↓
    Find elements where data-lang equals "fr"

The basic pattern is:

    element[attribute="value"]

Think:

    HTML attribute
          ↓
    Attribute selector
          ↓
    Matching element
          ↓
    CSS style applied

---

# Quick Summary

- The `lang` attribute specifies the language of an element's content.
- `p[lang="en"]` targets paragraphs where `lang` is set to `"en"`.
- `data-lang` is a custom `data-*` attribute that can store language information.
- `p[data-lang="fr"]` targets paragraphs where `data-lang` is `"fr"`.
- `p[lang]` targets paragraphs that have a `lang` attribute, regardless of its value.
- `p[data-lang]` targets paragraphs that have a `data-lang` attribute, regardless of its value.
- Attribute selectors allow CSS to apply styles based on metadata stored in HTML.
- `lang` is a standard HTML attribute, while `data-lang` is a custom data attribute.
- The general syntax is:

    element[attribute="value"] {
      property: value;
    }
