# Polymorphi.css Tokens

**70,527 CSS custom property tokens** for comprehensive design systems.

## Structure

```
polymorphi-tokens/
├── colors/          # 13 files × 2,560 tokens = 33,280
│   ├── blue.tokens.css
│   ├── green.tokens.css
│   ├── red.tokens.css
│   ├── black.tokens.css
│   ├── orange.tokens.css
│   ├── yellow.tokens.css
│   ├── brown.tokens.css
│   ├── white.tokens.css
│   ├── gray.tokens.css
│   ├── pink.tokens.css
│   ├── violet.tokens.css
│   ├── magenta.tokens.css
│   └── purple.tokens.css
├── fonts/           # 6 files = 862 tokens
│   ├── fonts-sans.tokens.css
│   ├── fonts-serif.tokens.css
│   ├── fonts-mono.tokens.css
│   ├── fonts-script.tokens.css
│   ├── fonts-display.tokens.css
│   └── fonts-all.tokens.css
├── icons/           # 5 files = 3,456 tokens
│   ├── icons-ui.tokens.css
│   ├── icons-audio.tokens.css
│   ├── icons-nav.tokens.css
│   ├── icons-social.tokens.css
│   └── icons-all.tokens.css
├── typography/      # 2,591 tokens
├── spacing/         # 1,792 tokens
├── sizing/          # 3,328 tokens
├── borders/         # 1,556 tokens
├── effects/         # 3,600 tokens
├── motion/          # 1,075 tokens
├── animation/       # 2,621 tokens
├── layers/          # 1,026 tokens
├── opacity/         # 259 tokens
├── gradients/       # 791 tokens
├── transforms/      # 3,337 tokens
├── text/            # 2,613 tokens
├── interaction/     # 100 tokens
├── breakpoints/     # 1,292 tokens
├── grids/           # 2,844 tokens
└── audio/           # 4,104 tokens
```

## Naming Convention

All tokens follow: `--pm-{category}-{property}-{000-255}`

### 256-Step Scales
- Colors: 10 dimensions × 256 steps per color
- Spacing/Sizing/Effects: 256 steps per property
- Audio: 256-step MIDI-compatible values

### Examples
```css
--pm-blue-base-128      /* Blue at 50% lightness */
--pm-space-margin-032   /* 8rem margin */
--pm-aud-knob-127       /* Knob at max (135°) */
--pm-tf-rotate-090      /* 90° rotation */
```

## Color Dimensions
1. BASE - Lightness 0-100%
2. SAT - Saturation 0-100%
3. WARM - Hue +15°
4. COOL - Hue -15°
5. MUTE - 30% saturation
6. VIVID - Full saturation, constrained lightness
7. TINT - Mix toward white
8. SHADE - Mix toward black
9. TONE - Mix toward gray
10. ALPHA - Opacity 0-1

## Audio-Specific
- VU/Peak meters with proper color gradients
- ADSR envelope controls
- Frequency (20Hz-20kHz logarithmic)
- Q/Resonance values
- BPM (20-300)
- Musical timing divisions
- MIDI-compatible 0-127 ranges

## Usage

Import what you need:
```css
@import "polymorphi-tokens/colors/blue.tokens.css";
@import "polymorphi-tokens/spacing/spacing.tokens.css";
```

Or import all:
```css
@import "polymorphi-tokens/all.tokens.css";
```

## License

MIT
