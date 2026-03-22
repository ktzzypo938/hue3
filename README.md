# 🎨 hue3 — Triadic Color Palette Advisor for Claude Code

> **Three colors. One system. Every mood.**

A [Claude Code](https://claude.ai/claude-code) skill that generates beautiful, production-ready color palettes from just three colors using triadic color theory.

**[Live Demo →](https://q27913588.github.io/hue3/)**

## Features

- **45 curated palettes** across 9 style categories, each with 5 carefully tuned schemes
- **Mood-first workflow** — describe a feeling, get matching colors (not the other way around)
- **Triadic color theory** — every palette built on proven three-color structures (triadic, split-complementary, analogous, temperature contrast)
- **60-30-10 ratio** — primary, secondary, accent roles with proper area distribution
- **Extended design system** — background, surface, text, border colors derived from the triadic base
- **WCAG accessibility check** — contrast ratios validated for every output
- **Dark mode conversion** — automatic light-to-dark transformation formulas
- **Live HTML preview** — generates a single-file preview website with your palette applied to real UI components
- **Bilingual color names** — English + Chinese/Japanese names for culturally-rooted palettes

## Style Categories

| Style | Keywords | Palettes |
|-------|----------|----------|
| 🌿 Nature | forest, ocean, earth, botanical, organic | 5 |
| 🔥 Trendy | social media, Gen Z, neon, gradient, bold | 5 |
| 🎩 Mature | elegant, luxury, refined, business, sophisticated | 5 |
| 🦅 American | classic USA, cowboy, sports, industrial, Ivy League | 5 |
| 🎌 Japanese | wabi-sabi, sakura, matcha, ukiyo-e, muji | 5 |
| 🏔️ Nordic | Scandinavian, minimal, hygge, fjord, aurora | 5 |
| 📻 Retro | 70s earth, 80s neon, 90s grunge, newspaper, pixel | 5 |
| 💻 Tech | AI, cyberpunk, terminal, space, startup | 5 |
| 🏮 Taiwanese | temple, night market, tea culture, indie, tin roof | 5 |

## Installation

### For all projects (recommended)

```bash
git clone https://github.com/q27913588/hue3.git
mkdir -p ~/.claude/skills/hue3
cp hue3/SKILL.md ~/.claude/skills/hue3/
cp -r hue3/references ~/.claude/skills/hue3/
```

### For a single project

```bash
git clone https://github.com/q27913588/hue3.git
mkdir -p .claude/skills/hue3
cp hue3/SKILL.md .claude/skills/hue3/
cp -r hue3/references .claude/skills/hue3/
```

## Usage

Once installed, the skill activates automatically when you mention colors, palettes, or visual design in Claude Code.

### Automatic trigger

Just describe what you need:

```
> I need a color scheme for a Japanese wabi-sabi style website
> Give me colors that feel like a Nordic winter cabin
> What palette would work for a cyberpunk dashboard?
```

### Manual trigger

```
> /color-palettes
```

### Example output

Each recommendation includes:

1. **Triadic base** — 3 colors with Hex, HSL, and role labels
2. **Extended system** — background, surface, text, border
3. **Rationale** — source palette, structure type, hue relationships
4. **Accessibility check** — WCAG AA contrast ratios
5. **HTML preview** — a single-file website you can open in any browser

## Preview Template

The skill includes `references/preview-template.html` — a responsive HTML page with:

- Color swatches (all 7 roles side by side)
- Hero section (primary color at scale)
- Navigation bar (secondary color)
- Card grid (surface + border + buttons)
- Form elements (focus states with accent color)
- Typography sample (text readability check)
- Dark mode toggle (one-click switch)

## File Structure

```
hue3/
├── SKILL.md                          # Main skill definition
├── README.md                         # This file
├── preview-all.html                  # Interactive gallery (all 45 palettes)
└── references/
    ├── color-theory.md               # Theory: HSL, triadic structures, 60-30-10, WCAG
    ├── preview-template.html         # HTML preview template
    ├── nature.md                     # 🌿 5 nature palettes
    ├── trendy.md                     # 🔥 5 trendy palettes
    ├── mature.md                     # 🎩 5 mature palettes
    ├── american.md                   # 🦅 5 American palettes
    ├── japanese.md                   # 🎌 5 Japanese palettes
    ├── nordic.md                     # 🏔️ 5 Nordic palettes
    ├── retro.md                      # 📻 5 retro palettes
    ├── tech.md                       # 💻 5 tech palettes
    └── taiwanese.md                  # 🏮 5 Taiwanese palettes
```

## Inspiration

This skill's three-color philosophy and mood-first approach were inspired by the Japanese design community's emphasis on constraint-driven palette design — particularly the idea that just three well-chosen colors can be more effective than a complex palette. The 60-30-10 ratio and triadic color structures are rooted in classic design education.

## License

MIT
