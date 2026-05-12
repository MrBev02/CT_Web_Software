---
title: Lesson 3 — Build Your Landing Page
---

# Lesson 3: Build Your Landing Page

Today you'll build a multi-page website with a flexbox navigation bar. The fundamentals you learn here give you the skills to direct AI, recognise good code, and ask for what you want.

- [Flexbox slides](slides/index.html)

> ⚠️ **You are NOT building the website you designed last assessment.**
> Your job today is to **reproduce the wireframe below** — same sections, same layout, same order. The wireframe is the spec. Don't add sections it doesn't have, don't skip sections it does have, don't rearrange them. You can pick your own words for headings and copy, but the structure must match.

![wireframe](wireframe.svg)

## What you're given

- [starter/index.html](https://github.com/MrBev02/CT_Web_Software/blob/main/lesson-3/starter/index.html) — your landing page. Has short signpost comments showing where each section goes. **All the build instructions are on this page (below).** The starter HTML just tells you *where* — this page tells you *what*.
- [starter/about.html](https://github.com/MrBev02/CT_Web_Software/blob/main/lesson-3/starter/about.html) and [starter/gallery.html](https://github.com/MrBev02/CT_Web_Software/blob/main/lesson-3/starter/gallery.html) — already built. The nav is in place. You just need to make sure the links to/from them work.
- [starter/styles.css](https://github.com/MrBev02/CT_Web_Software/blob/main/lesson-3/starter/styles.css) — has the basics. You'll add the nav and section styles.
- [demo/flexbox-playground.html](demo/flexbox-playground.html) — your sandbox. Use it whenever you're not sure what a flexbox property does.
- [reference/flexbox.md](reference/flexbox.md) — the cheat sheet. Read it when you get stuck.

## Why we're hand-coding today

In the coming weeks you will use AI to build the bulk of your assessment site. Today's lesson gives you the knowledge to read what the AI writes, judge whether it's any good, and tell it what to change.

---

## Task order — do these in sequence

### ✅ Task 1 — Build the nav HTML *(about 5 min)*

Open `starter/index.html`. Find the `<!-- NAV -->` signpost near the top.

Add a `<nav class="main-nav">`. Inside it, add **two things**:

1. A brand link on the left: `<a href="index.html" class="brand">Brand</a>`
2. A wrapper `<div class="nav-links">` containing five `<a>` tags:
    - Home → `index.html` (give this one `class="active"`)
    - About → `about.html`
    - Gallery → `gallery.html`
    - Blog → `#`
    - Contact → `#`

Your finished structure should look like:

```
nav.main-nav
  ├── a.brand
  └── div.nav-links
        ├── a (Home — has class="active")
        ├── a (About)
        ├── a (Gallery)
        ├── a (Blog)
        └── a (Contact)
```

Save and open the page in Live Server. The links will look like a vertical list — that's expected. You'll fix that with CSS next.

### ✅ Task 2 — Make the nav horizontal with flexbox *(about 5 min)*

Open `starter/styles.css`. Find the `.main-nav` rule. Add these four properties:

```css
.main-nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 24px;
}
```

Then do the same for `.nav-links` (it's also a flex container — flexbox inside flexbox is normal):

```css
.nav-links {
  display: flex;
  gap: 20px;
  align-items: center;
}
```

**Check before moving on:** Reload your page. The brand should be on the left, the links should be on the right, and they should all be on the same horizontal line. If not, check the cheat sheet's "Common things that break" section.

### ✅ Task 3 — Make the nav links look like buttons *(about 5 min)*

Look at the wireframe nav again: the links aren't plain blue underlined text — they're **button-shaped**. Home is a solid dark filled button (because we're on the home page); the other four are outlined boxes.

Add this to `styles.css`:

```css
.main-nav a {
  display: inline-block;
  padding: 6px 14px;
  border: 1px solid #666;
  border-radius: 4px;
  text-decoration: none;
  color: #222;
}

.main-nav a.active {
  background: #222;
  color: white;
  border-color: #222;
}

.main-nav .brand {
  border-style: dashed;
}
```

**What each bit does:**

- `padding` gives the link some room inside its border, so it looks like a clickable rectangle instead of a tight box around the text
- `border` + `border-radius` is what gives it the button shape
- `text-decoration: none` removes the blue underline that links have by default
- `.active` paints the *current page's* link solid dark (that's why we gave Home `class="active"` back in Task 1)
- `.brand` gets a dashed border to mark it as the logo placeholder, matching the wireframe

Reload. Home should be a solid dark button, the rest should be outlined boxes.

### ✅ Task 4 — Test the page-to-page links *(about 2 min)*

Click your "About" link. You should land on `about.html`. From there, click "Home" — you should come back. Click "Gallery" from About — you should land on the gallery page. Click "← Back to home" — back to index.

If any of these fail, the most likely cause is a typo in your href (e.g., `about.htm` instead of `about.html`).

### ✅ Task 5 — Hero section *(about 3 min)*

Find the `<!-- HERO -->` signpost in `index.html`. The `<section class="hero">` is already there — you just fill it in.

Inside the hero, add:

- an `<h1>` with the big headline (look at the wireframe for what kind of text fits)
- a `<p>` with the tagline / one-line description
- a call-to-action link: `<a href="#" class="cta-button">Call to Action</a>`

Finished structure:

```
section.hero
  ├── h1
  ├── p
  └── a.cta-button
```

### ✅ Task 6 — Cards section *(about 5 min)*

Find the `<!-- CARDS -->` signpost. The `<section class="cards">` is already there — **this is your flex container**, same pattern as the nav.

Inside the cards container, add **three** `<article class="card">` elements. Inside each card, add:

- `<div class="card-image"></div>` (empty for now — it'll show as a coloured box)
- `<h3>Card title</h3>`
- `<p>Short description</p>`

Finished structure:

```
section.cards
  ├── article.card
  │     ├── div.card-image
  │     ├── h3
  │     └── p
  ├── article.card  (same contents)
  └── article.card  (same contents)
```

Now make the cards sit in a row. In `styles.css`:

```css
.cards {
  display: flex;
  gap: 24px;
}
.card {
  flex: 1;
}
```

`flex: 1` on each card makes them share the available space equally. Try removing it and see what happens.

### ✅ Task 7 — About preview *(about 2 min)* — if time

Find the `<!-- ABOUT PREVIEW -->` signpost. Inside `<section class="about-preview">`, add:

- an `<h2>` heading (e.g. "About us")
- a `<p>` with a short paragraph
- a link to the about page: `<a href="about.html">Read more →</a>`

Finished structure:

```
section.about-preview
  ├── h2
  ├── p
  └── a (link to about.html)
```

### ✅ Task 8 — Footer *(about 3 min)* — if time

Find the `<!-- FOOTER -->` signpost. The footer is **also a flex container** — same pattern as the nav.

Inside `<footer class="site-footer">`, add:

- `<p>© 2026 Your Site</p>` for copyright
- A wrapper `<div class="footer-links">` containing two `<a>` tags (e.g. About and Gallery)

Finished structure:

```
footer.site-footer
  ├── p (copyright)
  └── div.footer-links
        ├── a (About)
        └── a (Gallery)
```

You won't necessarily finish every task in this lesson — that's fine. **Aim for at minimum:** Tasks 1–5 done (nav working and looking like buttons, hero filled in). Tasks 6–8 are the stretch.

---

## Self-check before calling the teacher over

Before you ask for help, work through this list:

- [ ] All three pages open in the browser without errors
- [ ] The nav appears horizontally (not vertically) on `index.html`
- [ ] The nav links look like buttons (Home is solid dark, the others are outlined)
- [ ] Clicking each nav link goes to the right page (or stays on `#`)
- [ ] You can explain what each of `display: flex`, `justify-content`, and `align-items` is doing on your nav

If something's broken and the cheat sheet hasn't helped, *then* call the teacher.

---

## End-of-lesson check

Before you pack up, your teacher will check:

1. You have three working files (`index.html`, `about.html`, `gallery.html`).
2. The nav lays out horizontally and clicking links navigates between pages.
3. Your landing page is in progress — the nav is done and you've started on the hero or cards.
4. **What you've built matches the wireframe** — same sections in the same order.

You'll also be asked to **point at one line of CSS and explain what it's doing**. Be ready.

---

## Done early? Pick one of these.

### Option A — Polish your nav with hover states

Your buttons work, but they don't react when you mouse over them. Add this to `styles.css`:

```css
.main-nav a {
  transition: background 0.2s, color 0.2s, border-color 0.2s;
}
.main-nav a:hover {
  background: #f4a72a;
  border-color: #f4a72a;
  color: white;
}
.main-nav a.active:hover {
  background: #222;
  border-color: #222;
}
```

Reload and mouse over the links. The non-active ones should fill orange on hover; the active Home button shouldn't change (it's already the current page).

Then explore `flex-grow` and `flex-shrink` in the playground demo. Try giving one of the nav links `flex-grow: 1` — what happens? Why?

### Option B — Recreate the wireframe with AI, then compare

Open the wireframe. Prompt an AI assistant to build it (be specific: "build a landing page in HTML and CSS that matches this wireframe — it has a nav with a brand on the left and five links on the right, a centred hero with a heading and CTA button, three cards in a row, an about section, and a footer").

Compare what the AI produced to what you built by hand:

- Did it use flexbox? Where?
- What did it call its CSS classes? Are they similar to yours?
- What's *better* about the AI's version? What's *worse*?

Bring your comparison to next lesson — we'll talk about it.
