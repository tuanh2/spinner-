<div align="center">

# ⚡ GenLayer Spinner

**Pure SVG + CSS Loading Spinners for the GenLayer Portal**

[![License: MIT](https://img.shields.io/badge/License-MIT-e619c9.svg)](LICENSE)
[![Dependencies: None](https://img.shields.io/badge/Dependencies-0-8b5cf6.svg)](#tech-specs)
[![Size: <2KB](https://img.shields.io/badge/Size-%3C2KB-22d3ee.svg)](#tech-specs)
[![Accessibility: A11y](https://img.shields.io/badge/A11y-Reduced--Motion-100%25-green.svg)](#accessibility)

[**🔥 Live Preview Demo**](https://tuanh2.github.io/spinner-/) • [**Option 1 Snippet**](#option-1) • [**Option 2 Snippet**](#option-2)

</div>

---

## ✦ Overview

A minimal, high-performance loading spinner design system crafted specifically for the **GenLayer Portal** mission. Built with 100% pure SVG and CSS animations — zero dependencies, zero JavaScript runtime, zero bundle bloat.

| Feature | Option 1 | Option 2 |
|---|---|---|
| **Animation Style** | Hexagon Pulse & Neon Chase | Shatter & Reassemble |
| **Cycle Loop** | 4.0s (Hexagon) / 2.5s (Mark) | 2.0s (Ease-in-out) |
| **Visual Elements** | Hex track + 3 neon trails + glow | Wireframe stroke + 3 flying paths |
| **Theme Support** | Dark & Light (Auto / Data-attribute) | Dark & Light (Auto / Data-attribute) |
| **Reduced Motion** | Fallback to static legible mark | Fallback to static legible mark |
| **Scalability** | 16px to 128px+ pixel-perfect | 16px to 128px+ pixel-perfect |

---

## ✦ Design Motion Concepts

### **Option 1 — Hexagon Neon Chase**
Reuses the GenLayer Portal's iconic hexagon container. Three gradient trails (`#e619c9`, `#8b5cf6`, `#22d3ee`) sweep around the mark contours while the outer hexagon pulses seamlessly. Gives high energy and futuristic web3 presence while preserving identity.

### **Option 2 — Shatter & Reassemble**
Deconstructs the GenLayer mark into its three core contours (left wing, right wing, center diamond). The elements explode outward and snap back together onto an underlying wireframe guide, simulating signal resolution and consensus.

---

## ✦ Quick Start

### 1. Include CSS
Load `spinner.css` in your project's `<head>`:

```html
<link rel="stylesheet" href="spinner.css">
```

### 2. Paste SVG Snippet

#### Option 1
```html
<div class="gl-spinner gl-spinner--o1" data-theme="dark" style="--gl-size: 48px">
  <!-- Paste contents of snippet-o1.html -->
</div>
```

#### Option 2
```html
<div class="gl-spinner gl-spinner--o2" data-theme="dark" style="--gl-size: 48px" role="status" aria-label="Loading">
  <!-- Paste contents of snippet-o2.html -->
</div>
```

---

## ✦ CSS Customization API

Control sizing, speed, and brand colors directly via CSS Custom Properties on any parent container:

```css
.my-custom-loader {
  --gl-size: 32px;         /* Dimensions (width & height) */
  --gl-speed: 1.5;         /* 1.5x speed multiplier */
  --gl-magenta: #e619c9;   /* Primary neon trail */
  --gl-purple:  #8b5cf6;   /* Secondary trail */
  --gl-cyan:    #22d3ee;   /* Tertiary trail */
}
```

| Variable | Default | Description |
|---|---|---|
| `--gl-size` | `48px` | Controls spinner width and height |
| `--gl-magenta` | `#e619c9` | Primary brand neon accent |
| `--gl-purple` | `#8b5cf6` | Secondary gradient accent |
| `--gl-cyan` | `#22d3ee` | Cyan trail highlight |
| `--gl-dur` | `2s` / `4s` | Main loop duration |

---

## ✦ Tech Specs & Accessibility

- **GPU Accelerated**: Uses pure CSS `transform` and `stroke-dashoffset` keyframes for 60FPS compositor rendering.
- **Zero Dependencies**: Pure HTML/CSS/SVG.
- **Accessibility (A11y)**: Built-in `role="status"` and `aria-label="Loading"`.
- **Prefer Reduced Motion**: Fully respects `@media (prefers-reduced-motion: reduce)` by halting all motion and displaying a clean static vector.

---

## ✦ License & Credits

- **License**: MIT © [tuanh2](https://github.com/tuanh2).
- **Brand Geometry**: Symbol & Hexagon shapes © GenLayer Foundation.
- **Repository**: [github.com/tuanh2/spinner-](https://github.com/tuanh2/spinner-)
- **Live Showcase**: [tuanh2.github.io/spinner-/](https://tuanh2.github.io/spinner-/)
