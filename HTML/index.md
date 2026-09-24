# HTML 5 Tutorials

A beginner-friendly, hands-on HTML course for creating well-structured web pages.

> **Learning approach:** Read a short lesson, type the example yourself, open it in a browser, and then complete the exercise. HTML is learned by building.

## Course goals

By the end of this tutorial, you should be able to:

- Create a valid HTML document from scratch.
- Structure content with headings, paragraphs, lists, links, images, tables, and forms.
- Use meaningful semantic elements to describe page structure.
- Add CSS and JavaScript to an HTML page.
- Build accessible, responsive pages using good HTML practices.
- Organize files and publish a small multi-page website.

## What you need

1. A modern web browser such as Chrome, Firefox, Edge, or Safari.
2. A text editor such as VS Code, Notepad++, or any plain-text editor.
3. A folder where you can save your practice files.

Create a file named `index.html`, then open it in your browser whenever you want to see your work.

---

## 1. Introduction to HTML

**HTML** means **HyperText Markup Language**. It describes the structure and meaning of content on a web page. HTML is not a programming language: it uses elements and attributes to mark up content.

A simple HTML page:

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>My first page</title>
  </head>
  <body>
    <h1>Hello, web!</h1>
    <p>I am learning HTML.</p>
  </body>
</html>
```

### What the document contains

| Part | Purpose |
| --- | --- |
| `<!doctype html>` | Tells the browser to use modern HTML. |
| `<html lang="en">` | Root element; identifies the page language. |
| `<head>` | Information about the page that is not page content. |
| `<meta charset="utf-8">` | Supports a wide range of characters. |
| `<meta name="viewport">` | Helps the page display correctly on mobile devices. |
| `<title>` | Text shown in the browser tab. |
| `<body>` | Visible page content. |

### Elements, tags, and attributes

Most elements have an opening tag, content, and a closing tag:

```html
<p class="intro">Welcome to the class.</p>
```

- `p` is the element name.
- `<p>` and `</p>` are tags.
- `class="intro"` is an attribute.
- `Welcome to the class.` is the content.

Some elements are void elements and do not have closing tags, such as `<img>` and `<br>`.

> **Good habit:** Use lowercase element names, quote attribute values, indent nested elements, and close every element that requires a closing tag.

### Try it

Replace the content in your page with a heading, two paragraphs, and a meaningful page title. Save and refresh the browser.

---

## 2. Text and formatting

### Headings and paragraphs

Use headings in order to create an outline. Use one main `<h1>` for the page topic, followed by `<h2>` and `<h3>` sections.

```html
<h1>Our School Garden</h1>
<h2>Why it matters</h2>
<p>Students grow vegetables and learn about healthy food.</p>
<h2>What we grow</h2>
<p>We grow tomatoes, herbs, and lettuce.</p>
```

Do not choose a heading because it looks large. Use CSS for appearance and headings for structure.

### Text meaning and formatting

### Common formatting tags

| Tag | Use |
| --- | --- |
| `<b>` | Makes text bold visually without adding special importance. |
| `<strong>` | Shows that text is important; it is usually displayed in bold. |
| `<i>` | Displays text in italics for an alternate voice or mood. |
| `<em>` | Emphasizes text; it is usually displayed in italics. |
| `<u>` | Underlines text, but should be used carefully because underlined text can look like a link. |
| `<mark>` | Highlights text as if it were marked with a highlighter. |
| `<small>` | Displays less important text, such as legal notices or side comments, in a smaller size. |
| `<del>` | Shows text that has been deleted or removed, usually with a line through it. |
| `<ins>` | Shows text that has been inserted or added, usually with an underline. |
| `<s>` | Shows text that is no longer accurate or relevant. |
| `<sub>` | Displays subscript text below the normal text line. |
| `<sup>` | Displays superscript text above the normal text line. |
| `<br>` | Inserts a line break. Use it for meaningful line breaks, not page spacing. |
| `<hr>` | Represents a thematic break between sections of content. |

Example:

```html
<p><strong>Important:</strong> Submit your work today.</p>
<p><em>Remember:</em> Save your file regularly.</p>
<p>This is <mark>highlighted</mark> text.</p>
<p>Old price: <del>$20</del> New price: <ins>$15</ins></p>
<p>Water formula: H<sub>2</sub>O</p>
<p>Area: 10 m<sup>2</sup></p>

```html
<p><strong>Important:</strong> Bring a notebook.</p>
<p><em>Optional:</em> Bring gardening gloves.</p>
<p>Water formula: H<sub>2</sub>O</p>
<p>Twenty percent: 20<sup>%</sup></p>
<hr>
<p>Line one<br>Line two</p>
```

Prefer semantic elements such as `<strong>` and `<em>` because they communicate meaning. Avoid using repeated `<br>` elements to create page spacing.

### Comments

Comments are notes for developers and are not displayed:

```html
<!-- Add the timetable after the content is approved. -->
```

### Quotations and code

```html
<blockquote cite="https://example.com/article">
  Learning is a process of making and testing ideas.
</blockquote>
<p>Run <code>npm start</code> in the terminal.</p>
<pre><code>const message = "Hello";</code></pre>
```

### Exercise 1

Create a page titled **About Me**. Include one `<h1>`, at least two `<h2>` headings, three paragraphs, one emphasized phrase, one strong phrase, and a comment for another student.

---

## 3. Links, images, and paths

### Links

Use `<a>` to create a hyperlink:

```html
<a href="https://developer.mozilla.org/">Visit MDN Web Docs</a>
<a href="contact.html">Contact us</a>
<a href="#schedule">Jump to the schedule</a>
```

Use descriptive link text. Avoid vague text such as “click here.” For a new tab, use both `target="_blank"` and `rel="noopener"`:

```html
<a href="https://example.com" target="_blank" rel="noopener">Open the resource</a>
```

### Images

Images require a source and useful alternative text:

```html
<img src="images/campus.jpg" alt="Students walking beside the campus library" width="800" height="450">
```

- `src` is the image path or URL.
- `alt` describes the image for screen readers and when the image cannot load.
- `width` and `height` help the browser reserve space.

Use an empty `alt=""` for a purely decorative image. Never use a file name as meaningful alternative text.

### File paths

```text
website/
├── index.html
├── contact.html
├── css/style.css
└── images/logo.png
```

From `index.html`, use `css/style.css` and `images/logo.png`. From `contact.html` in the same folder, use `index.html` to link back to the home page.

### Exercise 2

Add a logo, a photograph with accurate alternative text, a link to another local page, an external reference, and an in-page link to a section near the bottom of the page.

---

## 4. Lists and tables

### Lists

Use an unordered list when order does not matter and an ordered list when sequence matters:

```html
<h2>Materials</h2>
<ul>
  <li>Notebook</li>
  <li>Pencil</li>
</ul>

<h2>Morning routine</h2>
<ol>
  <li>Check the timetable.</li>
  <li>Pack the materials.</li>
  <li>Join the lesson.</li>
</ol>
```

Nested lists are useful for groups of related items:

```html
<ul>
  <li>Languages
    <ul>
      <li>HTML</li>
      <li>CSS</li>
    </ul>
  </li>
</ul>
```

### Tables

Tables are for data, not page layout. Use a caption and identify header cells:

```html
<table>
  <caption>Class timetable</caption>
  <thead>
    <tr>
      <th scope="col">Day</th>
      <th scope="col">Subject</th>
      <th scope="col">Room</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Monday</th>
      <td>HTML</td>
      <td>101</td>
    </tr>
    <tr>
      <th scope="row">Tuesday</th>
      <td>CSS</td>
      <td>102</td>
    </tr>
  </tbody>
</table>
```

### Exercise 3

Create a list of three learning goals and a table with four lessons. Include a caption, column headings, and row headings.

---

## 5. Grouping and page structure

### Block and inline elements

Block elements normally begin on a new line, while inline elements occupy only the space they need. Use elements according to their meaning, not their default appearance.

`<div>` and `<span>` are generic containers. Use them when no more meaningful element fits:

```html
<div class="notice">
  <p>This is a grouped notice.</p>
</div>
<p>Learn <span class="keyword">HTML</span> step by step.</p>
```

### Semantic layout

Semantic elements make the purpose of page regions clear:

```html
<header>
  <h1>Student Journal</h1>
  <nav aria-label="Main navigation">
    <a href="index.html">Home</a>
    <a href="about.html">About</a>
  </nav>
</header>

<main>
  <article>
    <h2>My first project</h2>
    <p>The project details go here.</p>
  </article>
  <aside>
    <h2>Related links</h2>
  </aside>
</main>

<footer><p>© 2025 Student Journal</p></footer>
```

Common semantic elements include `header`, `nav`, `main`, `section`, `article`, `aside`, and `footer`. A page should have one `main` element and should not place a `main` inside another `main`.

### Classes and IDs

Use `class` for a reusable group and `id` for one unique element:

```html
<section id="schedule" class="card">
  <h2>Schedule</h2>
</section>
```

An `id` can be used as a fragment link (`href="#schedule"`). Keep names meaningful and avoid spaces.

### Iframes

An iframe embeds another document. Include a title and use it only when embedding is necessary:

```html
<iframe
  src="https://www.example.com"
  title="Example information page"
  width="600"
  height="400">
</iframe>
```

---

## 6. CSS and JavaScript

HTML provides structure. CSS controls presentation, and JavaScript adds behavior.

### Add CSS

External CSS is usually easiest to maintain:

```html
<head>
  <link rel="stylesheet" href="css/style.css">
</head>
```

```css
body {
  font-family: system-ui, sans-serif;
  line-height: 1.6;
  margin: 2rem;
}

.card {
  border: 1px solid #cccccc;
  padding: 1rem;
}
```

You can also use an internal `<style>` element for a small experiment. Avoid inline styles in larger projects.

### Add JavaScript

```html
<button type="button" id="helloButton">Say hello</button>
<script src="js/app.js" defer></script>
```

```javascript
const button = document.querySelector('#helloButton');
button.addEventListener('click', () => {
  alert('Hello, student!');
});
```

The `defer` attribute lets the document load before the script runs.

---

## 7. The document head and metadata

The `<head>` can include the title, character set, viewport settings, stylesheets, icons, descriptions, and other metadata:

```html
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="description" content="A student guide to learning HTML.">
  <title>HTML Student Guide</title>
  <link rel="icon" href="images/favicon.png">
  <link rel="stylesheet" href="css/style.css">
</head>
```

The description can help search engines and users understand the page. The title should be specific and different for each important page.

---

## 8. Forms and user input

Forms collect information. Every control should have a label, and the form should identify its purpose:

```html
<form action="/signup" method="post">
  <fieldset>
    <legend>Newsletter sign-up</legend>

    <label for="email">Email address</label>
    <input type="email" id="email" name="email" required>

    <label for="topic">Favorite topic</label>
    <select id="topic" name="topic">
      <option value="html">HTML</option>
      <option value="css">CSS</option>
    </select>

    <label for="message">Message</label>
    <textarea id="message" name="message" rows="4"></textarea>

    <button type="submit">Subscribe</button>
  </fieldset>
</form>
```

Important form ideas:

- `action` identifies where submitted data goes.
- `method="get"` commonly sends data in the URL; `method="post"` sends it in the request body.
- `name` identifies submitted values.
- `required`, `type="email"`, `min`, `max`, and `pattern` provide browser validation.
- A server must still validate and safely process all submitted data.

### Exercise 4

Build a feedback form with a name, email, topic selection, message, and submit button. Test it with an empty required field and an invalid email address.

---

## 9. Media and responsive content

### Audio and video

```html
<video controls width="640" poster="images/preview.jpg">
  <source src="media/lesson.mp4" type="video/mp4">
  Your browser does not support the video element.
</video>
```

Provide captions for video when possible and do not autoplay media with sound. For images that need different sizes, use `picture`:

```html
<picture>
  <source media="(min-width: 800px)" srcset="images/large.jpg">
  <img src="images/small.jpg" alt="A quiet reading room">
</picture>
```

Responsive behavior is mainly implemented with CSS, but good HTML helps: include the viewport metadata, use meaningful structure, and provide flexible media alternatives.

---

## 10. Entities, symbols, and character encoding

Reserved characters must be written as entities:

```html
<p>Use &lt;h1&gt; for a main heading.</p>
<p>Our company&nbsp;name stays together.</p>
<p>Copyright &copy; 2025</p>
```

Always use UTF-8 with `<meta charset="utf-8">` so that common symbols and international text display correctly.

---

## 11. Accessibility and HTML style guide

Use this checklist before sharing a page:

- [ ] The document begins with `<!doctype html>`.
- [ ] The page has a descriptive `<title>`.
- [ ] The language is declared on `<html>`.
- [ ] Headings describe a logical outline.
- [ ] Images have useful `alt` text.
- [ ] Form controls have associated labels.
- [ ] Links describe their destination.
- [ ] Buttons are used for actions and links for navigation.
- [ ] Tables have captions and header cells.
- [ ] Colors are not the only way information is communicated.
- [ ] HTML has been checked with a validator and tested at different sizes.

Keep indentation consistent, use quotes around attribute values, avoid obsolete tags, and prefer semantic HTML over unnecessary `div` elements. Validate your pages at [validator.w3.org](https://validator.w3.org/).

---

## Final project: Student resource website

Create a three-page website about a subject you enjoy:

1. `index.html` — introduction and navigation.
2. `topics.html` — headings, paragraphs, images, lists, and a table.
3. `contact.html` — an accessible feedback form.

Requirements:

- Use the complete HTML document structure on every page.
- Link all pages together with a navigation area.
- Use at least five semantic elements.
- Add external CSS and one small JavaScript interaction.
- Include meaningful image alternative text and form labels.
- Test keyboard navigation, mobile layout, links, and validation.

### Suggested marking guide

| Area | Points |
| --- | ---: |
| Structure and valid HTML | 20 |
| Content and semantic elements | 20 |
| Links, images, lists, and table | 20 |
| Accessibility and responsive preparation | 20 |
| CSS/JavaScript integration | 10 |
| Organization and code style | 10 |
| **Total** | **100** |

## Quick reference

| Task | Element or attribute |
| --- | --- |
| Main heading | `<h1>` |
| Paragraph | `<p>` |
| Link | `<a href="...">` |
| Image | `<img src="..." alt="...">` |
| Unordered list | `<ul>` and `<li>` |
| Ordered list | `<ol>` and `<li>` |
| Table heading | `<th>` |
| Form label | `<label for="...">` |
| Text input | `<input>` |
| Button | `<button type="button">` |
| Page navigation | `<nav>` |
| Main content | `<main>` |
| Section | `<section>` |
| External CSS | `<link rel="stylesheet">` |
| External JavaScript | `<script src="..." defer>` |

## Continue learning

After completing this guide, continue with CSS for layout and visual design, JavaScript for interaction, and web accessibility for inclusive experiences. Read documentation, inspect real websites, and keep building small projects.
