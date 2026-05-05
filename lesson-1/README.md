# Lesson 1 — Introduction to HTML

The catch-up page. If you missed the lesson, were lost in class, or want to refresh before working on your Figma site, start here.

## What this lesson covered

By the end of the lesson you should be able to:

- Explain what HTML is and what the browser does with it
- Recognise common HTML tags — `<h1>`, `<p>`, `<ul>`/`<li>`, `<a>`, `<img>` — and pick the right one for the job
- Write a valid HTML page yourself, save it, and view it in a browser

## See it running

The actual files we used in class. Click to view them rendered:

- **[skeleton.html](https://mrbev02.github.io/CT_Web_Software/lesson-1/demo/skeleton.html)** — the empty starting point. The DOCTYPE and skeleton tags are there; you fill in the body.
- **[example-complete.html](https://mrbev02.github.io/CT_Web_Software/lesson-1/demo/example-complete.html)** — the finished version of what we built together.
- **[scaffold.html](https://mrbev02.github.io/CT_Web_Software/lesson-1/demo/scaffold.html)** — same skeleton but with comments showing where each tag goes. Start here if you're stuck.

And the closing demo — same content, once without CSS and once with CSS:

- **[before.html](https://mrbev02.github.io/CT_Web_Software/lesson-1/demo/example-complete.html)** — pure HTML, no styling.
- **[after.html](https://mrbev02.github.io/CT_Web_Software/lesson-1/css-preview/after.html)** — same page, with CSS added.

That's the preview of Lesson 2.

## What we built — walkthrough

Open `skeleton.html` in VS Code. The structure is already there:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>About Coffee</title>
</head>
<body>
    <!-- Live-coding starts here -->

</body>
</html>
```

You're going to fill in the `<body>`. Save after each step, then refresh your browser to see what changed.

### 1. Add a heading

Inside the body, type:

```html
<h1>About Coffee</h1>
```

**What to notice:** the text appears, big and bold. You didn't tell the browser what size or weight to use — `<h1>` *means* "biggest heading", and the browser already knows what that should look like.

### 2. Add a paragraph

Below the heading:

```html
<p>Coffee is a brewed drink made from roasted beans of the Coffea plant.</p>
```

**What to notice:** the closing `</p>`. Without it, the browser would keep treating the rest of the page as part of the paragraph. Most tags come in pairs — opener and closer.

### 3. Add a sub-heading and a list

```html
<h2>Common Brewing Methods</h2>

<ul>
    <li>Espresso</li>
    <li>French press</li>
    <li>Pour over</li>
</ul>
```

**What to notice:** `<li>` tags are *inside* `<ul>`. This is **nesting** — tags wrapping other tags. Indent the inner tags so you can see at a glance what's nested inside what.

### 4. Add a link (your first attribute)

```html
<p><a href="https://en.wikipedia.org/wiki/Coffee">Read more on Wikipedia</a></p>
```

**What to notice:** `href="..."` is an **attribute** — extra info on a tag, written *inside* the opening tag. The text between `<a>` and `</a>` is what the user sees and clicks; the `href` is where the click takes them.

### 5. Add an image

```html
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/45/A_small_cup_of_coffee.JPG/640px-A_small_cup_of_coffee.JPG" alt="A small white cup of black coffee on a saucer">
```

**What to notice:** two new things here.

- `<img>` is **self-closing** — no `</img>`. Some tags have no content, so they don't need a closer.
- The `alt` attribute describes the image for screen readers and for when images fail to load. **Not optional.** Always write meaningful alt text.

### 6. Save and reload

You should now have a page with a heading, a paragraph, a sub-heading, a list, a link, and an image. Compare it with `example-complete.html`.

That's it — you've written a webpage.

## Try it yourself

Pick something you actually care about — a hobby, a sport, a band, a game, a place. **Not your Figma assessment topic.** This is throwaway practice; you want to make all your mistakes here, not in your real project.

Create a new file, save it as `mypage.html`, and build a page with all of these:

- [ ] One `<h1>` with the page title
- [ ] At least two `<h2>` sub-headings
- [ ] At least three `<p>` paragraphs
- [ ] One `<ul>` with at least three `<li>` items
- [ ] One `<a>` link to a real website
- [ ] One `<img>` with both `src` and `alt` attributes — try `https://placehold.co/400x300` if you need a placeholder image

### Stretch goals

If you finish, push further:

1. **Add semantic structure.** Wrap your content in proper structural tags:
   ```html
   <header>...</header>
   <nav>...</nav>
   <main>
       <section>...</section>
       <section>...</section>
   </main>
   <footer>...</footer>
   ```
2. Add a second image with a different shape or aspect ratio.
3. Add an ordered list (`<ol>`) — for a top-5, a ranking, or a sequence of steps.
4. Open your Figma design. On paper, sketch which Figma sections will become which HTML tags. Don't write the HTML yet — just plan.

## Things that will trip you up

- **Forgot the closing tag.** Every opener needs a closer (except `<img>`, `<br>`, `<hr>`, which are self-closing).
- **Saved as `.txt` instead of `.html`.** The browser won't render it. Check the file extension.
- **Image not loading.** Paste the `src` URL into your browser address bar — does the image appear there? If not, the URL is wrong.
- **Page didn't update.** Did you save the file? Did you refresh the browser? If you're using Live Server, give it a second.
- **Content in the wrong place.** Visible content goes in `<body>`. The `<head>` is for info *about* the page (the title, the language, links to stylesheets) — not for content the user reads.

## What's next

Lesson 2 is CSS — the language that makes the page actually look like something.

Open these two side by side:

- [before.html](https://mrbev02.github.io/CT_Web_Software/lesson-1/css-preview/before.html) — pure HTML, no styling
- [after.html](https://mrbev02.github.io/CT_Web_Software/lesson-1/css-preview/after.html) — same HTML, with CSS added

Both files contain the exact same body content. The only meaningful difference is one extra line in the `<head>` linking a stylesheet. Tomorrow we write that stylesheet — and after that, your Figma design becomes a real website.

## Reference

- **[Tag cheatsheet](../reference/html_tags.md)** — every tag we used today, with examples
- A styled version of the cheatsheet is also on the Canvas course page