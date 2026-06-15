# ease-dna-spin

> A premium animated DNA Helix utility for the **EaseMotion CSS** repository.  
> Pure HTML & CSS. Zero JavaScript. Zero dependencies. Infinite elegance.

---

## Description

`ease-dna-spin` renders a futuristic, smoothly rotating DNA double-helix using
nothing but HTML structure and CSS animations. Designed for biotechnology
interfaces, AI laboratory dashboards, medical data visualizations, and any
premium design system that needs a living, breathing visual identity at its core.

The twist illusion is achieved by staggering `scaleX` keyframes across 14
connector rungs — each rung compresses and expands at a different phase offset,
simulating the depth of a helix rotating in 3D space without a single line of
JavaScript or any CSS 3D transform.

---

## Features

- **Pure HTML & CSS** — no JavaScript, no external libraries, no build step
- **Responsive** — adapts fluidly across desktop, tablet, and mobile viewports
- **Infinite Animation** — seamless loop with no visible restart artifact
- **Hover Variant** — scale-up and glow intensification on pointer interaction
- **Glow Variant** — amplified cyan/purple/blue aura for hero placements
- **Fast Variant** — 2× speed for data-processing / loading states
- **Slow Variant** — 0.5× speed for ambient / background use
- **Large Variant** — 1.6× scale for feature hero sections
- **Mini Variant** — 0.5× scale for inline use in cards, navbars, or badges
- **Composable** — stack any combination of variant classes freely
- **Accessibility** — full `prefers-reduced-motion` support; all animations
  are disabled for users who request reduced motion

---

## Usage

### 1. Include the stylesheet

```html
<link rel="stylesheet" href="ease-dna-spin/style.css" />
```

### 2. Default helix

```html
<div class="ease-dna-spin">
  <div class="dna-track">

    <div class="dna-strand dna-strand-left"></div>
    <div class="dna-strand dna-strand-right"></div>

    <div class="dna-connectors">
      <!-- Repeat this block 14 times for a full helix -->
      <div class="dna-rung">
        <div class="dna-node"></div>
        <div class="dna-rung-bar"></div>
        <div class="dna-node"></div>
      </div>
      <!-- × 14 -->
    </div>

  </div>
</div>
```

### 3. With variant modifiers

```html
<!-- Glow + Hover + default speed -->
<div class="ease-dna-spin ease-dna-glow ease-dna-hover">
  ...
</div>

<!-- Mini helix in a loading badge -->
<div class="ease-dna-spin ease-dna-mini ease-dna-fast">
  ...
</div>

<!-- Hero section: large, slow, maximum glow -->
<div class="ease-dna-spin ease-dna-large ease-dna-slow ease-dna-glow">
  ...
</div>
```

### 4. Variant reference

| Class             | Effect                                      |
|-------------------|---------------------------------------------|
| `ease-dna-spin`   | Base helix — required on every instance     |
| `ease-dna-fast`   | 2× animation speed                          |
| `ease-dna-slow`   | 0.5× animation speed                        |
| `ease-dna-glow`   | Amplified cyan / purple / blue aura         |
| `ease-dna-hover`  | Scale-up + glow boost on `:hover`           |
| `ease-dna-large`  | 1.6× size (192 × 768 px base)               |
| `ease-dna-mini`   | 0.5× size (64 × 256 px base)               |

All variants are composable — combine freely without class conflicts.

---

## Accessibility

`ease-dna-spin` respects the user's operating system preference for reduced
motion. When `prefers-reduced-motion: reduce` is detected, every animation and
transition is disabled, leaving a clean, static visual that still communicates
the DNA structure without motion.

```css
@media (prefers-reduced-motion: reduce) {
  /* All animations are suppressed automatically */
}
```

---

## Why it fits EaseMotion CSS

EaseMotion CSS is built on three principles:

### Animation-first
Every utility class in EaseMotion exists to produce motion, not just style.
`ease-dna-spin` is entirely defined by its animations — remove them and you
have two coloured bars and some dots. The visual *is* the animation.

### Human-readable
Class names read like intent. `.ease-dna-spin` means *"spin this DNA element."*
`.ease-dna-glow` means *"make it glow more."* No cryptic shorthand, no memorised
breakpoint prefixes. Any developer can read the HTML and understand exactly what
is happening and why.

### Composable
Modifier classes are orthogonal. Speed variants don't know about size variants.
Glow doesn't know about hover. This means you can stack `.ease-dna-fast`,
`.ease-dna-large`, `.ease-dna-glow`, and `.ease-dna-hover` onto a single
element without any class overriding another. The CSS custom property
architecture (`--dna-helix-w`, `--dna-duration`, etc.) ensures each modifier
only changes the axis it owns.

---

## Folder Structure

```
ease-dna-spin/
├── demo.html      ← Live demo of all variants
├── style.css      ← The utility (import this)
└── README.md      ← This file
```

---

## Browser Support

Works in all modern browsers that support CSS custom properties, `@keyframes`,
`animation`, and `backdrop-filter`. Graceful degradation in browsers without
`backdrop-filter` (glassmorphism card fallback is a semi-transparent surface).

| Browser         | Support   |
|-----------------|-----------|
| Chrome 90+      | ✓ Full    |
| Firefox 90+     | ✓ Full    |
| Safari 14+      | ✓ Full    |
| Edge 90+        | ✓ Full    |
| iOS Safari 14+  | ✓ Full    |
| Android Chrome  | ✓ Full    |

---

## License

MIT — free for personal and commercial use.

---

*Built for EaseMotion CSS · Pure HTML & CSS · Zero JavaScript*