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
> For example: natural, trendy, sophisticated, American, Japanese, Nordic, retro, tech-forward, Taiwanese local?
> You can also describe something more specific, like "a coffee shop on a rainy day", "sunset by the sea", or "Tokyo street vibes".

### Step 2 — Match the Style and Load the Corresponding Reference File

Based on the user's described feel, match it to the most fitting **style category** and load the corresponding reference file:

| Style Category | Trigger Keywords (Chinese) | English Equivalents | Reference File |
|----------------|---------------------------|---------------------|----------------|
| 🌿 Nature | 森林、海洋、大地、植物、有機、田園、花園 | forest, ocean, earth, botanical, organic, pastoral, garden | `references/nature.md` |
| 🔥 Trendy | 潮流、社群、Z世代、IG風、大膽、街頭、時尚 | trendy, social media, Gen Z, IG-style, bold, street, fashion | `references/trendy.md` |
| 🎩 Mature | 沉穩、優雅、高端、奢華、精品、紳士、商務 | composed, elegant, premium, luxury, refined, gentleman, business | `references/mature.md` |
| 🦅 American | 美國、牛仔、運動、公路、校園、工業 | American, cowboy, sporty, highway, campus, industrial | `references/american.md` |
| 🎌 Japanese | 和風、侘寂、禪、可愛、動漫、抹茶、無印 | Japanese, wabi-sabi, zen, kawaii, anime, matcha, muji | `references/japanese.md` |
| 🏔️ Nordic | 斯堪地納維亞、極簡、Hygge、IKEA、白淨 | Scandinavian, minimalist, hygge, IKEA, clean white | `references/nordic.md` |
| 📻 Retro | 懷舊、70s、80s、90s、老派、膠卷、像素 | nostalgic, 70s, 80s, 90s, old-school, film, pixel | `references/retro.md` |
| 💻 Tech | 未來、AI、區塊鏈、賽博龐克、程式、新創 | futuristic, AI, blockchain, cyberpunk, coding, startup | `references/tech.md` |
| 🏮 Taiwanese | 廟宇、夜市、茶文化、文青、老街、鐵皮屋 | temple, night market, tea culture, literary, old street, tin-roof house | `references/taiwanese.md` |
| 🇰🇷 Korean | K-beauty、韓劇、韓服、首爾、咖啡廳 | K-beauty, K-drama, hanbok, Seoul, café culture | `references/korean.md` |
| 🏛️ Mediterranean | 聖托里尼、托斯卡尼、西班牙磁磚、蔚藍海岸 | Santorini, Tuscany, Spanish tile, Côte d'Azur | `references/mediterranean.md` |
| 🎨 Art Deco | 1920s、蓋茨比、幾何裝飾、金與黑、爵士時代 | 1920s, Gatsby, geometric, gold & black, Jazz Age | `references/artdeco.md` |
| 🪑 Mid-Century Modern | 50-60年代、Eames、原子時代、丹麥設計 | 1950s-60s, Eames, atomic age, Danish design | `references/midcentury.md` |
| 🇫🇷 French | 巴黎、浪漫、甜點色、薰衣草、小酒館 | Parisian, romantic, pâtisserie, lavender, bistro | `references/french.md` |
| 🌍 African | 部落、肯特布、草原、安卡拉印花、大地色 | tribal, kente, savanna, ankara print, earth tones | `references/african.md` |

**Rules:**
- Multiple style files can be loaded at once (e.g. user says "Japanese literary" → load japanese.md + the literary section from taiwanese.md)
- **Always also load** `references/color-theory.md` as the theoretical foundation
- If the user's description spans multiple styles, prioritize loading the 1–2 closest files

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

## Cross-Style Mixing

When the user's needs span multiple styles:

1. Pick the three-color foundation from the primary style file
2. Fine-tune saturation or lightness using the secondary style file
3. Explain the mixing logic in the "Why This Palette?" section

Example: "Nordic feel but with a touch of Taiwanese literary" → take the color structure from nordic.md, but swap the accent color for the kiln-fired orange from taiwanese.md TWN-04.

---

## Number of Palette Suggestions

- By default, provide **2–3 palettes**, drawn from different palettes within the same style file
- If the user's needs are very specific, a single best-fit palette is acceptable
- Every palette must include source attribution (which style file and which palette ID, or Custom Palette)
