# Learning Studio Design System

Visual specifications for print-ready educational PDFs by grade band.

---

## Universal Print Specifications

- **Page size:** US Letter — 8.5" × 11" (612 × 792 points)
- **Margins:** 0.75" (54pt) minimum on all sides
- **Binding margin:** Add 0.25" (18pt) to the left margin for stapled/bound packets
- **Safe print area:** 7.0" × 9.5" (504 × 684 points)
- **Resolution:** 300 DPI for raster elements
- **Color model:** Design in color; ensure readability in grayscale
- **Font embedding:** Embed all fonts in PDF output

---

## Color Palette

Use these colors across all grade bands. Adjust usage intensity by band.

| Role | Hex | Usage |
|------|-----|-------|
| Primary Blue | `#2B4C7E` | Headers, section titles |
| Accent Teal | `#3B9A9C` | Subheaders, highlights, "Challenge" labels |
| Warm Orange | `#E8782A` | Stars, rewards, "Fun Fact" boxes |
| Soft Green | `#5DAE6F` | Correct/positive indicators, "Great Job" elements |
| Light Gray | `#F4F4F4` | Answer boxes, writing lines background |
| Medium Gray | `#9E9E9E` | Tracing lines, secondary text |
| Dark Text | `#2D2D2D` | Body text |
| White | `#FFFFFF` | Page background |

### Grade Band Color Adjustments
- **Pre-K to 1st:** Warmer tones — use orange, green, and teal more prominently. Softer blue.
- **2nd to 3rd:** Balanced palette — all colors in moderate use.
- **4th to 6th:** Cooler, more restrained — primary blue and teal dominant. Orange used sparingly. Avoid anything that reads as "cute."
- **7th to 8th:** Professional palette — primary blue and medium gray dominant. Teal for accents. Minimal color overall. Think "clean textbook supplement."
- **9th to 12th:** Minimal color — primary blue for headers, medium gray for structure, white space dominant. Accent color only for formula/concept boxes. Materials should look like they belong in a college-prep or tutoring center setting.

---

## Typography

### Font Recommendations (system-safe for ReportLab/WeasyPrint)

| Purpose | Primary | Fallback |
|---------|---------|----------|
| Headers | Helvetica Bold | Arial Bold |
| Body text | Helvetica | Arial |
| Student writing areas | Courier (for lined guides) | — |
| Math problems | Helvetica | Arial |
| Parent notes | Helvetica Oblique (9pt) | Arial Italic |

### Size Specifications by Grade Band

#### Pre-K to 1st Grade
| Element | Size | Weight | Notes |
|---------|------|--------|-------|
| Page title | 28–36pt | Bold | Centered or left-aligned |
| Section header | 22–26pt | Bold | — |
| Directions | 18–20pt | Regular | 1 sentence max |
| Activity text | 18–22pt | Regular | — |
| Tracing text | 28–48pt | Light/Regular | Dotted or dashed stroke |
| Answer spaces | 24pt height min | — | Thick bottom border |
| Parent note | 9–10pt | Italic | Bottom of page, muted color |
| Footer/standard | 7–8pt | Regular | — |

#### 2nd to 3rd Grade
| Element | Size | Weight | Notes |
|---------|------|--------|-------|
| Page title | 20–24pt | Bold | — |
| Section header | 16–18pt | Bold | — |
| Directions | 13–15pt | Regular | 1–2 sentences |
| Body/passage text | 13–15pt | Regular | 1.4 line spacing |
| Math problems | 14–16pt | Regular | — |
| Answer spaces | 18pt height min | — | — |
| Parent note | 9pt | Italic | — |
| Footer/standard | 7pt | Regular | — |

#### 4th to 6th Grade
| Element | Size | Weight | Notes |
|---------|------|--------|-------|
| Page title | 18–20pt | Bold | — |
| Section header | 14–16pt | Bold | — |
| Directions | 11–12pt | Regular | 2–3 sentences OK |
| Body/passage text | 11–12pt | Regular | 1.3–1.4 line spacing |
| Math problems | 12–13pt | Regular | — |
| Answer lines | 14pt height | — | Standard ruled |
| Parent note | 8pt | Italic | — |
| Footer/standard | 7pt | Regular | — |

#### 7th to 8th Grade (Middle School)
| Element | Size | Weight | Notes |
|---------|------|--------|-------|
| Page title | 16–18pt | Bold | — |
| Section header | 13–15pt | Bold | — |
| Directions | 10.5–11.5pt | Regular | Concise, can be multi-step |
| Body/passage text | 11–12pt | Regular | 1.3 line spacing |
| Math problems | 11–12pt | Regular | — |
| Vocabulary sidebar | 9–10pt | Regular | Boxed, light background |
| Answer lines | 12pt height | — | Standard ruled |
| Parent note | 8pt | Italic | Optional at this level |
| Footer/standard | 7pt | Regular | — |

#### 9th to 12th Grade (High School)
| Element | Size | Weight | Notes |
|---------|------|--------|-------|
| Page title | 14–16pt | Bold | — |
| Section header | 12–14pt | Bold | — |
| Directions | 10–11pt | Regular | Concise, assumes independence |
| Body/passage text | 10.5–11.5pt | Regular | 1.25–1.3 line spacing |
| Math problems | 11–12pt | Regular | — |
| Formula box | 9–10pt | Regular | Bordered, shaded background |
| Vocabulary sidebar | 9–10pt | Regular | Boxed, light background |
| Answer lines | 11pt height | — | College-ruled |
| Study tip callout | 9pt | Italic | Boxed, accent border |
| Footer/standard | 6.5–7pt | Regular | — |

---

## Page Layout Templates

### Single-Skill Worksheet
```
┌─────────────────────────────────┐
│ [TITLE: Skill Name]             │
│ Name: ____________  Date: _____ │
├─────────────────────────────────┤
│ Directions: [1–2 sentences]     │
├─────────────────────────────────┤
│                                 │
│  [Practice Problems / Activity] │
│  (10–20 items, scaffolded       │
│   easy → medium → challenge)    │
│                                 │
├─────────────────────────────────┤
│ ★ Challenge Corner (optional)   │
├─────────────────────────────────┤
│ [footer: standard code]    [pg] │
└─────────────────────────────────┘
```

### Reading Passage + Questions
```
┌─────────────────────────────────┐
│ [TITLE: Passage Title]          │
│ Name: ____________  Date: _____ │
├─────────────────────────────────┤
│                                 │
│  [Passage text — full width,    │
│   1.4 line spacing, numbered    │
│   lines for grades 3+]         │
│                                 │
├─────────────────────────────────┤
│ Comprehension Questions         │
│ 1. [literal recall]             │
│ 2. [literal recall]             │
│ 3. [inference]                  │
│ 4. [vocabulary in context]      │
│ 5. [text evidence]              │
│ 6. [opinion/connection]         │
├─────────────────────────────────┤
│ [footer: standard code]    [pg] │
└─────────────────────────────────┘
```

### Math Practice Page
```
┌─────────────────────────────────┐
│ [TITLE: Math Skill]             │
│ Name: ____________  Date: _____ │
├─────────────────────────────────┤
│ Directions: [child-friendly]    │
├────────────────┬────────────────┤
│  Warm-Up       │  Practice      │
│  (2–3 easy)    │  (8–12 medium) │
├────────────────┴────────────────┤
│ Word Problems (3–4, themed)     │
├─────────────────────────────────┤
│ ★ Challenge Zone                │
├─────────────────────────────────┤
│ [footer: standard code]    [pg] │
└─────────────────────────────────┘
```

### Daily Packet Page (multi-subject, K–6)
```
┌─────────────────────────────────┐
│ Day [N] — [Day Name]            │
│ Name: ____________  Date: _____ │
├─────────────────────────────────┤
│ 📖 Reading / Language Arts      │
│ [passage or grammar activity]   │
├─────────────────────────────────┤
│ ✏️ Math                         │
│ [skill practice]                │
├─────────────────────────────────┤
│ 🌱 Science or 🌍 Social Studies │
│ [rotating subject]              │
├─────────────────────────────────┤
│ ⭐ Brain Break / Fun Fact       │
├─────────────────────────────────┤
│ [footer: standard codes]   [pg] │
└─────────────────────────────────┘
```

### Study Guide Page (Grades 7–12)
```
┌─────────────────────────────────┐
│ [TOPIC TITLE]                   │
│ [Subject — Course Name]         │
├─────────────────────────────────┤
│ KEY CONCEPTS                    │
│ [2–4 concept summaries with     │
│  definitions and formulas]      │
├──────────────────┬──────────────┤
│ WORKED EXAMPLE   │ KEY VOCAB    │
│ [Step-by-step    │ • term: def  │
│  solution]       │ • term: def  │
│                  │ • term: def  │
├──────────────────┴──────────────┤
│ PRACTICE                        │
│ [6–12 problems, scaffolded]     │
├─────────────────────────────────┤
│ APPLY IT / EXTENSION            │
│ [1–2 multi-step or real-world]  │
├─────────────────────────────────┤
│ [footer: standard code]    [pg] │
└─────────────────────────────────┘
```

### Test Prep Page (Grades 7–12)
```
┌─────────────────────────────────┐
│ [ASSESSMENT NAME] Practice      │
│ Section: [topic]  Time: [est.]  │
├─────────────────────────────────┤
│                                 │
│  [Questions in target test      │
│   format — MC, gridded          │
│   response, short answer,       │
│   or free response as           │
│   appropriate]                  │
│                                 │
├─────────────────────────────────┤
│ [footer: standard codes]   [pg] │
└─────────────────────────────────┘
```

### Essay / Writing Practice (Grades 6–12)
```
┌─────────────────────────────────┐
│ Writing Prompt                  │
│ Name: ____________  Date: _____ │
├─────────────────────────────────┤
│ PROMPT:                         │
│ [2–4 sentence prompt with       │
│  clear task and audience]       │
├─────────────────────────────────┤
│ PLANNING SPACE                  │
│ [Graphic organizer: outline,    │
│  claim-evidence-reasoning,      │
│  or brainstorm web]             │
├─────────────────────────────────┤
│ DRAFT                           │
│ [Lined writing space —          │
│  college-ruled for 9–12,        │
│  standard-ruled for 6–8]        │
│  (1–2 full pages)               │
├─────────────────────────────────┤
│ [footer: standard code]    [pg] │
└─────────────────────────────────┘
```

---

## Packet Structure — Multi-Page Resources

### Front Matter
1. **Cover page** — Title, child's name (if configured), grade level, decorative but grade-appropriate art
2. **Parent/Tutor Guide** (1 page) — How to use the packet, pacing, tips
3. **Table of Contents** (for 10+ page packets)

### Body
- Daily or skill-based pages following consistent structure
- Friday pages: writing prompts or project-based activities
- Mid-packet check-in page (for packets 15+ pages)

### Back Matter
1. **Reading Log** (if packet includes reading passages)
2. **Progress Tracker** — Check-off grid for completed days/skills
3. **Skill Mastery Checklist** — Parent-facing, standards-referenced
4. **Answer Key** — Organized by day/page number, clearly separated
5. **Completion Certificate** — Celebratory, with space for name and date

---

## Visual Elements

### Decorative Rules
- Use simple geometric dividers between sections (lines, dots, thin rules).
- Avoid clip art, cartoon characters, or overly decorative borders for grades 3+.
- For Pre-K to 1st: simple, friendly icons (stars, smiley faces, pencils) are acceptable.
- For 7th–8th: zero decorative elements. Clean horizontal rules and boxed sections only.
- For 9th–12th: professional, textbook-quality. Thin rules, shaded concept boxes, clean borders. No icons or decorative elements whatsoever.

### Answer Spaces
- **Multiple choice:** Bubbles (○ A  ○ B  ○ C  ○ D) — large enough to fill with a pencil.
- **Short answer:** Single line with clear baseline.
- **Extended response:** 4–8 ruled lines with consistent spacing.
- **Math computation:** Gridded work space or blank area with labeled answer line.

### Reward / Motivation Elements
- **K–5:** "Great Job!" or "You Did It!" — use sparingly, end of sections. Star ratings for self-assessment. Visual progress trackers (color-in bars, check boxes).
- **6–8:** Replace celebration language with progress-focused language: "Skills Mastered," "Ready for the Next Level." Check-box trackers. No stars or stickers.
- **9–12:** No motivational elements. Use mastery-tracking checklists and score/percentage boxes for self-assessment. Progress is its own reward at this level — the materials should communicate competence and respect.

---

## Technical Reminders

### ReportLab Specifics
- Use `Paragraph` with `ParagraphStyle` for body text — set `spaceAfter`, `leading` explicitly.
- For math: build custom `Flowable` subclasses for vertical arithmetic, grids, number lines.
- Fraction bars: draw with `canvas.line()` inside a custom Flowable, not with text underlines.
- Always set `pagesize=letter` and define frames with explicit margins.

### WeasyPrint Specifics
- Use `@page { size: letter; margin: 0.75in; }` in CSS.
- Avoid `linearGradient` in SVGs — use adjacent solid `<rect>` elements for color transitions.
- Use `page-break-before: always` to control pagination.
- Embed fonts via `@font-face` if using non-system fonts.

### Quality Check
- Render with `pdftoppm -jpeg -r 105` and visually inspect.
- Check specific pages with `-f [start] -l [end]` flags.
- Verify answer key matches questions exactly.
- Print a test page to confirm margin safety.
