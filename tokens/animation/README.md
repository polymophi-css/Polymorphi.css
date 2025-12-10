# Polymorphi Animation Tokens

## 6-Tier Animation System

| Tier | Name | Tempo | Character | Use Cases |
|------|------|-------|-----------|-----------|
| 1 | Largo | 40-60 BPM | Very slow, stately | Page transitions, hero reveals |
| 2 | Adagio | 60-80 BPM | Slow, expressive | Modals, drawers, collapse |
| 3 | Andante | 80-108 BPM | Walking pace | Menus, tooltips, standard UI |
| 4 | Allegro | 108-140 BPM | Fast, lively | Hover, buttons, micro-interactions |
| 5 | Vivace | 140-176 BPM | Very fast | Real-time meters, gaming, data viz |
| 6 | Fortissimo | 176+ BPM | Maximum chaos | Glitch, explosions, celebrations |

## Stats
- 353 @keyframes animations
- 3,217 CSS tokens
- 160 ready-to-use presets

## Usage

```css
@import "polymorphi-animation/all.animation.tokens.css";

.element {
  animation: var(--pm-allegro-preset-pop);
}
```

## Token Patterns

Each tier includes:
- Duration scale (17 values: 000-255)
- Easing curves (standard, sine, quad, cubic, quart, quint, expo, circ, back, elastic, spring)
- Delay scale
- Stagger increments
- Iteration counts
- Direction, fill mode, play state
- Keyframe animations
- Ready-to-use presets
