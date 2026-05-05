# Colour: snippet patterns and guidance

Reference for picking colours that work. Copy values into your own CSS — don't paste the whole file.

## Colour formats in CSS

Three ways to write the same colour:

| Format | Example | Notes |
|--------|---------|-------|
| Named | `tomato` | About 140 names available. Quick but limited. |
| Hex | `#ff6347` | Six hex digits. Most common. |
| RGB | `rgb(255, 99, 71)` | Useful when you want transparency: `rgba(255, 99, 71, 0.5)` |

All three above produce the same orange-red.

## Starter palettes

Pick one. All have been checked for readable text contrast.

### Calm blue

```
background  #f5f7fa   (very light blue-grey)
text        #1f2937   (near black, slightly blue)
accent      #2563eb   (medium blue)
muted       #64748b   (grey-blue)
```

```css
body { background: #f5f7fa; color: #1f2937; }
h1   { color: #2563eb; }
.muted { color: #64748b; }
```

### Warm earth

```
background  #fdf6e3   (cream)
text        #3a2e1f   (dark brown)
accent      #b45309   (burnt orange)
muted       #8b7355   (warm grey)
```

```css
body { background: #fdf6e3; color: #3a2e1f; }
h1   { color: #b45309; }
.muted { color: #8b7355; }
```

### High contrast (best for accessibility)

```
background  #ffffff   (white)
text        #000000   (black)
accent      #d62828   (red)
muted       #555555   (medium grey)
```

```css
body { background: #ffffff; color: #000000; }
h1   { color: #d62828; }
.muted { color: #555555; }
```

## Contrast rules (don't skip)

Text needs to be readable. The professional standard is **WCAG AA**:

- **Body text vs background**: at least 4.5:1 contrast ratio
- **Large headings (24px+) vs background**: 3:1 is enough

If unsure: dark text on light background, or light text on dark background. Never mid-grey on mid-grey.

**Test any pair:** paste your two colours into [https://webaim.org/resources/contrastchecker/](https://webaim.org/resources/contrastchecker/)

## Common mistakes

| Mistake | Why it's bad | Better |
|---------|--------------|--------|
| Pure black on pure white | Technically passes contrast but feels harsh on screens | `#1f2937` on `#ffffff` |
| Light grey text (`#aaa` on white) | Fails contrast. Hard to read for low-vision users | `#555` minimum |
| Coloured text on coloured background | Usually fails contrast | Keep one of them neutral |
| Too many colours on one page | Looks chaotic | Pick 3–4 and stick with them |

## Applying colour

```css
body {
  background: #f5f7fa;
  color: #1f2937;       /* `color` always means TEXT colour */
}

h1 {
  color: #2563eb;       /* accent for the main heading */
}

.note {
  background: #fff3cd;        /* light yellow */
  color: #856404;             /* dark yellow-brown text */
  border-left: 4px solid #ffc107;
  padding: 1rem;
}

a {
  color: #2563eb;       /* matches our accent */
}
```

## Where to find more colours

- [https://coolors.co](https://coolors.co) — generates palettes. Use the "shuffle" button.
- [https://www.realtimecolors.com](https://www.realtimecolors.com) — preview colours on a real-looking page before committing.
- VS Code: hover over any colour value in your CSS and a colour picker pops up.

## Plain-English property reference

| Property | What it does | Example |
|----------|--------------|---------|
| `color` | Text colour (note: American spelling) | `color: navy;` |
| `background` | Colour or image behind the element | `background: #f5f7fa;` |
| `background-color` | Just the colour part (same as `background` for solid colours) | `background-color: white;` |
| `border` | A line around the element | `border: 2px solid black;` |
| `border-left` | Just the left side line | `border-left: 4px solid red;` |
