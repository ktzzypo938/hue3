# 🎨 hue3 — Triadic Color Palette Advisor for Claude Code

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://claude.ai/claude-code)
[![Palettes](https://img.shields.io/badge/Palettes-60-ff6b6b)]()
[![Moods](https://img.shields.io/badge/Moods-12-4ecdc4)]()

> **Three colors. One system. Every mood.**

A [Claude Code](https://claude.ai/claude-code) skill that generates beautiful, production-ready color palettes from just three colors using triadic color theory.

**[Live Demo →](https://ktzzypo938.github.io/hue3/)** — Browse all 60 palettes with instant preview
**[Wikipedia Before & After →](https://ktzzypo938.github.io/hue3/wikipedia-before-after.html)** — See hue3 transform a familiar website

![hue3 preview — 60 palettes across 12 moods](preview.png)

### Wikipedia Before & After

Same page, different mood — 12 hue3 palettes applied to Wikipedia's layout:

| Before (Original) | After (Cyberpunk / DRM-01) |
|:--:|:--:|
| ![Wikipedia Original](wiki-before.png) | ![Wikipedia with Cyberpunk palette](wiki-after.png) |

**[Try it yourself →](https://ktzzypo938.github.io/hue3/wikipedia-before-after.html)** — Switch between 12 moods with one click

## Why hue3?

Most color tools give you a color wheel and leave you on your own. hue3 is different:

- **You describe a mood**, not a hex code — say "calm and serene" or "bold and energetic" and get a complete palette
- **Every palette is battle-tested** — curated with proper 60-30-10 ratio, not random generation
- **Instant design system** — not just 3 colors, but background, surface, text, border all derived
- **WCAG built-in** — accessibility isn't an afterthought, it's checked on every output

## Features

- **60 curated palettes** across 12 mood categories (11 moods + Japanese), each with 5 carefully tuned schemes
- **Mood-first workflow** — describe a feeling, get matching colors (not the other way around)
- **Triadic color theory** — every palette built on proven three-color structures (triadic, split-complementary, analogous, temperature contrast)
- **60-30-10 ratio** — primary, secondary, accent roles with proper area distribution
- **Extended design system** — background, surface, text, border colors derived from the triadic base
- **WCAG accessibility check** — contrast ratios validated for every output
- **Dark mode conversion** — automatic light-to-dark transformation formulas
- **Live HTML preview** — generates a single-file preview website with your palette applied to real UI components
- **Bilingual color names** — English + Chinese/Japanese names for culturally-rooted palettes

## Mood Categories

| Mood | Keywords | Palettes |
|------|----------|----------|
| 🌊 Calm | serene, meditation, spa, peaceful, healing | 5 |
| ⚡ Bold | energetic, dynamic, sports, impact, confident | 5 |
| 🎀 Romantic | soft, tender, dreamy, sweet, wedding, pastel | 5 |
| 👑 Luxurious | premium, elegant, opulent, refined, exclusive | 5 |
| 🌿 Earthy | natural, organic, forest, botanical, pastoral | 5 |
| 🎮 Playful | fun, joyful, creative, whimsical, colorful | 5 |
| 🏢 Professional | corporate, business, trustworthy, reliable | 5 |
| 🔮 Dramatic | dark, edgy, cinematic, cyberpunk, gaming | 5 |
| ☕ Cozy | warm, homey, autumnal, fireplace, café | 5 |
| ⬜ Minimal | modern, clean, simple, whitespace, pure | 5 |
| 🎌 Japanese | wabi-sabi, sakura, matcha, ukiyo-e, anime | 5 |

## Quick Start

### Installation

```bash
git clone https://github.com/ktzzypo938/hue3.git
mkdir -p ~/.claude/skills/hue3
cp hue3/SKILL.md ~/.claude/skills/hue3/
cp -r hue3/references ~/.claude/skills/hue3/
```

That's it. Open any Claude Code session and start asking about colors.

### Usage

The skill activates automatically when you mention colors, palettes, or visual design:

```
> I need a calm, serene color scheme for a meditation app
> Give me something bold and energetic for a sports brand
> What palette would work for a dramatic cyberpunk dashboard?
> Make it feel cozy, like a fireside café
```

Or trigger it manually:

```
> /color-palettes
```

### What you get

Each recommendation includes:

1. **Triadic base** — 3 colors with Hex, HSL, and role labels
2. **Extended system** — background, surface, text, border
3. **Rationale** — source palette, structure type, hue relationships
4. **Accessibility check** — WCAG AA contrast ratios
5. **HTML preview** — a single-file website you can open in any browser

## Preview Gallery

Open `preview-all.html` in your browser to browse all 60 palettes with a live UI preview. Use **↑↓ arrow keys** to quickly flip through palettes.

The skill also includes `references/preview-template.html` — a single-palette preview with:

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
├── LICENSE                           # MIT License
├── preview-all.html                  # Interactive gallery (all 60 palettes)
├── wikipedia-before-after.html       # Wikipedia reskin demo (12 moods)
├── index.html                        # GitHub Pages entry point
├── preview.png                       # Social preview image
├── wiki-before.png                   # Wikipedia demo — before screenshot
├── wiki-after.png                    # Wikipedia demo — after screenshot
└── references/
    ├── color-theory.md               # Theory: HSL, triadic structures, 60-30-10, WCAG
    ├── preview-template.html         # Single-palette HTML preview template
    ├── calm.md                       # 🌊 5 calm/serene palettes
    ├── bold.md                       # ⚡ 5 bold/energetic palettes
    ├── romantic.md                   # 🎀 5 romantic/soft palettes
    ├── luxurious.md                  # 👑 5 luxurious/sophisticated palettes
    ├── earthy.md                     # 🌿 5 earthy/natural palettes
    ├── playful.md                    # 🎮 5 playful/vibrant palettes
    ├── professional.md               # 🏢 5 professional/trustworthy palettes
    ├── dramatic.md                   # 🔮 5 dramatic/edgy palettes
    ├── cozy.md                       # ☕ 5 cozy/warm palettes
    ├── minimal.md                    # ⬜ 5 minimal/modern palettes
    └── japanese.md                   # 🎌 5 Japanese palettes
```

## Contributing

Contributions are welcome! Here are some ways you can help:

- **Add new mood categories** — Nostalgic, Futuristic, Rebellious, Ethereal...
- **Improve existing palettes** — better color choices, more refined harmony
- **Add new features to SKILL.md** — gradient generation, color blindness simulation
- **Translate** — add more bilingual color names or translate the skill workflow

Please open an issue first to discuss what you'd like to change.

## Inspiration

This skill's three-color philosophy and mood-first approach were inspired by the Japanese design community's emphasis on constraint-driven palette design — particularly the idea that just three well-chosen colors can be more effective than a complex palette. The 60-30-10 ratio and triadic color structures are rooted in classic design education.

## License

[MIT](LICENSE)
