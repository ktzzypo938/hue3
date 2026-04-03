---
name: color-palettes
description: >
  Triadic color palette advisor. Triggers when user mentions color, palette, color scheme, hex codes, color matching,
  or visual design recommendations. Also triggers when user describes a mood, emotion, or aesthetic and wants matching
  colors — e.g. "calm", "professional", "Japanese wabi-sabi", "energetic startup".
  Always use this skill before recommending any colors in UI, branding, illustration, or presentation contexts.
---

# Triadic Color Palette Advisor

A color advisor built on **Triadic Color Theory**. All palette recommendations start from three colors and expand into a complete design system.

## Language Rules

- **Reply in the user's language** — if the user asks in English, reply entirely in English; if in Chinese, reply in Chinese
- Color role labels in the output template use bilingual labels (e.g. "Primary / 主導 60%")
- Preview HTML UI text is always in English (the template itself is already in English)
- Style reference files are written in Chinese; translate their content into the user's language when replying

## Core Principle

> **Three-Color Rule:** Every palette is built on three color roles — Primary, Secondary, Accent.
> Using the **60-30-10 area distribution**, three colors can cover all design needs.

---

## Workflow

### Step 1 — Ask the User for the Desired "Feel"

**Before creating any palette, confirm the user's desired mood or direction.**

If the user has already stated a clear mood or style keyword, skip directly to Step 2.
If not clear enough, ask proactively:

> What "feel" do you want this palette to convey?
> For example: calm, bold, romantic, luxurious, earthy, playful, professional, dramatic, cozy, minimal, or Japanese?
> You can also describe something more specific, like "a coffee shop on a rainy day", "sunset by the sea", or "Tokyo street vibes".

### Step 2 — Match the Mood and Load the Corresponding Reference File

Based on the user's described feel, match it to the most fitting **mood category** and load the corresponding reference file:

| Mood Category | Trigger Keywords (Chinese) | English Equivalents | Reference File |
|---------------|---------------------------|---------------------|----------------|
| 🌊 Calm | 寧靜、冥想、療癒、SPA、放鬆、安靜、平和 | calm, serene, meditation, healing, spa, relax, peaceful | `references/calm.md` |
| ⚡ Bold | 活力、大膽、能量、運動、衝擊、自信、熱情 | bold, energetic, dynamic, sports, impact, confident, passionate | `references/bold.md` |
| 🎀 Romantic | 浪漫、柔和、溫柔、夢幻、甜美、粉嫩、婚禮 | romantic, soft, tender, dreamy, sweet, pastel, wedding | `references/romantic.md` |
| 👑 Luxurious | 奢華、高端、精品、優雅、尊貴、沉穩、頂級 | luxurious, premium, refined, opulent, elegant, exclusive | `references/luxurious.md` |
| 🌿 Earthy | 自然、大地、有機、森林、田園、泥土、植物 | natural, earthy, organic, forest, pastoral, botanical | `references/earthy.md` |
| 🎮 Playful | 繽紛、歡樂、活潑、創意、童趣、彩色、派對 | playful, fun, joyful, creative, whimsical, colorful, party | `references/playful.md` |
| 🏢 Professional | 專業、企業、商務、信任、可靠、銀行、科技 | professional, corporate, business, trustworthy, reliable | `references/professional.md` |
| 🔮 Dramatic | 戲劇、暗黑、叛逆、電影感、賽博龐克、電競 | dramatic, dark, edgy, cinematic, cyberpunk, gaming | `references/dramatic.md` |
| ☕ Cozy | 溫馨、溫暖、家的感覺、秋天、壁爐、咖啡廳 | cozy, warm, homey, autumnal, fireplace, café | `references/cozy.md` |
| ⬜ Minimal | 極簡、現代、乾淨、無印、簡約、留白、純粹 | minimal, modern, clean, muji, simple, whitespace, pure | `references/minimal.md` |
| 🎌 Japanese | 和風、侘寂、禪、可愛、動漫、抹茶、浮世繪 | Japanese, wabi-sabi, zen, kawaii, anime, matcha, ukiyo-e | `references/japanese.md` |

**Rules:**
- Multiple mood files can be loaded at once (e.g. user says "cozy but minimal" → load cozy.md + minimal.md)
- **Always also load** `references/color-theory.md` as the theoretical foundation
- If the user's description spans multiple moods, prioritize loading the 1–2 closest files

### Step 3 — Find Matching Palettes from the Reference Files

Browse the loaded reference files and find **2–3 palettes that best match the user's desired feel**.

Matching criteria:
1. Does the palette's "mood" description align with the user's feel?
2. Does the three-color structure match the user's implied preference?
3. Does the saturation/lightness match the expected visual intensity?

### Step 4 — If No Perfect Match, Generate from Theory

If none of the reference file palettes fit the user's feel closely enough, generate from scratch using this process:

1. Anchor the primary hue H° (derived from the closest style file palette, or specified by the user)
2. Select a triadic structure type from `color-theory.md` Section 3
3. Assign roles per Section 4's 60-30-10 distribution
4. Generate saturation/lightness variants per Section 5
5. Verify contrast per Section 6

After generating, label the palette as `[Custom Palette]` and explain the derivation logic.

### Step 5 — Output the Palette

For each palette, output in the following format (before outputting, verify: three-color HSL + Hex labels are complete, 60-30-10 distribution is sensible, WCAG AA is met, source attribution is specific):

```
## [Palette Name] — [Style Category] [Palette ID]

### Three-Color Foundation
| Role | Hex | HSL | Color Name |
|------|-----|-----|------------|
| 🔵 Primary / 主導 60% | #XXXXXX | H° S% L% | Name |
| 🟢 Secondary / 輔助 30% | #XXXXXX | H° S% L% | Name |
| 🔴 Accent / 強調 10% | #XXXXXX | H° S% L% | Name |

### Extended System
| Role | Hex | Usage |
|------|-----|-------|
| Background | #XXXXXX | Page background |
| Surface | #XXXXXX | Cards, containers |
| Text | #XXXXXX | Body text |
| Border | #XXXXXX | Borders, dividers |

### Why This Palette?
- **Style source:** [nature.md NAT-03] or [Custom Palette]
- **Structure type:** [Equidistant triad / Split-complementary / Analogous triad / ...]
- **Hue relationship:** A(H°) → B(H°) → C(H°), interval X°
- **Mood:** ...
- **Suitable for:** ...

### Accessibility Check
| Combination | Contrast Ratio | WCAG |
|-------------|---------------|------|
| Text on Background | X.X:1 | AA ✓ / ✗ |
| Accent on Background | X.X:1 | AA ✓ / ✗ |
| Accent on Surface | X.X:1 | AA ✓ / ✗ |
```

### Step 5.5 — Generate a Preview Page

Once the user confirms which palette they want to preview, use `references/preview-template.html` as the skeleton to generate a preview HTML:

1. Copy the template contents
2. Replace `{{PALETTE_NAME}}` with the palette name
3. Replace the CSS variable placeholders in `:root` with actual Hex values:

| Placeholder | Corresponding Role |
|-------------|-------------------|
| `{{PRIMARY}}` | Primary color |
| `{{SECONDARY}}` | Secondary color |
| `{{ACCENT}}` | Accent color |
| `{{BACKGROUND}}` | Background |
| `{{SURFACE}}` | Surface |
| `{{TEXT}}` | Text |
| `{{BORDER}}` | Border |
| `{{ACCENT_HOVER}}` | Accent hover state (Accent L ±8%) |

4. If a dark mode palette exists, also fill in the `{{DARK_*}}` variables in the `.dark` block; if there is no dark mode, remove the entire `.dark {}` block
5. Output the complete HTML file so the user can open it directly in a browser

### Step 6 — Dark Mode (Optional)

If the user needs dark mode, adjust according to the conversion formulas in `color-theory.md` Section 7.
Output a separate dark mode palette table and fill it into the preview HTML's `.dark` block.

### Step 7 — Apply to a Deliverable (Optional)

If the user has an existing deliverable (presentation, UI, document), proactively offer to apply the palette to it.

---

## Cross-Mood Mixing

When the user's needs span multiple moods:

1. Pick the three-color foundation from the primary mood file
2. Fine-tune saturation or lightness using the secondary mood file
3. Explain the mixing logic in the "Why This Palette?" section

Example: "cozy but minimal" → take the warm tones from cozy.md COZ-02, but reduce saturation toward minimal.md MIN-03's restraint.

---

## Number of Palette Suggestions

- By default, provide **2–3 palettes**, drawn from different palettes within the same mood file
- If the user's needs are very specific, a single best-fit palette is acceptable
- Every palette must include source attribution (which mood file and which palette ID, or Custom Palette)
