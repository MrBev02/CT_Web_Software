# CSS Glossary

Quick reference for the words your teacher will use. Plain English where possible.

## Anatomy of a CSS rule

```
selector {
  property: value;
}
```

A real example:

```css
h1 {
  color: blue;
}
```

| Part | What it is |
|------|------------|
| `h1` | The **selector** — what to style |
| `color: blue;` | A **declaration** |
| `color` | The **property** — what aspect to change |
| `blue` | The **value** — what to change it to |
| The whole thing | A **rule** (selector + declarations) |

A stylesheet is just a list of rules.

## Selector types

| Selector | Symbol | Targets | Example |
|----------|--------|---------|---------|
| Element | (no symbol) | All elements of that type | `p { ... }` styles every `<p>` |
| Class | `.` (dot) | Elements with that class | `.note { ... }` styles `<p class="note">` |
| ID | `#` (hash) | The one element with that ID | `#header { ... }` styles `<div id="header">` |

**When to use which:**

- **Element** when you want the same style on *all* elements of that type
- **Class** when you want the same style on *several* specific elements (reusable)
- **ID** when you have one unique element on the page (rare in practice)

## Box model

Every element on a page is a rectangle with four parts:

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

| Part | Meaning |
|------|---------|
| **margin** | Pushes other elements *away* from this one |
| **border** | A visible line around the element |
| **padding** | Pushes content *inward* from the border |
| **content** | The actual text or image inside |

Memory hook: **m**argin pushes neighbours away. **p**adding pushes content in.

## Other terms you'll hear

| Term | Meaning |
|------|---------|
| **Cascade** | When two rules conflict, CSS has a system to decide which wins. |
| **Specificity** | More specific selectors beat less specific ones. ID beats class beats element. |
| **Inherit** | Some properties (like colour, font) automatically pass down from parent to child. |
| **External stylesheet** | A separate `.css` file linked from HTML. The professional way. |
| **Inline style** | CSS written directly on an HTML element using `style="..."`. Avoid this. |
| **Live Server** | The VS Code extension that auto-refreshes your browser when you save. |

## Property name translations

CSS uses English (American) words. Some can be confusing:

| CSS property | What it really means |
|--------------|----------------------|
| `color` | Colour of the **text** (not the background) |
| `background` | The colour or image **behind** the element |
| `font-family` | The **typeface** — the style of the letters |
| `font-size` | How big the letters are |
| `font-weight` | How thick the letters are (bold or thin) |
| `margin` | **Outside** spacing — pushes other things away |
| `padding` | **Inside** spacing — gives content room |
| `border` | The **line** around an element |
| `width` / `height` | How wide / tall the element is |
| `text-align` | Where the text sits (left, centre, right) |

## Two spelling traps

1. **`color`** — not `colour`. CSS uses American spelling. The word `colour` will not work.
2. **CSS is case-sensitive for class and ID names.** `.menu` and `.Menu` are two different things. If your HTML says `class="Menu"`, your CSS must say `.Menu` too.

## VS Code tip

If you're not sure what a property does, **hover over the property name** in VS Code. A pop-up will show the description. This works for any CSS property.

## Looking up properties

The most reliable reference is MDN: [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)

Search for the property name (e.g. "MDN border-radius") and you'll get an explanation, examples, and which browsers support it.
