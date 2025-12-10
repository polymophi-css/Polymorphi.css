# Polymorphi Foundation

## Layer 0: Foundation

Load **before** tokens. Provides the base reset and utilities.

### Files

| File | Lines | Purpose |
|------|-------|---------|
| reset.foundation.css | 299 | Modern CSS reset |
| normalize.foundation.css | 299 | Cross-browser normalization |
| responsive.foundation.css | 591 | Breakpoints, aspect ratios, containers, responsive display/grid |
| utilities.foundation.css | 607 | Common utilities (sr-only, positioning, text, etc.) |

### Aspect Ratios Supported

- 1:1 (Square)
- 4:3 (Classic TV)
- 3:2 (Photo)
- 16:10 (MacBook)
- 16:9 (HD Video)
- **21:9 (Ultrawide)**
- **32:9 (Super Ultrawide)**
- Portrait variants (9:16, 9:21, 2:3, 3:4)

### Responsive Prefixes

**Width Breakpoints:**
- `pm-xs:` 320px+
- `pm-sm:` 480px+
- `pm-md:` 768px+
- `pm-lg:` 1024px+
- `pm-xl:` 1280px+
- `pm-2xl:` 1440px+
- `pm-3xl:` 1600px+
- `pm-4xl:` 1920px+ (Full HD)
- `pm-5xl:` 2560px+ (QHD)
- `pm-6xl:` 3840px+ (4K)

**Height Breakpoints:**
- `pm-h-xs:` 480px+
- `pm-h-sm:` 600px+
- `pm-h-md:` 768px+
- `pm-h-lg:` 900px+
- `pm-h-xl:` 1080px+
- `pm-h-2xl:` 1440px+

**Aspect Ratio:**
- `pm-ultrawide:` 21:9+
- `pm-superwide:` 32:9+
- `pm-widescreen:` 16:9 to 21:9
- `pm-16-10:` 16:10 to 16:9
- `pm-classic:` 4:3 to 16:10
- `pm-square:` 1:1 to 4:3
- `pm-portrait:` below 1:1
- `pm-landscape:` landscape orientation

### Usage

```css
@import "polymorphi-foundation/all.foundation.css";
@import "polymorphi-tokens/all.tokens.css";
@import "polymorphi-components/all.components.css";
```
