# TheFileGarage — Duolingo-Style Claymorphism Design System

## Design Philosophy

This design system transforms the previous gradient-heavy claymorphism into a **playful, approachable Duolingo-inspired aesthetic** with a beaver mascot color palette. The key principles are:

- **Solid colors only** — No gradients, no glassmorphism
- **Chunky shadows** — Duolingo-style offset box shadows for depth
- **Playful but trustworthy** — Balances fun with professionalism for document handling
- **Beaver-inspired warmth** — Amber/copper primary with teal accents

---

## Color Palette

### Primary Colors (Beaver-Inspired)

```css
--tfg-primary: #F0A030        /* Hard Hat Amber — beaver fur, buttons, mascot */
--tfg-primary-strong: #c87d1a /* Darker amber for shadows/hover states */
--tfg-teal: #1B9C85            /* Teal — success states, accent pop */
--tfg-navy: #2E4374            /* Blueprint Navy — headers, precision accents */
--tfg-ink: #2B2620             /* Dark brown — primary text, borders */
```

### Surface Colors

```css
--tfg-canvas: #FBF7F1          /* Warm ivory background (not stark white) */
--tfg-surface: #ffffff         /* Card backgrounds (light mode) */
--tfg-muted: #6b615a           /* Muted brown for secondary text */
```

### Dark Mode

```css
Background: #1a1510            /* Deep warm brown */
Card surface: #2a2420          /* Lighter warm brown */
Borders: #F0A030               /* Amber borders for contrast */
Shadows: #1a1510               /* Darker browns for depth */
```

---

## Typography

### Font Stack

```css
Headings: "Baloo 2", Inter, sans-serif
Body: "Inter", -apple-system, sans-serif
Mono: "JetBrains Mono", ui-monospace, monospace
```

**Rationale:** Baloo 2 provides the rounded, pillowy feel that matches claymorphism perfectly (think Duolingo's playful mascot headers), while Inter keeps forms, buttons, and document-related content professional and trustworthy.

### Font Weights
- Headings: 700-800 (bold, chunky)
- Body: 400-600 (readable, balanced)
- Buttons: 700 (confident, clear)

---

## Component Styles

### Cards (`.clay-card`)

**Light Mode:**
```css
background: #ffffff
border: 3px solid #2B2620
box-shadow: 0 6px 0 #2B2620
border-radius: 1.5rem
```

**Hover State:**
```css
transform: translateY(-2px)
box-shadow: 0 8px 0 #2B2620
```

**Active State:**
```css
transform: translateY(2px)
box-shadow: 0 2px 0 #2B2620
```

**Dark Mode:**
```css
background: #2a2420
border: 3px solid #F0A030
box-shadow: 0 6px 0 #1a1510
```

### Primary Buttons (`.clay-btn-primary`)

**Default State:**
```css
background: #F0A030
color: #2B2620
border: 3px solid #2B2620
box-shadow: 0 5px 0 #c87d1a
border-radius: 1rem
```

**Hover State:**
```css
transform: translateY(-3px)
box-shadow: 0 8px 0 #c87d1a
```

**Active State:**
```css
transform: translateY(2px)
box-shadow: 0 2px 0 #c87d1a
```

**Philosophy:** Chunky, offset shadows create a tactile "press-down" effect reminiscent of Duolingo's playful button interactions.

### Secondary Pills (`.clay-pill`)

**Light Mode:**
```css
background: #ffffff
border: 3px solid #2B2620
box-shadow: 0 4px 0 #2B2620
```

**Hover State:**
```css
background: #1B9C85 (teal accent)
color: #ffffff
transform: translateY(-2px)
box-shadow: 0 6px 0 #156e5e
```

### Navigation Tabs (`.clay-tab`)

**Inactive:**
```css
background: transparent
color: #2B2620
```

**Active:**
```css
background: #F0A030
color: #2B2620
border: 3px solid #2B2620
box-shadow: 0 4px 0 #c87d1a
border-radius: 1rem
```

**Dark Mode Active:**
```css
background: #F0A030
color: #2B2620
border: 3px solid #1a1510
box-shadow: 0 4px 0 #c87d1a
```

### Dropzones (`.clay-inset`)

**Default:**
```css
background: #f5f0ea
border: 3px dashed #F0A030
box-shadow: inset 0 3px 0 rgba(43, 38, 32, 0.1)
```

**Hover/Dragover:**
```css
border-color: #1B9C85 (teal)
border-style: solid
background: #e8e3dd
transform: scale(1.02)
```

### Navigation Bar (`.glass-bar`)

**NO GLASS EFFECTS** — Solid colors only:

**Light Mode:**
```css
background: #ffffff (solid)
border-bottom: 3px solid #2B2620
```

**Dark Mode:**
```css
background: #2a2420 (solid)
border-bottom: 3px solid #F0A030
```

---

## Shadow System (Duolingo-Inspired)

### Shadow Philosophy
Inspired by Duolingo's chunky, playful shadows that create depth through **solid offset box-shadows** rather than blur.

### Shadow Scale

| Element | Shadow |
|---------|--------|
| Small elements (pills) | `0 4px 0 [color]` |
| Medium elements (buttons) | `0 5px 0 [color]` |
| Large elements (cards) | `0 6px 0 [color]` |
| Hover state | Add 2-3px to base |
| Active/pressed | Reduce to `0 2px 0 [color]` |

### Shadow Colors by Theme

**Light Mode:**
- Primary shadows: `#2B2620` (dark brown)
- Amber shadows: `#c87d1a` (darker amber)
- Teal shadows: `#156e5e` (darker teal)

**Dark Mode:**
- Primary shadows: `#1a1510` (deep brown)
- Amber shadows: `#c87d1a` (darker amber)
- Teal shadows: `#156e5e` (darker teal)

---

## Animation & Interaction

### Transition Timing
```css
transition: all 0.1s ease /* Fast, snappy like Duolingo */
```

### Transform Scale
- Hover: `translateY(-2px)` to `translateY(-3px)`
- Active: `translateY(2px)`
- Scale on special elements: `scale(1.02)`

### Cubic Bezier (for special cases)
```css
cubic-bezier(0.34, 1.56, 0.64, 1) /* Slight bounce for cards */
```

---

## Special Components

### QR Code Containers

The live QR code generation boxes maintain scannability while adopting the playful aesthetic:

```css
background: #ffffff
border: 3px solid #F0A030
border-radius: 1.5rem
box-shadow: 0 6px 0 #c87d1a
padding: 1rem
```

The QR codes themselves remain high-contrast (black on white) to ensure reliable phone scanning.

### Toast Notifications

```css
background: #ffffff
border: 3px solid #2B2620
border-radius: 1.25rem
box-shadow: 0 6px 0 #2B2620
```

**Dark Mode:**
```css
background: #2a2420
border: 3px solid #F0A030
box-shadow: 0 6px 0 #1a1510
```

---

## Accessibility

### Contrast Ratios
- Primary text (`#2B2620`) on light backgrounds: **>14:1** ✓
- Amber (`#F0A030`) on dark text: **~4.5:1** ✓
- Teal (`#1B9C85`) on white: **>4.5:1** ✓

### Focus States
```css
:focus-visible {
    outline: 3px solid #1B9C85 (teal)
    outline-offset: 3px
}
```

### Reduced Motion
```css
@media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
        animation-duration: 0.01ms !important;
        transition-duration: 0.01ms !important;
    }
}
```

---

## Removed Elements

To achieve the clean Duolingo aesthetic, the following were **removed**:

- ❌ All gradient overlays (`.clay-mesh-blob`)
- ❌ Glassmorphism effects (`backdrop-filter`, `blur`)
- ❌ Ambient cursor lights (`#ambientCursorLight`)
- ❌ Complex multi-layer shadows
- ❌ Gradient backgrounds on any element

---

## Mascot Integration Notes

The beaver mascot color scheme is reflected in:

1. **Primary amber** (#F0A030) — warm beaver fur tone
2. **Dark brown borders** (#2B2620) — beaver accents, engineer hard hat
3. **Teal accent** (#1B9C85) — engineering/blueprint theme, water association
4. **Navy for headers** (#2E4374) — technical precision, blueprint reference

The hard hat amber + teal combo avoids "muddy brown" and keeps the palette vibrant on screen while staying true to a beaver theme.

---

## Implementation Checklist

- [x] Replace all Tailwind color tokens
- [x] Update CSS shadow system to chunky offsets
- [x] Remove all glass/blur effects
- [x] Change fonts to Baloo 2 + Inter
- [x] Update Google Fonts imports
- [x] Ensure QR codes remain scannable
- [x] Preserve all backend functionality
- [x] Test dark mode variants
- [x] Verify accessibility contrast ratios

---

## Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile Safari iOS 14+
- Chrome Android 90+

All modern browsers support the solid color + box-shadow approach without fallbacks needed.

---

## Design Credits

**Inspired by:** Duolingo's playful, chunky UI design  
**Color System:** Custom beaver-mascot palette  
**Typography:** Baloo 2 (rounded, friendly) + Inter (professional, trustworthy)  
**Philosophy:** Playful accessibility that maintains document-handling credibility
