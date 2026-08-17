# GenLayer Spinner — Option 1 & Option 2

**Two loading-spinner concepts for the GenLayer Portal mission.**

Option 1 sends three coloured trails around the polygon mark while a hexagon border pulses behind it. Option 2 flies the left wing, right wing and core diamond apart then reassembles them on a stroked wireframe. Both are pure SVG + CSS, light and dark, reduced-motion safe.

> **Watch it move on the [live demo](https://tuanh2.github.io/spinner-/)**, or open `index.html` locally.

Submitted to the [GenLayer Portal mission](https://portal.genlayer.foundation) — *Design the GenLayer Spinner*.

| | Option 1 | Option 2 |
|---|---|---|
| **Loop** | 4 s hex / 2.5 s mark | 2 s |
| **Easing** | linear / ease-in-out | ease-in-out |
| **Elements** | hex track + edge pulse + 3 trails + neon | wireframe + 3 paths |
| **Technique** | SVG + CSS, no dependencies, no JavaScript | SVG + CSS, no dependencies, no JavaScript |
| **Themes** | light and dark, automatic | light and dark, automatic |
| **A11y** | `role="status"`, `prefers-reduced-motion` respected | `role="status"`, `prefers-reduced-motion` respected |
| **Size** | legible from 72 px down to 16 px | legible from 72 px down to 16 px |

---

## Why this motion

**Option 1.** The Portal already has a hexagon container wrapping the mark on badges and icons. Reusing that exact geometry means the spinner is a component the interface already knows, temporarily in motion. The neon gradient and three offset trails give it energy without losing the GenLayer identity.

**Option 2.** The GenLayer symbol's three closed contours — left wing, right wing, core — are already distinct shapes. Separating them along their natural axes and bringing them back together reads as the mark assembling itself, or as a signal resolving. The wireframe underneath holds the silhouette between passes so the shape never disappears.

---

## What is in here

| File | What it is |
|---|---|
| `spinner.css` | Styles and keyframes for both options. |
| `snippet-o1.html` | Option 1 SVG markup, ready to paste. Pairs with `spinner.css`. |
| `snippet-o2.html` | Option 2 SVG markup, ready to paste. Pairs with `spinner.css`. |
| `index.html` | The demo page — live preview on both grounds, size ladder, speed control, in-context examples. |

---

## Use it

### 1 · Paste snippet + CSS

Copy `snippet-o1.html` or `snippet-o2.html` into your markup and load `spinner.css`. Set `data-theme="dark"` or `data-theme="light"` on the spinner element.

```html
<link rel="stylesheet" href="spinner.css">

<!-- Option 1 -->
<div class="gl-spinner gl-spinner--o1" data-theme="dark" style="--gl-size:20px">
  <!-- contents of snippet-o1.html -->
</div>

<!-- Option 2 -->
<div class="gl-spinner gl-spinner--o2" data-theme="dark" style="--gl-size:20px"
     role="status" aria-label="Loading">
  <!-- contents of snippet-o2.html -->
</div>
```

### 2 · CSS variables

Override size, speed, and colours from any ancestor:

```css
.my-container {
  --gl-size: 20px;
  --gl-speed: 1.5;       /* half again as fast */
  --gl-magenta: #e619c9;
  --gl-purple:  #8b5cf6;
  --gl-cyan:    #22d3ee;
}
```

| Variable | Default | Does |
|---|---|---|
| `--gl-size` | `48px` | Width and height |
| `--gl-magenta` | `#e619c9` | Primary neon colour |
| `--gl-purple` | `#8b5cf6` | Secondary trail colour |
| `--gl-cyan` | `#22d3ee` | Tertiary trail colour |

### 3 · As `<img>`

For a static preview (no animation):

```html
<img src="preview.svg" width="24" height="24" alt="Loading">
```

---

## Accessibility

Both spinners carry `role="status"` and an `aria-label` that defaults to *Loading*, so assistive tech announces the wait instead of skipping it. Under `prefers-reduced-motion: reduce` every animation stops and the spinner resolves to a legible static state — the mark stays visible, it simply holds still.

---

## Design notes

The geometry is not a redraw. The polygon paths (Option 1) are lifted from the GenLayer mark SVG. The three path commands (Option 2) are lifted unmodified from `gl-symbol-black.svg` in `genlayer-foundation/points`, the Portal's own repository — so the proportions, the notch in each wing and the angle of the core are exactly the ones already in production.

The hexagon geometry (Option 1 background) is from the Portal's hexagon badge path. The palette is derived from the GenLayer brand:

| Token | Value | Used for |
|---|---|---|
| magenta | `#e619c9` | Primary neon, trails |
| purple | `#8b5cf6` | Secondary trail |
| cyan | `#22d3ee` | Tertiary trail |

Motion is CSS only. No JavaScript, no runtime, no animation library, nothing to bundle — each spinner is a few `<svg>` elements and a handful of keyframes. It renders on the compositor, so it stays smooth on a page that is busy doing the work the user is waiting for.

---

## Licence

MIT — see LICENSE. Free for the GenLayer Foundation to use, modify and ship in the Portal or anywhere else.

Symbol and palette © GenLayer Foundation, used from their public repository. Motion design, packaging and documentation are original work by [@tuanh2](https://github.com/tuanh2).

Repository: [github.com/tuanh2/spinner-](https://github.com/tuanh2/spinner-)
