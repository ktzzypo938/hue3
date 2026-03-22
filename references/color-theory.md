# Color Theory Reference — Three-Color Foundation System

A pure color theory toolkit. Provides the mathematical foundations, operational formulas, and extension methods for a three-color system.
Does not include style recommendations or palette examples — those belong in the respective style reference files.

---

## §1. Core Concept: Why Three Colors?

The three-color system offers the **highest balance and optimal visual tension** among color combination approaches:

- **Two colors** tend to be monotonous or overly contrasting
- **Three colors** provide sufficient variation without becoming chaotic
- **Four or more colors** require a high degree of control, otherwise they easily lose focus

Human vision has a natural sense of stability with triangular structures (similar to the rule-of-thirds in composition). Three-color palettes leverage this psychological trait to achieve the best balance between richness and harmony.

---

## §2. Color Wheel Basics (HSL Model)

All color theory operations use HSL (Hue-Saturation-Lightness) as the working model:

```
H (Hue)        = 0°–360° position on the color wheel
S (Saturation)  = 0% (gray) – 100% (pure color)
L (Lightness)   = 0% (black) – 100% (white)
```

### Color Wheel Quick Reference

| Angle | Color Name |
|-------|------------|
| 0°    | Red        |
| 30°   | Orange     |
| 60°   | Yellow     |
| 120°  | Green      |
| 180°  | Cyan       |
| 210°  | Sky Blue   |
| 240°  | Blue       |
| 270°  | Purple     |
| 300°  | Magenta    |
| 330°  | Rose       |

### Color Temperature Classification

```
Warm range:      H 0°–60° (Red, Orange, Yellow)
Cool range:      H 180°–270° (Cyan, Blue, Purple)
Transition range: H 60°–180° (Yellow-Green, Green, Cyan-Green) and H 270°–360° (Purple-Red, Rose)
Neutral:         Any hue with S < 10%
```

---

## §3. Three-Color Combination Types

### 3.1 Equidistant Triad (Triadic) — Preferred Approach

```
Three colors spaced 120° apart, forming an equilateral triangle
Color A (H)  →  Color B (H+120°)  →  Color C (H+240°)
```

**Characteristics:** Balanced, rich, vibrant

#### Classic Equidistant Triads

| Base     | A          | B              | C            |
|----------|------------|----------------|--------------|
| Red-based   | 0° Red     | 120° Green     | 240° Blue    |
| Orange-based | 30° Orange | 150° Cyan-Green | 270° Purple  |
| Yellow-based | 60° Yellow | 180° Cyan      | 300° Magenta |

### 3.2 Modified Triadic

Fine-tune the angles (±10°–15°) from the equidistant base to avoid overly "textbook" hue placement:

```
Color A (H)  →  Color B (H+110°)  →  Color C (H+230°)
Offsets within ±15° still maintain the triadic sense of balance
```

### 3.3 Split-Complementary Triad

```
Base color (H) + Complement neighbor (H+150°) + Complement neighbor (H+210°)
```

**Characteristics:** Retains complementary contrast but softer than pure complementary

### 3.4 Analogous Triad

```
Three adjacent colors, spaced 30° apart
Color A (H)  →  Color B (H+30°)  →  Color C (H+60°)
```

**Characteristics:** Harmonious, unified, low tension

### 3.5 Temperature Contrast Triad

```
1 warm color (0°–60°) + 1 cool color (180°–270°) + 1 neutral color (see §2 Color Temperature Classification)
```

**Characteristics:** Uses color temperature differences to create depth

---

## §4. The 60-30-10 Golden Ratio

The **area distribution rule** for three-color palettes, originating from interior design and widely applied across all visual design:

```
60% — Dominant color  → Background, large surface areas
30% — Secondary color → Containers, navigation, cards
10% — Accent color    → CTA buttons, icons, highlights
```

### Role Assignment Guide

| Role               | Suggested HSL Adjustment           | Purpose                    |
|--------------------|------------------------------------|----------------------------|
| Dominant (60%)     | Lower S to 10–30%, L to 90–97%    | Background stays unobtrusive |
| Secondary (30%)    | Medium S 40–60%, L 40–60%         | Structure remains identifiable |
| Accent (10%)       | Keep high S 70–100%, L 45–55%     | Instant focal point          |

### Generating Extended Colors

Extending from the three-color base to a complete design system:

```
Background   = Dominant color → S down to 5–10%, L up to 95–98%
Surface      = Dominant color → S down to 8–15%, L up to 88–93%
Text         = Secondary color → S down to 10–20%, L down to 10–20%
Border       = Secondary color → S down to 15%, L 60–70%
Hover/Focus  = Accent color → L ±8% for state changes
```

---

## §5. Three-Level Saturation & Lightness Control

Each hue requires multiple saturation/lightness variants in practice:

### 5.1 Three-Level Saturation System

```
High saturation (S: 70–100%) → Accent color, CTAs, icons
Mid saturation  (S: 30–60%)  → Secondary elements, headings, borders
Low saturation  (S: 5–20%)   → Backgrounds, large areas, surfaces
```

### 5.2 Five-Level Lightness Scale

Extend 5 lightness levels from each of the three base colors:

```
50  → L: 95%  Ultra-light (for backgrounds)
200 → L: 80%  Light (for hover states)
500 → L: 50%  Standard (primary color value)
700 → L: 30%  Dark (for text, borders)
900 → L: 15%  Ultra-dark (for headings, emphasized text)
```

---

## §6. Contrast & Accessibility (WCAG)

### 6.1 Standards

| Level | Normal Text | Large Text (≥18px bold / ≥24px) |
|-------|-------------|--------------------------------|
| AA    | ≥ 4.5:1     | ≥ 3.0:1                        |
| AAA   | ≥ 7.0:1     | ≥ 4.5:1                        |

### 6.2 Contrast Strategy Within the Three-Color System

```
Accent on Background    → Must be ≥ 4.5:1 (most common combination)
Secondary on Background → Recommended ≥ 4.5:1
Dominant on Background  → Must be ≥ 4.5:1 if used as text; ≥ 3.0:1 for decorative use only
Any two of the three    → All pairwise combinations should be ≥ 3.0:1
```

### 6.3 Quick Assessment Rules

```
Light background (L > 85%)  → Text color L must be < 40%
Dark background (L < 25%)   → Text color L must be > 70%
The mid-range is most risky → When background L is 40–60%, almost no hue can look good and pass at the same time
```

---

## §7. Dark Mode Conversion for the Three-Color System

Converting the three-color system from light mode to dark mode:

### Conversion Formulas

```
Light Mode → Dark Mode:

Background:  L 95–98%  →  L 8–12%,  S unchanged or +5%
Surface:     L 88–93%  →  L 14–20%, S unchanged or +5%
Primary:     L 45–55%  →  L 60–70%, S -10% (needs to be brighter on dark backgrounds)
Secondary:   L 40–50%  →  L 55–65%, S -10%
Accent:      L 50–55%  →  L 65–75%, S -5%
Text:        L 10–20%  →  L 85–95%, S -5%
```

### Important Notes

- Dark mode is not a simple inversion; saturation must be reduced to avoid eye strain
- Shadows in dark mode should use overlaid black with higher transparency
- Borders in dark mode should use brighter variants (L +10%)
