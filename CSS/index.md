# CSS Tutorial

Welcome to this beginner-friendly CSS tutorial. CSS (Cascading Style Sheets) is the language used to style and lay out HTML pages. You will learn CSS through short explanations, examples, and practice exercises.

> **Learning approach:** Read a section, try the example, change a value, and observe what happens in the browser.

## What you will learn

By the end of this tutorial, you should be able to:

- Add CSS to an HTML document.
- Select HTML elements and apply styles.
- Work with colors, fonts, text, spacing, and borders.
- Understand the CSS box model.
- Build page layouts with Flexbox and Grid.
- Make pages responsive on different screen sizes.
- Use pseudo-classes, pseudo-elements, and CSS variables.
- Organize and debug a stylesheet.

## 1. What is CSS?

CSS describes how HTML elements should look and where they should appear on a page.

HTML provides the **structure**:

```html
<h1>My first webpage</h1>
<p>This is a paragraph.</p>
```

CSS provides the **presentation**:

```css
h1 {
  color: navy;
  text-align: center;
}

p {
  font-size: 1.1rem;
}
```

A CSS rule has three main parts:

```css
selector {
  property: value;
}
```

- **Selector** chooses the HTML element.
- **Property** identifies what you want to change.
- **Value** specifies the new setting.

## 2. Adding CSS to HTML

There are three ways to add CSS.

### Inline CSS

Inline CSS is written in an HTML `style` attribute. It is useful for a quick test, but it is usually not recommended for a complete website.

```html
<p style="color: crimson;">This text is red.</p>
```

### Internal CSS

Internal CSS is written inside a `<style>` element in the `<head>` of an HTML document.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Internal CSS</title>
  <style>
    body {
      background-color: #f4f7fb;
    }

    h1 {
      color: #17365d;
    }
  </style>
</head>
<body>
  <h1>Welcome</h1>
</body>
</html>
```

### External CSS

External CSS is stored in a separate `.css` file. This is the recommended method because one stylesheet can be reused by many pages.

**HTML (`index.html`)**

```html
<head>
  <link rel="stylesheet" href="styles.css">
</head>
```

**CSS (`styles.css`)**

```css
body {
  margin: 0;
  font-family: Arial, sans-serif;
}
```

## 3. CSS selectors

Selectors let you target elements to style.

```css
/* Element selector */
p {
  color: #333;
}

/* Class selector: matches class="note" */
.note {
  background-color: #fff3cd;
}

/* ID selector: matches id="main-title" */
#main-title {
  color: #0d47a1;
}

/* Group selector */
h1, h2, h3 {
  font-family: Georgia, serif;
}

/* Descendant selector */
nav a {
  text-decoration: none;
}
```

Prefer classes for reusable styles. Use an ID when an element is unique, and avoid using IDs as your main styling system.

### Combining selectors

```css
/* Direct child */
.card > p {
  margin-top: 0;
}

/* Adjacent sibling */
h2 + p {
  font-weight: bold;
}

/* Attribute selector */
input[type="email"] {
  border-color: steelblue;
}
```

## 4. Comments and formatting

CSS comments are ignored by the browser and help explain your code.

```css
/* Page-wide defaults */
body {
  margin: 0;
  color: #222;
}
```

Keep one declaration per line and use consistent indentation. A semicolon should end each declaration.

## 5. Colors and backgrounds

CSS supports named colors, hexadecimal colors, RGB, HSL, and transparent colors.

```css
.box {
  color: white;
  background-color: #2563eb; /* hexadecimal */
  border-color: rgb(30, 64, 175); /* RGB */
}

.highlight {
  background: hsl(48, 96%, 89%); /* hue, saturation, lightness */
}
```

You can add an image background:

```css
.hero {
  min-height: 240px;
  background-image: url("images/banner.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}
```

## 6. Text and fonts

```css
article {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1rem;
  line-height: 1.6;
  color: #263238;
}

article h1 {
  font-size: 2.25rem;
  font-weight: 700;
  letter-spacing: 0.02em;
  text-align: center;
  text-transform: uppercase;
}

a {
  color: #1565c0;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}
```

Use relative units such as `rem`, `%`, and `em` when possible. They help content adapt to the user's settings and screen size.

## 7. The CSS box model

Every HTML element can be understood as a box:

1. **Content** — text or other content.
2. **Padding** — space inside the border.
3. **Border** — line around the padding and content.
4. **Margin** — space outside the border.

```css
.card {
  width: 300px;
  padding: 20px;
  border: 2px solid #90a4ae;
  margin: 24px auto;
}
```

A useful default makes width calculations easier:

```css
* {
  box-sizing: border-box;
}
```

With `border-box`, an element's declared width includes its padding and border.

## 8. Borders, shadows, and rounded corners

```css
.panel {
  border: 1px solid #d1d5db;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgb(0 0 0 / 12%);
  padding: 1.5rem;
}
```

## 9. Display and positioning

Common `display` values include:

- `block` — starts on a new line and usually fills the available width.
- `inline` — flows with text and ignores width and height.
- `inline-block` — flows inline but accepts width and height.
- `none` — removes the element from the layout.
- `flex` and `grid` — create modern layouts.

```css
.badge {
  display: inline-block;
  padding: 0.35rem 0.7rem;
  background: #e0f2fe;
  border-radius: 999px;
}
```

Positioning example:

```css
.container {
  position: relative;
}

.label {
  position: absolute;
  top: 1rem;
  right: 1rem;
}
```

Use absolute positioning for elements that need to be placed relative to a container, not as a replacement for normal page layout.

## 10. Flexbox layout

Flexbox is useful for arranging items in one direction: a row or a column.

```html
<div class="toolbar">
  <strong>My Site</strong>
  <nav>
    <a href="#home">Home</a>
    <a href="#about">About</a>
  </nav>
</div>
```

```css
.toolbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
  padding: 1rem;
}

.toolbar nav {
  display: flex;
  gap: 1rem;
}
```

Important Flexbox properties include `flex-direction`, `justify-content`, `align-items`, `flex-wrap`, `gap`, and `flex`.

## 11. CSS Grid layout

Grid is useful for two-dimensional layouts with rows and columns.

```css
.gallery {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}

.gallery-card {
  padding: 1rem;
  background: #f1f5f9;
}
```

A responsive grid can automatically create as many columns as fit:

```css
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 1rem;
}
```

## 12. Pseudo-classes and pseudo-elements

Pseudo-classes style a special state of an element.

```css
button:hover {
  background-color: #1d4ed8;
}

button:focus-visible {
  outline: 3px solid #f59e0b;
  outline-offset: 3px;
}

li:first-child {
  font-weight: bold;
}
```

Pseudo-elements style part of an element or add generated content.

```css
.required::after {
  content: " *";
  color: crimson;
}
```

## 13. CSS outline

An outline is a line drawn outside an element's border. Unlike a border, an outline does not take up layout space.

```css
input:focus {
  outline: 3px solid #60a5fa;
  outline-offset: 2px;
}
```

The outline shorthand follows this pattern:

```css
selector {
  outline: width style color;
}
```

For example:

```css
.demo {
  outline: 4px dashed tomato;
}
```

Common outline styles include `solid`, `dashed`, `dotted`, and `none`. Do not remove focus outlines unless you replace them with another clearly visible focus style. Visible focus is important for keyboard users.

## 14. Transitions and simple animations

A transition makes a change happen gradually.

```css
.button {
  background-color: #2563eb;
  color: white;
  transition: background-color 180ms ease, transform 180ms ease;
}

.button:hover {
  background-color: #1d4ed8;
  transform: translateY(-2px);
}
```

A simple animation uses `@keyframes`:

```css
@keyframes fade-in {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.message {
  animation: fade-in 400ms ease-out;
}
```

## 15. Responsive design

Responsive design allows a page to work on phones, tablets, and larger screens.

```css
.page {
  width: min(100% - 2rem, 1100px);
  margin-inline: auto;
}

@media (max-width: 700px) {
  .toolbar {
    align-items: flex-start;
    flex-direction: column;
  }

  .gallery {
    grid-template-columns: 1fr;
  }
}
```

Also include this viewport setting in HTML:

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

## 16. CSS variables

Variables make repeated values easier to maintain.

```css
:root {
  --brand-color: #2563eb;
  --text-color: #1f2937;
  --page-space: 1rem;
}

body {
  color: var(--text-color);
  padding: var(--page-space);
}

.button {
  background-color: var(--brand-color);
}
```

## 17. The cascade and specificity

When multiple rules target the same element, the browser considers importance, specificity, and source order.

```css
p {
  color: navy;
}

.article-text {
  color: darkgreen;
}
```

An element with `class="article-text"` is green because a class selector is more specific than an element selector. Avoid using `!important` unless you have a well-documented reason.

## 18. Complete practice example

Save the following as `index.html`, then create `styles.css` with the CSS below it.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Student Profile</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <main class="profile">
    <h1>Student Profile</h1>
    <p class="intro">Learning HTML and CSS one example at a time.</p>
    <a class="button" href="#projects">View projects</a>
  </main>
</body>
</html>
```

```css
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
  color: #1f2937;
  background: #eff6ff;
}

.profile {
  width: min(90%, 600px);
  margin: 4rem auto;
  padding: 2rem;
  text-align: center;
  background: white;
  border: 1px solid #bfdbfe;
  border-radius: 1rem;
  box-shadow: 0 8px 20px rgb(30 64 175 / 12%);
}

.intro {
  line-height: 1.6;
}

.button {
  display: inline-block;
  padding: 0.75rem 1rem;
  color: white;
  background: #2563eb;
  border-radius: 0.5rem;
  text-decoration: none;
}

.button:hover,
.button:focus-visible {
  background: #1d4ed8;
}
```

## Practice exercises

1. Change the page colors and font family.
2. Add a profile image and give it a circular border.
3. Create three project cards using CSS Grid.
4. Add a visible focus style to every link and button.
5. Add a media query that changes the card layout on small screens.
6. Replace repeated colors with CSS variables.
7. Inspect the page with browser developer tools and identify the box model values.

## Quick reference

| Property | Purpose | Example |
| --- | --- | --- |
| `color` | Text color | `color: #222;` |
| `background-color` | Background color | `background-color: white;` |
| `font-size` | Text size | `font-size: 1rem;` |
| `margin` | Outside spacing | `margin: 1rem;` |
| `padding` | Inside spacing | `padding: 1rem;` |
| `border` | Border around an element | `border: 1px solid gray;` |
| `display` | Layout behavior | `display: flex;` |
| `gap` | Space between layout items | `gap: 1rem;` |
| `outline` | Line outside the border | `outline: 2px solid blue;` |
| `transform` | Visual movement or scaling | `transform: scale(1.05);` |

## Good CSS habits

- Use external stylesheets for reusable styles.
- Use meaningful class names such as `.profile-card` rather than `.blue-box`.
- Keep selectors simple and avoid unnecessary specificity.
- Test keyboard focus, not only mouse hover.
- Use responsive units and test multiple screen sizes.
- Check contrast so text is readable.
- Validate your HTML and use browser developer tools to debug styles.
