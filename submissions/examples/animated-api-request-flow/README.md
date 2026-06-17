# Animated API Request Flow

**EaseMotion CSS submission** · Pure HTML & CSS · No JavaScript · No external libraries

---

## 1. What does this do?

This component renders a **real-time API request flow visualization** styled as a modern SaaS architecture dashboard. It shows five infrastructure nodes — Client, API Gateway, Application Server, Database, and External Service — connected by animated data-flow lines and traveling packet indicators.

Every animation is driven by pure CSS:

| Effect | Technique |
|--------|-----------|
| Pulsing node rings | `@keyframes ping-ring` with expanding `inset` border |
| Traveling data packets | Absolute-positioned elements with `translate` keyframes |
| Glowing connection lines | SVG `stroke-dashoffset` animation with `feGaussianBlur` filter |
| Floating status pills | Subtle `translateY` loop |
| Hover lift on cards | `transform: translateY(-6px) scale(1.02)` + `transition` |
| Entry animation on log rows | Staggered `animation-delay` + `translateX` slide-in |

The component also includes a metrics bar (requests/sec, success rate, active connections, DB query time) and a live request log panel, giving it the feel of a genuine infrastructure monitoring tool.

---

## 2. How is it used?

### Drop-in usage

Link `style.css` and add the `.api-flow` wrapper to your HTML:

```html
<link rel="stylesheet" href="style.css" />

<div class="api-flow">
  <!-- Node grid -->
  <div class="flow-grid">
    <article class="flow-node flow-client">
      <div class="node-icon">🖥</div>
      <div class="node-name">Client</div>
      <div class="node-role">Browser / Mobile App</div>
      <div class="node-status"><span class="status-dot"></span>Connected</div>
    </article>

    <article class="flow-node flow-gateway">
      <div class="node-icon">🔀</div>
      <div class="node-name">API Gateway</div>
      <div class="node-role">Auth · Rate limit · Route</div>
      <div class="node-status"><span class="status-dot"></span>Active</div>
    </article>

    <article class="flow-node flow-appserver">
      <div class="node-icon">⚙️</div>
      <div class="node-name">App Server</div>
      <div class="node-role">Business logic · Orchestration</div>
      <div class="node-status"><span class="status-dot"></span>Running</div>
    </article>

    <article class="flow-node flow-database">
      <div class="node-icon">🗄</div>
      <div class="node-name">Database</div>
      <div class="node-role">PostgreSQL · Redis cache</div>
      <div class="node-status"><span class="status-dot"></span>Healthy</div>
    </article>

    <article class="flow-node flow-external">
      <div class="node-icon">🌐</div>
      <div class="node-name">External API</div>
      <div class="node-role">Payment · Email · Storage</div>
      <div class="node-status"><span class="status-dot"></span>Online</div>
    </article>
  </div>
</div>
```

### Full demo

Open `demo.html` directly in any modern browser — no build step, no server required.

### Customisation

All timing and colours are controlled by CSS custom properties at the top of `style.css`:

```css
:root {
  --packet-speed: 2.4s;   /* data packet travel duration */
  --cyan:   #63b3ed;       /* Client accent */
  --violet: #b794f4;       /* API Gateway accent */
  --green:  #68d391;       /* App Server accent */
  --amber:  #f6ad55;       /* Database accent */
  --rose:   #fc8181;       /* External Service accent */
}
```

Swap any hex value to re-theme the entire diagram.

---

## 3. Why is it useful?

**For documentation sites** — embed a live, animated architecture diagram directly in Markdown-rendered pages or static sites without loading a diagram library.

**For SaaS dashboards** — drop the component into an admin panel or status page to communicate infrastructure health visually, without the runtime overhead of a charting library or canvas renderer.

**For developer onboarding** — a self-contained, always-up-to-date visual of your API call chain helps new engineers understand the system at a glance.

**For presentations and landing pages** — the dark glassmorphism aesthetic fits naturally alongside marketing copy for developer tools, API products, or cloud infrastructure services.

**Zero dependencies** means it loads instantly, works offline, has no supply-chain risk, and requires no build pipeline.

---

## File structure

```
animated-api-request-flow/
├── demo.html   ← Full self-contained demo
├── style.css   ← All styles and animations
└── README.md   ← This file
```

## Browser support

All modern browsers (Chrome 88+, Firefox 89+, Safari 14+, Edge 88+).  
Respects `prefers-reduced-motion` — all animations are disabled for users who prefer less motion.