# AI Context — Diamond Sutra

## What this project is

A static mini site for studying the Diamond Sutra (金刚般若波罗蜜经), one of nine scripture sites under The Dharma Gate portal. Same architecture as HeartSutra — HTML + external CSS, no frameworks, 32 section pages.

## Current state (as of 2026-04-13)

- 32 section pages: one per chapter of the traditional 32-chapter Kumārajīva structure
- Index page: 32-card chapter grid, two lines per card (chapter number + Chinese title)
- Each card: Chinese phrase (bold) + short Chinese explanation (concept-focused, accessible register) + collapsible "English ▾" toggle containing English translation + full English commentary
- Summary at end of each section: Chinese by default, expandable via "English ▾" toggle
- Toggle button label: "English ▾" (consistent across all cards and summaries)
- Speech button label: 🔊 聆听经文 (targets Ting-Ting voice on iOS Safari, rate 0.9)
- Section heading: 逐句解释
- Summary heading: 总结 · Summary
- Portal bar and footer link back to DharmaGate

## Explanation card pattern

```html
<div class="explanation-card">
  <p class="line"><strong>Chinese phrase</strong></p>
  <p class="explanation-zh">Short Chinese explanation (2–3 sentences, concept-focused)</p>
  <button class="toggle-btn" onclick="toggleDetail(this)" aria-expanded="false">English ▾</button>
  <div class="detail-content" hidden>
    <p class="translation">English translation (red)</p>
    <p class="explanation">Full English commentary (grey, with analogies)</p>
  </div>
</div>
```

## Summary pattern

```html
<section class="summary">
  <h2>总结 · Summary</h2>
  <p class="summary-zh">Chinese summary</p>
  <button class="toggle-btn" onclick="toggleDetail(this)" aria-expanded="false">English ▾</button>
  <div class="detail-content" hidden>
    <p class="explanation">English summary</p>
  </div>
</section>
```

## Chapter card pattern (index.html)

```html
<a href="sectionN.html" class="chapter-card">
  <span class="chapter-num">第N章</span>
  <span class="chapter-zh">章名</span>
</a>
```

No English subtitle on the cards — removed by design.

## File structure

```
DiamondSutra/
  index.html         <- intro + 32-card chapter grid
  section1.html      <- Ch 1: 法会因由分
  section2.html      <- Ch 2: 善现启请分
  ...
  section32.html     <- Ch 32: 应化非真分
  css/
    style.css        <- all styles (red/saffron tokens), shared with HeartSutra
  docs/
    readme.md
    architecture.md
    ai-context.md    <- this file
    roadmap.md
```

## Design tokens

| Token | Value | Usage |
|-------|-------|-------|
| `--red` | `#b83232` | Primary accent |
| `--red-light` | `#d44e4e` | Hover states, headings |
| `--saffron` | `#c8820a` | Chapter number colour |
| `--saffron-lt` | `#e09c2a` | Portal bar links |
| `--ink` | `#1c0f0f` | Header/footer backgrounds |
| `--bg` | `#f7f0e6` | Page background |
| `--text` | `#2d1f1f` | Body text, Chinese explanations |
| `--muted` | `#7a6060` | English text, toggle buttons |
| `--border` | `#e0d0c8` | Card borders, dividers |

## Portal link

Portal bar and footer both link to: `https://lugh3456.github.io/DharmaGate/`

## GitHub repo

Live at: `https://lugh3456.github.io/DiamondSutra/`

## Notable content highlights

- Ch 10 (庄严净土分): 应无所住而生其心 — the sutra's most famous line; triggered the 6th Patriarch Huineng's awakening
- Ch 14 (离相寂灭分): Subhuti weeps; the six-image verse (dream, bubble, dew, lightning, shadow, foam)
- Ch 26 (法身非相分): 若以色见我，以音声求我，是人行邪道 — most quoted verse
- Ch 32 (应化非真分): Full circle closing — bodhicitta aspiration + six-image verse repeated
