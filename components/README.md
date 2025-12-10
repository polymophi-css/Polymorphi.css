# Polymorphi Components

**Layer 3: Composites built from Tokens + Primitives**

## Files

### Audio
- `mixer.css` - Channel strip mixer
- `transport.css` - Transport bar controls
- `arrangement.css` - Timeline/arrangement view
- `plugin-rack.css` - FX chain/plugin rack
- `pad-grid.css` - MPC-style pad sampler

### UI
- `buttons.css` - Button variants and states
- `forms.css` - Inputs, selects, checkboxes, toggles
- `cards.css` - Card containers, badges, avatars

### Layouts
- `app-shell.css` - DAW-style application shell

## Usage

```css
/* Import tokens first */
@import "polymorphi-tokens/all.tokens.css";

/* Then import components */
@import "polymorphi-components/all.components.css";
```

## Naming Convention

All components use BEM-style naming:
- `.pm-{component}` - Block
- `.pm-{component}__{element}` - Element
- `.pm-{component}--{modifier}` - Modifier

## Rules

1. Components ONLY reference tokens - no hardcoded values
2. Components document their primitive dependencies
3. Components are theme-agnostic
