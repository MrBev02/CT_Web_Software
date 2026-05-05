# HTML Tag Cheatsheet

A quick reference for the tags you'll use today. Print and keep nearby.

---

## How a tag works

```
   opening tag      content       closing tag
       ↓               ↓               ↓
     <h1>     My page title       </h1>
```

```
   opening tag with attribute               closing tag
              ↓                                  ↓
     <a href="https://google.com">  Google   </a>
                  ↑
              attribute (extra info)
```

**Rules:**
- Most tags come in pairs: opening `<tag>` and closing `</tag>` (note the slash).
- Attributes go *inside the opening tag*, in the format `name="value"`.
- Tags can contain other tags (nesting). Close in reverse order.

---

## The document skeleton

Every HTML page has this shape:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Page title (shows in browser tab)</title>
</head>
<body>

    <!-- Everything the user actually sees goes here -->

</body>
</html>
```

| Part | Purpose |
|---|---|
| `<!DOCTYPE html>` | Tells the browser "this is HTML5". Always the first line. |
| `<html>` | Wraps the whole document. |
| `<head>` | Information *about* the page. Not visible on the page itself. |
| `<title>` | Page name. Shows in the browser tab and bookmarks. |
| `<body>` | Everything visible to the user. |

---

## Headings — `<h1>` to `<h6>`

```html
<h1>Biggest heading — most important</h1>
<h2>Sub-heading</h2>
<h3>Sub-sub-heading</h3>
```

**Use one `<h1>` per page** (like a chapter title). Use `<h2>` and `<h3>` for sections within. Levels 4–6 exist but you'll rarely need them.

---

## Paragraph — `<p>`

```html
<p>This is a paragraph. The browser adds spacing automatically.</p>
```

For blocks of running text. Don't use `<p>` for a single word or for layout — use it for actual sentences.

---

## Lists — `<ul>` and `<li>`

**Unordered list** (bullets):
```html
<ul>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ul>
```

**Ordered list** (numbers) — same idea, just `<ol>` instead of `<ul>`:
```html
<ol>
    <li>Step one</li>
    <li>Step two</li>
</ol>
```

`<li>` items must always sit *inside* a `<ul>` or `<ol>`, never on their own.

---

## Link — `<a>`

```html
<a href="https://developer.mozilla.org">Visit MDN</a>
```

| Part | What it is |
|---|---|
| `<a>` | Anchor — the link element |
| `href="..."` | Where the link goes (the URL) |
| `Visit MDN` | The text the user sees and clicks |

The `href` is required. Without it, you have a non-link.

---

## Image — `<img>`

```html
<img src="photo.jpg" alt="A photo of a sunset">
```

Self-closing — no closing tag needed.

| Attribute | What it is | Required? |
|---|---|---|
| `src` | Where the image lives (URL or filename) | Yes |
| `alt` | Description of the image for screen readers / when image fails to load | **Yes — accessibility** |

> ⚠️ **`alt` is not optional.** Without it, blind users can't experience your page, and you'll lose marks.

---

## Semantic structure tags (for the stretch task)

These don't change how the page *looks*, but they describe *what each section is for*. Useful for accessibility, SEO, and making CSS easier next lesson.

```html
<header>  <!-- Top of page: site name, navigation -->
<nav>     <!-- A navigation menu -->
<main>    <!-- The main content of the page -->
<section> <!-- A logical section of content -->
<article> <!-- A self-contained piece of content -->
<footer>  <!-- Bottom of page: copyright, links -->
```

---

## Common mistakes to avoid

| Mistake | What goes wrong | Fix |
|---|---|---|
| `<p>Hello` (no closing tag) | Browser may keep treating later text as part of the paragraph | Always close: `<p>Hello</p>` |
| `<li>Item</li>` floating outside a `<ul>` | List item with no list — invalid | Wrap in `<ul>...</ul>` |
| `<a>Click here</a>` (no href) | Not actually a link — nothing happens | Add `href="..."` |
| `<img src="photo.jpg">` (no alt) | Screen readers can't read it; fails accessibility | Add `alt="description"` |
| `<H1>...` uppercase | Works but is non-standard | Always use lowercase: `<h1>` |
| Wrong nesting order: `<p><strong>hi</p></strong>` | Closing in wrong order — invalid | Match the order: `<p><strong>hi</strong></p>` |

---

## The three things you must remember

1. **Every opening tag needs a closing tag** (with a few exceptions like `<img>` and `<br>`).
2. **Attributes go inside the opening tag**, in `name="value"` form.
3. **Save the file before checking the browser.** Live Server only reloads on save.