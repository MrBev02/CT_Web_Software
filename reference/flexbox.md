---
title: Flexbox — quick reference
---

# Flexbox

Use this when you need to lay out elements in a row or column with control over spacing and alignment. Most navigation bars, card rows, and form layouts are flexbox.

---

## The mental model

Flexbox has **two parts**: a **container** (the parent) and the **items** inside it.

You apply `display: flex` to the **container**. The items inside then arrange according to the rules you set on the container.

```
                        main axis  ──────────────►

                ┌────────────────────────────────────┐
                │  ┌──────┐    ┌──────┐    ┌──────┐  │   ▲
 container ──►  │  │ item │    │ item │    │ item │  │   │ cross
                │  │  1   │    │  2   │    │  3   │  │   │ axis
                │  └──────┘    └──────┘    └──────┘  │   ▼
                └────────────────────────────────────┘
```

When `flex-direction: row` (the default), the main axis runs **left → right** and the cross axis runs **top → bottom**.

When you change to `flex-direction: column`, those axes **swap**. This is the single most important thing to remember about flexbox: the meaning of "main" and "cross" depends on the direction.

---

## The four properties you need

All four go on the **container**, not the items.

| Property | What it does |
|---|---|
| `display: flex` | Turns flexbox on. Without this, none of the others do anything. |
| `flex-direction: row \| column` | Sets which way the items flow. `row` is the default. |
| `justify-content: ...` | Spaces items along the **main** axis. Use `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `space-evenly`. |
| `align-items: ...` | Aligns items along the **cross** axis. Use `flex-start`, `flex-end`, `center`, `stretch`. |
| `gap: 16px` | Space between items. Works for both axes. |

A typical horizontal navigation bar uses all of these:

```css
.main-nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 24px;
}
```

---

## Common things that break

When your flexbox isn't doing what you expect, check these in order:

**1. "Nothing is laying out horizontally."**
You forgot `display: flex` on the container. Or you put it on the wrong element — flexbox affects the **direct children** of the element you put it on.

**2. "My items are vertical when I want them horizontal."**
`flex-direction` is set to `column` somewhere. Default is `row`, but if you've inherited or copied CSS, check.

**3. "Items aren't centred horizontally even though I used `align-items: center`."**
`align-items` works on the **cross** axis. With `flex-direction: row`, that's the **vertical** axis. To centre horizontally on a row, you want `justify-content: center`.

This is the most common flexbox bug. Remember the diagram above.

**4. "My items are stretching to fill the whole height of the container."**
`align-items` defaults to `stretch`. If you don't want that, set it explicitly: `align-items: center` (or `flex-start`, etc.).

**5. "Items are overflowing off the edge of the container."**
Either the items have fixed widths that add up to more than the container, or you need `flex-wrap: wrap` to let them flow to a second row.

**6. "Why is my nav looking weird on every page?"**
Check that every page links to the same stylesheet (`<link rel="stylesheet" href="styles.css">`) and that the nav uses the same class names everywhere.

---

## When you'll see this in AI-generated code later

You'll soon be using AI to build pages. AI loves flexbox — almost every layout it produces will use `display: flex` somewhere. Your job will be to read the code and tell whether it's right.

If the AI gives you a layout that looks broken, trace through the four properties on the container. Nine times out of ten, the bug is one of the six above.
