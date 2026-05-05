# Lesson 2: CSS Basics — Walkthrough

> Use this page to follow along during class, or to catch up if you fell behind during the demo.
> The walkthrough at the bottom takes you through exactly what we built on the projector.

## Contents

- [What is CSS?](#what-is-css)
- [Linking a stylesheet](#linking-a-stylesheet)
- [Selectors — three kinds](#selectors--three-kinds)
- [The box model](#the-box-model)
- [Colour and font properties](#colour-and-font-properties)
- [Demo walkthrough — transform a page in five steps](#demo-walkthrough--transform-a-page-in-five-steps)
- [Common mistakes](#common-mistakes)
- [Where to go next](#where-to-go-next)

---

## What is CSS?

HTML describes **what is on the page** (headings, paragraphs, lists, images). CSS describes **how it looks** (colours, fonts, spacing, layout).

Keeping these in two separate files is called **separating content from presentation**. It means you can change the look of a whole site by editing one CSS file, without touching any of the HTML.

## Linking a stylesheet

HTML and CSS live in two separate files. The browser loads both. To connect them, add a `<link>` tag inside the `<head>` of your HTML:

```html
<head>
  <link rel="stylesheet" href="styles.css">
</head>
```

Your folder should look like this:

```
my-page/
├── index.html
└── styles.css
```

The `href` value must match your CSS filename exactly. **Capital letters matter.** `Styles.css` and `styles.css` are not the same file.

## Selectors — three kinds

A **selector** is the part of a CSS rule that says *which elements to style*. There are three kinds you need to know today:

| Selector | Symbol | Targets | Example |
|----------|--------|---------|---------|
| Element | (none) | All elements of that type | `p { ... }` styles every `<p>` |
| Class | `.` (dot) | Elements with that class | `.note { ... }` styles `<p class="note">` |
| ID | `#` (hash) | The one element with that ID | `#header { ... }` styles `<div id="header">` |

**When to use which:**

- **Element** — when you want the same style on *every* tag of that type
- **Class** — when you want the same style on *several* specific elements (reusable)
- **ID** — when there's only ever *one* element of its kind on the page

## The box model

Every element on a web page is a rectangle with four parts. Understanding these is the key to controlling spacing.

```
┌──────────────────────────────┐
│         margin               │   space OUTSIDE the border
│  ┌────────────────────────┐  │
│  │       border           │  │   visible line
│  │  ┌──────────────────┐  │  │
│  │  │     padding      │  │  │   space INSIDE the border
│  │  │  ┌────────────┐  │  │  │
│  │  │  │  content   │  │  │  │   the text or image
│  │  │  └────────────┘  │  │  │
│  │  └──────────────────┘  │  │
│  └────────────────────────┘  │
└──────────────────────────────┘
```

| Part | What it does |
|------|--------------|
| **margin** | Pushes other elements *away* from this one |
| **border** | A visible line around the element |
| **padding** | Pushes content *inward* from the border |
| **content** | The actual text or image inside |

**Memory hook:** **m**argin pushes neighbours away. **p**adding pushes content in.

## Colour and font properties

```css
color: #1a4d8c;                       /* TEXT colour */
background: #f5f7fa;                  /* BEHIND the element */
font-family: system-ui, sans-serif;   /* the typeface */
font-size: 1.2rem;                    /* how big */
```

> ⚠ **Spelling trap:** CSS uses American spelling. The property is `color`, not `colour`. If you write `colour`, the rule will silently do nothing.

For palette ideas and accessibility-checked colour combinations, see the [Colours reference](../03-snippet-patterns/colours.md).

---

## Demo walkthrough — transform a page in five steps

This is what we did on the projector. If you got lost, work through it yourself now.

### Get the starting HTML

Either use a fresh copy of your L1 HTML, or grab the starter file from this folder: [`live-demo/index.html`](live-demo/index.html). It looks like this:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>About Me</title>
</head>
<body>
  <h1>About Me</h1>
  <p>Hi, I'm Alex. Welcome to my page.</p>

  <h2>What I Like</h2>
  <ul>
    <li>Music</li>
    <li>Soccer</li>
    <li>Cats</li>
  </ul>

  <h2>About This Page</h2>
  <p class="note">This page is part of my Computing Technology project.</p>
</body>
</html>
```

Create a new file called `styles.css` in the same folder. **Save after each step** and watch the page change in Live Server.

### Step 0 — Link the stylesheet

In your HTML `<head>`, add:

```html
<link rel="stylesheet" href="styles.css">
```

Save and refresh. Nothing visible changes — that's correct. The connection is made, but no rules exist yet.

### Step 1 — Body typography

```css
body {
  font-family: system-ui, sans-serif;
  line-height: 1.6;
}
```

The whole page now uses the system font and has more breathing room between lines.

### Step 2 — Heading colour

```css
h1 {
  color: #1a4d8c;
}
```

The element selector `h1` turns every `<h1>` heading navy.

### Step 3 — Class selector and box model

```css
.note {
  background: #fff3cd;
  padding: 1rem;
  border-left: 4px solid #ffc107;
}
```

This styles only the paragraph with `class="note"`. Padding gives the text room. The border on the left makes it look like a call-out box.

### Step 4 — Page layout (extend the body rule)

Replace your `body` rule with this expanded version:

```css
body {
  font-family: system-ui, sans-serif;
  line-height: 1.6;
  max-width: 600px;
  margin: 2rem auto;
  padding: 1rem;
}
```

`margin: 2rem auto` — the `auto` on the sides centres the page in the browser window.

### Step 5 — Polish the list

```css
li {
  margin-bottom: 0.5rem;
}
```

Now the list breathes — each item has a bit of space below it.

### Final stylesheet

If you've followed every step, your `styles.css` should look like this:

```css
body {
  font-family: system-ui, sans-serif;
  line-height: 1.6;
  max-width: 600px;
  margin: 2rem auto;
  padding: 1rem;
}

h1 {
  color: #1a4d8c;
}

.note {
  background: #fff3cd;
  padding: 1rem;
  border-left: 4px solid #ffc107;
}

li {
  margin-bottom: 0.5rem;
}
```

Five rules. That's the whole demo.

---

## Common mistakes

If your CSS doesn't seem to be doing anything, check these in order:

1. **Is the file saved?** Live Server only updates on save. `Ctrl + S` (or `Cmd + S`).
2. **Is the `<link>` tag in the `<head>`?** Not in the body. And the filename must match exactly — case-sensitive.
3. **Are you in the right folder?** `index.html` and `styles.css` need to be in the same folder, or the `href` path needs to point to wherever the CSS lives.
4. **Is the selector spelled correctly?** `.menu` and `.Menu` are two different things. Whatever your HTML says, your CSS must match.
5. **Is `color` spelled the American way?** `colour` doesn't work in CSS.
6. **Did you forget a semicolon?** A missing `;` will silently break the *next* rule.

If you've checked all six and it's still not working, ask a neighbour to read your CSS aloud — they'll spot the typo faster than you will.

---

## Where to go next

- **[CSS Glossary](../03-snippet-patterns/glossary.md)** — definitions of every CSS word your teacher used today.
- **[Colours reference](../03-snippet-patterns/colours.md)** — palettes, contrast checking, and how to apply colour without making a page hard to read.
- **[Typography patterns](../03-snippet-patterns/typography.css)** — copy-paste-ready rules for fonts, sizes, line heights.
- **[Starter file](starter.css)** — a stylesheet with one rule pre-written, plus three "now you try" prompts. Good if you're not sure where to begin.
