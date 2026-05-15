# Font-Size Audit — `index.html`

Base body size: **15 px** (`html, body` at L66). All ratios below are relative to 15 px.

> Goal: pick a single ratio `r` so every step in the scale is `15 × r^n`. Most pleasing scales sit in **1.20 – 1.333** for body-heavy content, **1.414 – 1.618** for editorial/marketing.

---

## 1 · The full type scale, sorted (smallest → largest)

| Size (px) | Ratio vs 15px | Used by | Lines |
|---:|---:|---|---|
| **10**   | 0.67× | `.team-card .role`, `.pipeline-eyebrow`, `.issue-card .num`, `.future-card .num`, `.cd-side-title`, `.cd-mid-eyebrow`, `.video-header .speed-tag`, `.os-hud .cell .lbl`, `.pipeline-topic .m` | 369, 453, 749, 749, 922, 984, 807, 1221, 613 |
| **11**   | 0.73× | `.eyebrow`, `.brand-mark`, `.hero-pill`, `.code-meta`, `.code-copy`, `.stat .lbl`, `thead th`, `.state .num`, `.demo-block .demo-tag`, `.pill`, `.cd-controls`, `.cd-stage-icon`, `.cd-stage-meta`, `.cd-mid-thought`, `.cd-code-meta`, `.hero-sim-pill`, `.hero-sim-hint`, `.os-btn`, `.os-hint`, `.dual-arch .col-title`, `.pipeline-live` | 130, 102, 157, 258, 284, 314, 698, 717, 769, 832, 880, 950, 969, 1002, 1064, 1103, 1117, 1157, 1197, 399, 480 |
| **12**   | 0.80× | `.code-tab`, `.pipeline-meta`, `.pipeline-topic .t`, `td code`, `.video-header`, `.cd-title`, `.cd-mid-file`, `.cd-code-tab`, `.os-title`, `.os-hud` | 235, 531, 607, 700, 794, 875, 1023, 1051, 1148, 1210 |
| **12.5** | 0.83× | `.dual-arch .step .topic`, `.shared-bus code, p code, td code, .step code` | 414, 431 |
| **13**   | 0.87× | `.nav ul a`, `.nav .nav-cta`, `pre.code`, `.card p`, `.card ul.tight`, `.team-card .avatar`, `.team-card .bio`, `.team-card .contrib`, `.state .desc`, `.issue-card .fix`, `.future-card .desc`, `.pipeline-name`, `.pipeline-foot`, `.pipeline-mode`, `.video-meta`, `footer`, `.cd-mid-prompt`, `inline notes` | 109, 115, 271, 344, 345, 364, 378, 382, 725, 757, 757, 525, 622, 463, 820, 846, 997, 2532 |
| **13.5** | 0.90× | `.dual-arch .step`, `.shared-bus`, `.table-wrap`, `.cd-stage-name`, `.cd-mid-body` | 410, 427, 691, 964, 1013 |
| **14**   | 0.93× | `.brand`, `.btn`, `.card p / ul.tight`, `.pipeline-mode arrow`, `.cd-code-tab .x`, `.os-hud .cell .val`, `.os-hud .state-cell .name` | 94, 184, 344, 419, 1059, 1225, 1239 |
| **15**   | 1.00× | `html, body` (base), `.card .icon`, `.issue-card .head`, `.future-card .head` | 66, 340, 754 |
| **16**   | 1.07× | `.card h3`, `.team-card .name`, `.state .name` | 343, 374, 721 |
| **17**   | 1.13× | `p.lede`, `.hero-sub` | 139, 176 |
| **18**   | 1.20× | `.cd-mid-title` (Cursor demo subtitle) | 989 |
| **20**   | 1.33× | `h3` (global) | 137 |
| **22**   | 1.47× | `.demo-block h3` | 764 |
| **30**   | 2.00× | `.stat .num` (hero stats) | 310 |
| **28–44** (fluid) | 1.87× – 2.93× | `h2` — `clamp(28px, 3.4vw, 44px)` | 135 |
| **38–68** (fluid) | 2.53× – 4.53× | `h1.title` — `clamp(38px, 5.8vw, 68px)` | 170 |

---

## 2 · Grouped by role

### Headings
| Token | Size | Line | Notes |
|---|---|---|---|
| H1 hero title | `clamp(38px, 5.8vw, 68px)` | 170 | only used once, in hero |
| H2 section | `clamp(28px, 3.4vw, 44px)` | 135 | every section title |
| H3 (global) | 20 px | 137 | "Aim · …", "Where this is useful", etc. |
| H3 inside `.card` | 16 px | 343 | shrinks 20 → 16 inside cards |
| H3 inside `.demo-block` | 22 px | 764 | bumps 20 → 22 for demo titles |
| Cursor-demo subtitle | 18 px | 989 | `.cd-mid-title` |
| Big stat number | 30 px | 310 | hero stats only |

**Current H2 ↔ H3 gap (desktop):** 44 → 20 = **2.20× drop**. That's why H3 feels small to you. Healthy editorial scales drop ~1.4× – 1.6× between tiers.

### Body / lede
| Token | Size | Line |
|---|---|---|
| Base body | 15 px | 66 |
| Lede paragraph | 17 px | 139 |
| Hero sub-paragraph | 17 px | 176 |

### Card content
| Token | Size | Line |
|---|---|---|
| `.card h3` | 16 px | 343 |
| `.card p` | 14 px | 344 |
| `.card ul.tight` | 14 px | 345 |
| `.card .icon` | 15 px | 340 |

### Team cards
| Token | Size | Line |
|---|---|---|
| Avatar text | 13 px | 364 |
| Role tag | 10 px | 369 |
| Name | 16 px | 374 |
| Bio | 13 px | 378 |
| Contributions | 13 px | 382 |

### State machine (Operation)
| Token | Size | Line |
|---|---|---|
| State number | 11 px | 717 |
| State name | 16 px | 721 |
| State desc | 13 px | 725 |

### Issue / future cards
| Token | Size | Line |
|---|---|---|
| Number | 10 px | 749 |
| Head | 15 px | 754 |
| Fix / desc | 13 px | 757 |

### Demos
| Token | Size | Line |
|---|---|---|
| `.demo-block h3` | 22 px | 764 |
| `.demo-tag` | 11 px | 769 |
| Video header | 12 px | 794 |
| Video meta | 13 px | 820 |
| Speed tag | 10 px | 807 |

### Hero stats
| Token | Size | Line |
|---|---|---|
| `.stat .num` | 30 px | 310 |
| `.stat .lbl` | 11 px | 314 |

### Nav
| Token | Size | Line |
|---|---|---|
| `.brand` | 14 px | 94 |
| `.brand-mark` | 11 px | 102 |
| `.nav ul a` | 13 px | 109 |
| `.nav .nav-cta` | 13 px | 115 |
| Mobile nav ul | 13 px | 2532 |

### Tables
| Token | Size | Line |
|---|---|---|
| `.table-wrap` (cell) | 13.5 px | 691 |
| `thead th` | 11 px | 698 |
| `td code` | 12 px | 700 |

### Code panels (Cursor-style demo)
| Token | Size | Line |
|---|---|---|
| `.cd-title` | 12 px | 875 |
| `.cd-controls` | 11 px | 880 |
| `.cd-side-title` | 10 px | 922 |
| `.cd-stage-icon` | 11 px | 950 |
| `.cd-stage-name` | 13.5 px | 964 |
| `.cd-stage-meta` | 11 px | 969 |
| `.cd-mid-eyebrow` | 10 px | 984 |
| `.cd-mid-title` | 18 px | 989 |
| `.cd-mid-prompt` | 13 px | 997 |
| `.cd-mid-thought` | 11 px | 1002 |
| `.cd-mid-body` | 13.5 px | 1013 |
| `.cd-mid-file` | 12 px | 1023 |
| `.cd-code-tab` | 12 px | 1051 |
| `.cd-code-tab .x` | 14 px | 1059 |
| `.cd-code-meta` | 11 px | 1064 |
| `pre.code` | 13 px | 271 |

### Architecture pipeline + dual-arch
| Token | Size | Line |
|---|---|---|
| `.dual-arch .col-title` | 11 px | 399 |
| `.dual-arch .step` | 13.5 px | 410 |
| `.dual-arch .step .topic` | 12.5 px | 414 |
| `.dual-arch .arrow` | 14 px | 419 |
| `.shared-bus` | 13.5 px | 427 |
| code inside `.step`/`.shared-bus`/`td`/`p` | 12.5 px | 431 |
| `.pipeline-eyebrow` | 10 px | 453 |
| `.pipeline-mode` | 13 px | 463 |
| `.pipeline-live` | 11 px | 480 |
| `.pipeline-name` | 13 px | 525 |
| `.pipeline-meta` | 12 px | 531 |
| `.pipeline-topic .t` | 12 px | 607 |
| `.pipeline-topic .m` | 10 px | 613 |
| `.pipeline-foot` | 13 px | 622 |

### Hero sim / OS-style frame
| Token | Size | Line |
|---|---|---|
| `.hero-pill` | 11 px | 157 |
| `.hero-sub` | 17 px | 176 |
| `.hero-sim-pill` | 11 px | 1103 |
| `.hero-sim-hint` | 11 px | 1117 |
| `.os-title` | 12 px | 1148 |
| `.os-btn` | 11 px | 1157 |
| `.os-hint` | 11 px | 1197 |
| `.os-hud` | 12 px | 1210 |
| `.os-hud .cell .lbl` | 10 px | 1221 |
| `.os-hud .cell .val` | 14 px | 1225 |
| `.os-hud .state-cell .name` | 14 px | 1239 |

### Misc
| Token | Size | Line |
|---|---|---|
| `.eyebrow` (section tag) | 11 px | 130 |
| `.btn` | 14 px | 184 |
| `.code-tab` | 12 px | 235 |
| `.code-meta` | 11 px | 258 |
| `.code-copy` | 11 px | 284 |
| `.pill` | 11 px | 832 |
| `footer` | 13 px | 846 |

---

## 3 · The problem your eyes are picking up

The page has **too many distinct sizes** clustered around 10–15 px (eight values: 10, 11, 12, 12.5, 13, 13.5, 14, 15 — that's ~8 micro-tiers within a 5-px band) **and too big a leap from 20 → 44** between H3 and H2. The result: small-text noise + a heading hierarchy that feels broken.

Diagnosis at a glance:
- **Body cluster:** 10 / 11 / 12 / 12.5 / 13 / 13.5 / 14 / 15 → collapse to 3–4 values.
- **Heading gap:** H3 = 20, H2 = 44 → ratio of 2.20 is too aggressive. Either lift H3 or lower H2.
- **No clear semantic owners:** 13 and 13.5 are used interchangeably; 14 px is used for both `.btn` and `.card p` (very different roles).

---

## 4 · Pick a ratio · what 15 px base gives you

Pure geometric scales — each step is `15 × r^n`, rounded to nearest 0.5 px.

| n | r = 1.125 (Major Second) | r = 1.200 (Minor Third) | r = 1.250 (Major Third) | r = 1.333 (Perfect Fourth) | r = 1.414 (Aug. Fourth) | r = 1.500 (Perfect Fifth) | r = 1.618 (Golden) |
|---:|---:|---:|---:|---:|---:|---:|---:|
| −2 | 11.9 | 10.4 | 9.6 | 8.4 | 7.5 | 6.7 | 5.7 |
| −1 | 13.3 | 12.5 | 12.0 | 11.3 | 10.6 | 10.0 | 9.3 |
| **0 (base)** | **15** | **15** | **15** | **15** | **15** | **15** | **15** |
| 1 | 16.9 | 18.0 | 18.8 | 20.0 | 21.2 | 22.5 | 24.3 |
| 2 | 19.0 | 21.6 | 23.4 | 26.7 | 30.0 | 33.8 | 39.4 |
| 3 | 21.4 | 25.9 | 29.3 | 35.6 | 42.4 | 50.6 | 63.7 |
| 4 | 24.0 | 31.1 | 36.6 | 47.4 | 60.0 | 75.9 | 103.0 |

**My recommendation for a content-heavy technical page like this:** `r = 1.250` (Major Third).
- Caption: **12 px**
- Body: **15 px**
- H3 free: **19 px** → round to **19** (or 18 to match `.cd-mid-title`)
- H3-big (demo): **23 px**
- H2: **29 px** floor → **47 px** desktop (still fluid; closer to the lede)
- H1: **59 px** → keep your existing `clamp(38, 5.8vw, 68)`

That gives a H2/H3 ratio of ~**1.5–1.85** instead of 2.20 — your eyes will feel the difference immediately.

**If you want it more editorial/dramatic:** `r = 1.333`. H3 free = **20 px** (current), H2 = **27–47 px** (lower the cap from 44 → ~47, raise the floor from 28 → 27). But then either bump H3 to **22 px** or accept the 2.0–2.2× gap as intentional.

**If you want minimal change:** keep `r ≈ 1.250` only on the heading tier:
- H3 (free): 20 → **22 px**
- H3 (card): 16 → **18 px**
- H2 cap: 44 → **40 px**
- H2 floor: 28 → **30 px**
That's a 4-line edit and most of the "tightness" complaint goes away.

---

## 5 · Suggested type-token consolidation (optional)

Collapse the 8-value 10–15 band into 4 semantic tokens:

| Token | Replaces | Use for |
|---|---|---|
| `--fs-micro` = 11 px | 10, 11, 12 | eyebrows, code metadata, table headers |
| `--fs-cap` = 12.5 px | 12.5, 13 | nav, table cells, captions, inline code |
| `--fs-body` = 15 px | 13.5, 14, 15 | paragraphs, buttons, cards |
| `--fs-lede` = 17 px | 17 | leads, hero sub |
| `--fs-h3` = 22 px (or 20) | 18, 20, 22 | section subheads, demo titles |
| `--fs-h2` = clamp(30, 3vw, 42) | unchanged | section titles |
| `--fs-h1` = clamp(40, 5.8vw, 68) | unchanged | hero |

Drop these into `:root` and replace the inline `font-size: 13px` etc. with `font-size: var(--fs-cap)`. The page will feel deliberate instead of accidental.

---

*Generated from `index.html` on the `vanilla-r-2` branch. Lines refer to that file.*

---

## 6 · Section-to-section vertical spacing

The empty space between two sections (e.g. §02 Introduction → §03 Motivation) is controlled by a single CSS custom property.

### Where it lives

`index.html` — **L56** (inside the `:root` block):

```css
--section-gap: 96px;
```

Applied at **L124–L125**:

```css
section { padding: var(--section-gap) 0; }
section + section { padding-top: 0; }   /* prevents double-stacking when two sections are adjacent */
```

### Why §02 → §03 feels wide

The visible gap between two sections separated by an `<hr class="section-divider" />` is:

```
bottom padding of §02   = 96 px
hr.section-divider     ≈  1 px (border, margin: 0 — L141-144)
top padding of §03     = 96 px
────────────────────────────────
total visible gap      ≈ 193 px
```

Almost 200 px of vertical air between every pair of sections. That's why the page reads as "wide-spaced" — every section pair contributes that much whitespace, and the page has 9+ section pairs.

### How to tighten it · single-knob fix

Change **L56** only. Every section responds uniformly.

| Target feel | New value | Resulting gap (px) | Total page shorter by (× 9 pairs) |
|---|---:|---:|---:|
| Same look, just tighter | `72px` | ~145 | ~432 px |
| Noticeably denser, still editorial | `56px` | ~113 | ~720 px |
| Compact / technical-doc feel | `40px` | ~81 | ~1008 px |
| Very dense (matches `.section-divider` weight) | `32px` | ~65 | ~1152 px |

**Recommendation: `56px`.** That keeps clear "this is a new section" rhythm without burning a full screen of vertical space between every block. Pairs nicely with the §3 type-scale recommendation (`r = 1.250`).

### When you want to tighten *only one* pair

Use an adjacent-sibling override; don't touch the global token.

```css
/* Example: tighten ONLY the gap between §02 Introduction and §03 Motivation */
#motivation { padding-bottom: 40px; }
#impact     { padding-top: 40px; }
```

(Or, if there's an `<hr>` between them, you can leave it; the padding above and below the hr is what you're trimming.)

### Related vertical-spacing knobs in the same file

Other places that contribute to page rhythm (don't touch unless the section-gap fix isn't enough):

| Selector | Line | Current | What it controls |
|---|---:|---|---|
| `.container` `padding: 0 28px` | 123 | 28 px | horizontal page gutter (not vertical) |
| `h2` `margin: 0 0 16px` | 135 | 16 px below H2 | space from section title to first paragraph |
| `h3` `margin: 24px 0 10px` | 137 | 24 / 10 px | space around H3 subheads inside a section |
| `p` `margin: 0 0 12px` | 138 | 12 px | space between paragraphs |
| `hr.section-divider` `margin: 0` | 141-144 | 0 | the divider itself is flush — fine as is |
| `.stats` `margin-top: 64px` | 300 | 64 px | space from hero text to the stats strip |
| inline `style="margin-top: 48px"` on some H3s | various | 48 px | one-off section breaks (e.g. "Aim · …", "Where this kind of system…") |

If after lowering `--section-gap` you still see one specific spot looking too airy, that's almost certainly a `style="margin-top: 48px"` inline override on an H3. Grep for it and trim that one tag.

---

## 7 · Reading and editing the Layout + Heading block

The CSS you pasted lives at **`index.html:122–140`**. Here it is again, annotated line-by-line so you can edit with confidence.

```css
/* ───────────── Layout ───────────── */
.container { max-width: var(--page-max); margin: 0 auto; padding: 0 28px; }   /* 123 */
section { padding: var(--section-gap) 0; }                                     /* 124 */
section + section { padding-top: 0; }                                          /* 125 */

.eyebrow {                                                                     /* 127 */
  display: inline-block;
  font-family: var(--font-mono);
  font-size: 11px; letter-spacing: 0.08em; text-transform: uppercase;
  color: var(--muted-stone); font-weight: 500;
  margin-bottom: 12px;
}
h1, h2, h3 { color: var(--deep-shadow); font-weight: 500; letter-spacing: -0.02em; }   /* 134 */
h2 { font-size: clamp(28px, 3.4vw, 44px); line-height: 1.1; margin: 0 0 16px;
     letter-spacing: -0.03em; max-width: 820px; }                              /* 135-136 */
h3 { font-size: 20px; line-height: 1.25; margin: 24px 0 10px; letter-spacing: -0.015em; }   /* 137 */
p  { color: var(--inkwell); max-width: 720px; margin: 0 0 12px; }              /* 138 */
p.lede { color: var(--muted-stone); font-size: 17px; line-height: 1.55; max-width: 720px; }   /* 139 */
```

### What each rule does, in plain English

| Selector | What it does | Tunable knobs |
|---|---|---|
| `.container` | The narrow column every section's content sits inside. `max-width` caps the column at `--page-max` (1240 px). `margin: 0 auto` centers that column on the page. `padding: 0 28px` adds 28 px of horizontal gutter so text never touches the screen edge on mobile. | `--page-max` (L55) — narrower = more editorial; wider = more dashboard.<br>`28px` gutter — bump to `36-40px` on wide screens for more breathing room. |
| `section { padding: ...}` | Top + bottom space inside each section. Pulls from `--section-gap`. | `--section-gap` at L56. See §6 above. |
| `section + section { padding-top: 0 }` | If two `<section>` tags are direct siblings (no `<hr>` between), the second one drops its top padding so they don't double-stack. | Usually leave alone. |
| `.eyebrow` | The "02 · Introduction" tag above each H2. `display: inline-block` means it sits on its own line but only takes up its own width. Mono font, tiny (11 px), uppercase, gray. | `font-size: 11px` — bump to 12 if it's hard to read.<br>`margin-bottom: 12px` — gap to the H2 below. |
| `h1, h2, h3` (shared) | One line that sets dark color, medium weight, and tight letter-spacing for all three headings. | `letter-spacing: -0.02em` — less negative = looser/more friendly. |
| `h2` | The big section title. Fluid size: 28 px on phones, scales to 44 px on wide screens via `clamp(min, ideal, max)`. `line-height: 1.1` keeps multi-line H2s tight. `margin: 0 0 16px` = 16 px below it. `max-width: 820px` caps its width so it never spans the whole page. | `clamp(28px, 3.4vw, 44px)` — raise the 44 to 52 if you want it more imposing; raise the 28 to 32 if it feels small on mobile. |
| `h3` | Subsection title. Fixed 20 px. `margin: 24px 0 10px` = 24 px above, 10 px below. | `font-size: 20px` — bump to 22-24 if H3s feel weak vs H2 (see §1 of this file). |
| `p` | Default paragraph. Dark text, capped at 720 px wide (long lines kill readability), 12 px space below. | `max-width: 720px` — narrower (e.g. 640) reads like a longform article; wider (820) reads more like docs. |
| `p.lede` | The opening paragraph of a section. Same 720 px cap, but muted gray (`--muted-stone`) and larger (17 px) so it visually sits between the H2 and body. | Same as above. |

### How to test a change without breaking things

1. Open the site in a browser, open DevTools (`Cmd+Opt+I`).
2. Click on the line in DevTools' Sources panel, OR find the rule in the right-side Styles panel.
3. Edit a value live (click on `20px` next to `h3`, type a new number, hit Enter).
4. When you find the value you like, change it in `index.html` at the line shown above.

### Common edits and what to change

| You want… | Change at line | New value to try |
|---|---|---|
| Wider page column | L55 `--page-max` | `1400px` |
| Narrower, more editorial column | L55 `--page-max` | `1080px` |
| H3 doesn't feel like a real heading | L137 | `font-size: 22px;` or `24px;` |
| Eyebrow ("02 · Introduction") too small | L130 | `font-size: 12px;` |
| H2 needs more breathing room before paragraph | L135 margin | `margin: 0 0 24px;` |
| Lede paragraph blends into body | L139 | bump `17px` to `18px` or add `font-weight: 500;` |

---

## 8 · Centering policy · one-liners center, multi-lines stay left

**Applied · live in the file.** Lives at **`index.html:142–180`**, right after the `strong` rule and before `hr.section-divider`.

### The rule, in one sentence

> **One-liners get centered. Multi-line text never does.**

Why: centered multi-line paragraphs create ragged left edges that hurt scannability. Centered short labels (eyebrow, section titles, demo tags) look intentional and Morphing-Matter-clean.

### What the CSS does

```css
section { text-align: center; }                     /* default: center inline content */

section h2, section h3 {
  margin-left: auto; margin-right: auto;            /* center the heading BLOCK */
}

section p, section p.lede {
  text-align: left;                                 /* paragraphs stay left-aligned */
  /* no margin: auto — block sits flush-left in its container */
}

/* Scan-heavy blocks stay left-aligned end-to-end */
section .card, section .team-card, section .issue-card, section .future-card,
section .video-card, section .video-meta,
section .pipeline, section .pipeline-stage, section .cursor-desktop,
section .code-window, section .table-wrap, section .state, section .dual-arch,
section table, section pre, section ul, section ol {
  text-align: left;
}
```

### What this means concretely on the page

| Element | Centered? | Why |
|---|---|---|
| `.eyebrow` (e.g. "02 · Introduction") | ✓ centered | one-liner, inline-block, picks up `text-align: center` from parent |
| `<h2>` (section titles, e.g. "The safety state machine") | ✓ centered | one-liner; `margin: 0 auto` centers the block |
| Free `<h3>` (e.g. "Our Objectives", "Where this kind of system…") | ✓ centered | one-liner |
| `.demo-tag` ("Demo 01 · Sim · Checkpoint 1") | ✓ centered | one-liner span |
| `.demo-block h3` ("Gazebo simulation.") | ✓ centered | one-liner |
| `<p>` body ("Convoying in robotics is defined as…") | ✗ left | multi-line — would go ragged if centered |
| `<p class="lede">` ("All three demos run the same…") | ✗ left | multi-line lede |
| Card internals (Hardware, Goal, Success bar, team cards…) | ✗ left | scan-heavy bullet content; cards are left-aligned end-to-end |
| `.video-meta` ("Source:", "Tracking topic:", "Trajectory:") | ✗ left | multi-line key/value list |
| `.state` (IDLE / ARM / FOLLOW / SEARCH / LAND boxes) | ✗ left | uniform left margin reads as a row |

### Mental model for future edits

- **Is it a one-line title, tag, or eyebrow?** → centered.
- **Will it wrap to 2+ lines on most screens?** → left-aligned.

If you find an exception (a one-line label that's stuck left because its parent is in the reset list), the fix is one of:
1. Remove its parent from the reset list (centers everything in that container)
2. Or add a more specific rule that re-centers just that one element, e.g. `section .state .num { text-align: center; }`

### How to back out completely

Delete L142–L180 from `index.html`. Page reverts to flat left-aligned.

### How to also center card titles (if you change your mind)

Card titles (`.card h3` like "Hardware", "Goal") are currently left-aligned because the whole card is in the reset. To center just the card's h3:

```css
section .card h3 { text-align: center; }
```

Add that after the reset block.

### Quick toggle in DevTools

Open DevTools → Elements → Styles panel → uncheck the rules to compare. Re-enable with one click without touching the file.


