# Polymorphi Framework Architecture

**Version:** 1.0.0  
**Status:** Tokens Complete, Primitives Pending

---

## Overview

Polymorphi is a music-first CSS design system built on four layers:

1. **Tokens** — Atomic CSS custom properties (70,527 tokens)
2. **Primitives** — Companion file specs for building blocks (85 files)
3. **Components** — Composable UI elements built from tokens + primitives
4. **Themes** — Skins that override token values

Each layer inherits from the one below. Change a token → everything cascades.

---

## Layer 1: Tokens (COMPLETE)

### Stats
- **70,527** CSS custom properties
- **40** files
- **19** categories
- **420KB** compressed
- **2.5MB** uncompressed

### Naming Convention

```
--pm-{category}-{property}-{index}
```

| Part | Description | Example |
|------|-------------|---------|
| `--pm-` | Polymorphi prefix | Always present |
| `{category}` | 2-5 letter category code | `blu`, `space`, `fx` |
| `{property}` | Property/dimension name | `base`, `margin`, `blur` |
| `{index}` | 3-digit index (000-255) | `000`, `128`, `255` |

### 256-Step Scale

All continuous values use a 256-step scale (000-255) for:
- Maximum granularity
- AI/automation compatibility
- Predictable interpolation
- Consistent naming

### Categories

| Category | Prefix | Tokens | Description |
|----------|--------|--------|-------------|
| Colors | `blu`, `grn`, `red`, etc. | 33,280 | 13 colors × 10 dimensions × 256 steps |
| Typography | `type` | 2,591 | Weight, size, tracking, leading, etc. |
| Spacing | `space` | 1,792 | Margin, padding, gap, gutter, inset |
| Sizing | `size` | 3,328 | Width, height, flex, aspect-ratio |
| Borders | `border` | 1,556 | Width, radius, outline, ring |
| Effects | `fx` | 3,600 | Shadow, blur, brightness, filters |
| Motion | `motion` | 1,075 | Duration, delay, easing |
| Animation | `anim` | 2,621 | Progress, amplitude, spring physics |
| Layers | `layer` | 1,026 | Z-index, elevation |
| Opacity | `opacity` | 259 | 0-1 transparency |
| Gradients | `grad` | 791 | Angles, stops, radial |
| Transforms | `tf` | 3,337 | Scale, rotate, translate, skew |
| Text | `text` | 2,613 | Tracking, leading, decoration |
| Interaction | `int` | 100 | Cursor, touch, scroll |
| Breakpoints | `bp`, `cq`, `fluid` | 1,292 | Responsive, container queries |
| Grids | `grid` | 2,844 | Columns, rows, spans, gaps |
| Audio | `aud` | 4,104 | Meters, ADSR, frequency, MIDI |
| Fonts | `font` | 862 | 431 font families |
| Icons | `icon` | 3,456 | UI, audio, nav, social |

### Color Dimensions

Each of 13 colors has 10 dimensions:

| Dimension | Code | Description |
|-----------|------|-------------|
| Base | `base` | Lightness 0-100% |
| Saturation | `sat` | Saturation 0-100% |
| Warm | `warm` | Hue shifted +15° |
| Cool | `cool` | Hue shifted -15° |
| Mute | `mute` | 30% saturation |
| Vivid | `vivid` | 100% saturation |
| Tint | `tint` | Mixed toward white |
| Shade | `shade` | Mixed toward black |
| Tone | `tone` | Mixed toward gray |
| Alpha | `alpha` | Opacity 0-1 |

### File Structure

```
tokens/
├── colors/           # 13 files
├── fonts/            # 6 files
├── icons/            # 5 files
├── typography/       # 1 file
├── spacing/          # 1 file
├── sizing/           # 1 file
├── borders/          # 1 file
├── effects/          # 1 file
├── motion/           # 1 file
├── animation/        # 1 file
├── layers/           # 1 file
├── opacity/          # 1 file
├── gradients/        # 1 file
├── transforms/       # 1 file
├── text/             # 1 file
├── interaction/      # 1 file
├── breakpoints/      # 1 file
├── grids/            # 1 file
├── audio/            # 1 file
├── all.tokens.css    # Master import
└── registry.html     # Documentation
```

---

## Layer 2: Primitives (PENDING)

### Overview

Primitives are **companion files** — JSON specs that define building blocks for AI and human consumption. They describe behavior, constraints, and relationships.

### Stats (Planned)
- **85** companion.json files
- **17** categories

### Companion File Format

```json
{
  "name": "primitive-name",
  "version": "1.0.0",
  "description": "What this primitive does",
  "category": "controllers",
  "tokens": ["--pm-aud-knob-*"],
  "properties": {},
  "constraints": {},
  "behaviors": {},
  "accessibility": {},
  "examples": []
}
```

### Categories

| Category | Files | Description |
|----------|-------|-------------|
| music-theory | 8 | Notes, scales, chords, keys, tempo |
| controllers | 9 | Faders, knobs, pads, wheels |
| displays | 9 | Meters, spectrum, waveform, tuner |
| processors | 9 | EQ, compressor, reverb, delay |
| synthesis | 6 | Oscillators, envelopes, LFOs |
| routing | 6 | Channels, buses, sends |
| transport | 7 | Play, record, loop, sync |
| hardware | 6 | Rack units, connectors, LEDs |
| layout | 6 | Channel strips, mixer, piano roll |
| branding | 5 | Logo, badge, press kit |
| ui-patterns | 7 | Modal, dropdown, toast |
| forms | 7 | Input, select, toggle |
| data-display | 7 | Table, card, progress |
| navigation | 6 | Navbar, sidebar, menu |
| feedback | 4 | Alert, spinner, error |

---

## Layer 3: Components (FUTURE)

Components are **CSS files** that compose tokens and primitives into usable UI elements.

### Planned Structure

```
components/
├── audio/
│   ├── mixer.css
│   ├── channel-strip.css
│   ├── transport-bar.css
│   ├── plugin-rack.css
│   └── daw-layout.css
├── ui/
│   ├── buttons.css
│   ├── forms.css
│   ├── cards.css
│   ├── modals.css
│   └── navigation.css
└── layouts/
    ├── app-shell.css
    ├── dashboard.css
    └── responsive.css
```

### Component Rules

1. Components ONLY reference tokens — no hardcoded values
2. Components MAY reference other components
3. Components document their primitive dependencies
4. Components are theme-agnostic

---

## Layer 4: Themes (FUTURE)

Themes override token values to create visual variants.

### Planned Themes

```
themes/
├── dark.css       # Default dark mode
├── light.css      # Light mode
├── vintage.css    # Analog/retro aesthetic
├── neon.css       # Cyberpunk/synthwave
└── minimal.css    # Reduced visual noise
```

### Theme Rules

1. Themes ONLY override `:root` token values
2. Themes do NOT add new tokens
3. Themes maintain semantic meaning
4. Themes are composable via CSS cascade

---

## Design Principles

### 1. Cascade First
Change one token → affects everything that references it. No exceptions.

### 2. Music First
Audio production UI patterns are first-class citizens, not afterthoughts.

### 3. AI Compatible
256-step scales and predictable naming for automated systems.

### 4. Zero Build
Pure CSS. No preprocessors. No JavaScript required.

### 5. Granular Control
Maximum options at the token level. Compose up, not down.

---

## Usage

### Import Everything
```css
@import "polymorphi/tokens/all.tokens.css";
```

### Import Selectively
```css
@import "polymorphi/tokens/colors/blue.tokens.css";
@import "polymorphi/tokens/spacing/spacing.tokens.css";
```

### Use Tokens
```css
.my-element {
  color: var(--pm-blu-base-128);
  padding: var(--pm-space-padding-016);
  border-radius: var(--pm-border-radius-008);
}
```

---

## Versioning

- **Tokens:** Semantic versioning (breaking changes = major bump)
- **Primitives:** Follows token version
- **Components:** Independent versioning
- **Themes:** Independent versioning

---

## License

MIT

