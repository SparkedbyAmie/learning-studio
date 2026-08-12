---
name: learning-studio
description: "Premium educational worksheet and workbook generator for K-12 students. Use this skill EVERY TIME a user asks to create worksheets, workbooks, learning packets, summer bridge materials, tutoring resources, flashcards, assessments, reading passages, math practice, study guides, exam prep, or any printable educational content for students in Pre-K through 12th grade. Also trigger when the user mentions: homeschool materials, summer learning loss, skill practice sheets, reading comprehension passages, math fluency practice, kindergarten readiness, grade transition prep, educational PDFs for kids or teens, ACT/SAT prep worksheets, algebra practice, essay writing practice, science review sheets, AP course supplements, or high school study packets. Use even if the user doesn't explicitly say 'use the skill' — if they're asking for student-focused educational content at any K-12 level, this is the skill. Supports per-family configuration: state standards, grade levels, and student interests for personalized content."
---

# Learning Studio

Generate premium, print-ready educational materials for K-12 students — worksheets, workbooks, packets, assessments, reading passages, math activities, study guides, exam prep, and more. Every output is standards-aligned, scaffolded for confidence, and personalized to each student's interests and level.

---

## First Steps — Every Time

1. **Read the user's profile** from `references/user-profile.md` if it exists in the skill directory. If not, ask the user to configure one (see Configuration below).
2. **Identify what the user wants**: worksheet, packet, assessment, reading passage, math page, full workbook, etc.
3. **Identify the target child** from their profile (by name, grade, or context clues).
4. **Read `references/standards-guide.md`** to load the correct state standards for the user's configured state and grade level.
5. **Read `references/design-system.md`** for typography, layout, and visual rules by grade band.
6. **Generate the content** following the instructional design principles below.
7. **Build the PDF** using the pdf skill's tooling (ReportLab for math-heavy content; WeasyPrint for text-heavy content).
8. **QC the output** — verify answer keys, check print margins, validate age-appropriateness.

---

## Configuration — User Profile

The skill is designed to be personalized. On first use or when the user says "set up my learning studio" or "configure my kids," walk them through creating a profile.

### Profile Structure

Save to `references/user-profile.md` inside the skill directory. If the directory is read-only, save to the working directory and instruct the user to place it in the skill folder.

```markdown
# Learning Studio — Family Profile

## State & Standards
- **State:** [e.g., Indiana, Texas, California, Florida]
- **Standards framework:** [auto-populated based on state]

## Children

### [Child Name]
- **Current grade completed:** [e.g., 3rd grade, Pre-K, 8th grade, 10th grade]
- **Entering grade:** [e.g., 4th grade, Kindergarten, 9th grade, 11th grade]
- **Interests:** [e.g., art/painting, dinosaurs, soccer, K-pop, Minecraft, Avatar: The Last Airbender, basketball, anime, coding, music production, fashion]
- **Learning style notes:** [e.g., gives up when things look hard, needs confidence-building; loves competition; very visual learner; needs real-world relevance to stay engaged]
- **Focus areas:** [e.g., reading comprehension, multiplication fluency, letter recognition, algebra, essay writing, chemistry, ACT prep]
- **Avoid:** [e.g., babyish visuals, overly dense text, condescending tone]

### [Child Name]
- (repeat for each child)
```

### Configuration Interview

When no profile exists, ask these questions conversationally:

1. What state are you in? (determines standards alignment)
2. How many children are we creating materials for?
3. For each child: name, grade just completed, grade entering
4. What are each child's interests? (hobbies, favorite shows/games/characters, sports, topics they love)
5. Any learning personality notes? (e.g., gets frustrated easily, loves challenges, needs large print)
6. Any specific academic focus areas or known gaps?

Store the answers in the profile format above.

---

## Instructional Design Principles

These apply to ALL outputs regardless of grade level.

### Confidence-First Scaffolding
- Begin every worksheet or activity with 2–3 accessible warm-up problems or a familiar concept.
- Progress from easy → medium → challenge within each page.
- Frame difficulty as growth ("Challenge Zone!" or "Level Up!") rather than as potential failure.
- Never use shame-based language, harsh corrections, or stressful testing language.

### Interest Anchoring
- Weave each child's configured interests into reading passages, word problems, examples, and scenarios.
- Create original characters and scenarios inspired by interests — never use copyrighted characters directly.
- For a child who likes painting: word problems about mixing colors, buying art supplies, gallery visitors.
- For a child who likes dinosaurs: reading passages about paleontology, math with fossil measurements.
- Interest anchoring should feel natural, not forced. If a math concept doesn't lend itself to a theme, skip it rather than creating an awkward connection.

### Standards Alignment
- Every activity must target at least one specific standard from the user's configured state.
- Reference the standard subtly in a footer: e.g., "Aligned to Indiana Grade 3 Math Standard 3.C.1"
- For grade-transition materials: 60% review of completed grade standards, 40% preview of entering grade.
- Spiral review: revisit earlier concepts periodically across multi-page packets.

### One Concept Per Activity
- Each worksheet or activity page should focus on one core skill or concept.
- Directions should be clear and age-appropriate: 1–2 sentences for K–2; 2–3 for grades 3–6; concise but complete for grades 7–12 (students should be able to work independently from the directions alone).
- For K–8: include an optional parent/tutor note in smaller text when the activity benefits from adult guidance.
- For 9–12: parent notes are optional; instead include "Study Tip" or "Key Concept" sidebars that support independent study.

### Developmental Appropriateness Across K-12
- **K–2:** Warm, celebratory, playful. Short activities. Large print. Repetition is a feature.
- **3–5:** Encouraging but not babyish. Structured. Growing independence. Interest anchoring is critical.
- **6–8:** Respectful of emerging adolescent identity. Content should feel relevant and real-world connected. Avoid anything patronizing. Can handle complexity and multi-step reasoning.
- **9–12:** Professional and clean. Treat students as capable young adults. Materials should mirror the quality of a good textbook supplement or tutoring center resource. Interest anchoring shifts to career connections, real-world applications, and topics teens genuinely care about.

---

## Content Types & How to Build Them

### Reading Passages
- ALWAYS write original passages — never reproduce copyrighted text.
- Anchor in the student's interests when possible.
- Include comprehension questions scaled to grade: 3–4 for K–1, 4–6 for grades 2–6, 6–8 for grades 7–12.
- Question types by band:
  - K–2: literal recall, simple inference, vocabulary
  - 3–6: literal recall, inference, vocabulary-in-context, text evidence, opinion/connection
  - 7–9: inference, author's purpose, text structure, evidence-based argument, vocabulary, comparison
  - 10–12: rhetorical analysis, synthesis across texts, evaluating argument, tone/style analysis, vocabulary in academic context
- For grades 3+, include both fiction and nonfiction across a packet.
- Lexile-approximate by grade: K (100–400L), 1st (200–500L), 2nd (400–650L), 3rd (600–800L), 4th (700–950L), 5th (850–1050L), 6th (950–1100L), 7th (1000–1150L), 8th (1050–1200L), 9th–10th (1100–1300L), 11th–12th (1200–1400L).
- Length: K–1 (80–150 words), 2–3 (200–400 words), 4–6 (350–600 words), 7–8 (500–800 words), 9–12 (600–1200 words).

### Math Practice Pages
- Use visual models appropriate to grade: counters and ten-frames (K–1), number lines and arrays (2–3), area models and fraction bars (4–6), coordinate planes and graphs (7–8), function tables and graphs (9–12).
- Include a mix of computation and word problems on each page.
- Word problems should use the student's name and interests when configured.
- For multi-digit operations, use ReportLab custom Flowables for precise alignment (vertical stacking, grid placement).
- Number line tick marks must use explicit x-coordinates — never calculated spacing shortcuts.
- **Middle school math (6–8):** Include ratio tables, proportion setups, integer number lines, coordinate grids, and equation-solving workspace with balance-model scaffolding.
- **High school math (9–12):** Include graph paper grids, coordinate planes with labeled axes, function tables, proof/derivation workspace, and formula reference boxes. For algebra/geometry/precalc, show worked examples before practice sets.

### Worksheets & Skill Pages
- Clear title with skill name: "Multiplying by 7" not "Math Practice"; "Solving Two-Step Equations" not "Algebra."
- Directions box at top with age-appropriate language.
- Item count by band: 10–20 for K–6, 8–15 for grades 7–9 (problems are longer/more complex), 6–12 for grades 10–12.
- Include a "Challenge Corner" (K–5), "Extension" (6–8), or "Apply It" (9–12) section for students who finish early or want deeper practice.
- Answer key on a separate page, clearly labeled. For grades 7–12, include worked solutions (not just final answers) for at least 2–3 representative problems.

### Study Guides (Grades 6–12)
- Organized by topic with key vocabulary, formulas/rules, and worked examples.
- Use two-column or Cornell-note style layouts for clarity.
- Include "Check Your Understanding" questions (3–5) at the end of each section.
- For test prep: mirror the format of the target assessment (state test, AP exam, ACT/SAT).

### Essay & Writing Practice (Grades 6–12)
- Include a prompt, a planning/outline organizer, and lined writing space.
- For argumentative/persuasive writing: include a claim-evidence-reasoning graphic organizer.
- For literary analysis: include a passage excerpt (original) with annotation prompts.
- Rubric on a separate page so students can self-assess.

### Full Packets & Workbooks
- Include a cover page with the child's name (if configured), packet title, and grade level.
- Table of contents for packets over 10 pages.
- Consistent daily structure when applicable (e.g., Day 1: reading + math; Day 2: math + writing).
- Back matter: answer key, progress tracker, skill checklist, completion certificate.
- Parent guide at the front explaining how to use the packet, pacing suggestions, and tips.

### Assessments
- Frame as "Skill Checks" or "Show What You Know" — avoid "test" language.
- Mix question types: multiple choice, short answer, fill-in-the-blank, matching.
- Include clear point values and a simple scoring guide for parents.
- Provide intervention suggestions for scores below mastery threshold.

### Flashcards
- Standard playing-card proportions (2.5" × 3.5") or index-card size (3" × 5").
- Front: term, problem, or image. Back: definition, answer, or explanation.
- Use large, clear fonts. Include cut-lines for printing.

---

## Grade-Band Design Systems

Read `references/design-system.md` for full specifications. Key rules:

### Pre-K to 1st Grade
- Fonts: 24–36pt for headers, 18–22pt for body, 28pt+ for tracing
- Tracing lines: 2pt stroke minimum
- Page density: LOW — lots of white space, 1–2 activities per page
- Visuals: warm, playful, encouraging — friendly shapes, gentle colors
- Writing areas: extra-large ruled lines (1" spacing minimum)
- Directions: 1 sentence, paired with a visual cue when possible

### 2nd to 3rd Grade
- Fonts: 18–24pt headers, 14–16pt body
- Page density: MODERATE — 2–3 activities per page
- Visuals: clean and educational, not cartoonish
- Writing areas: standard primary ruled lines
- Directions: 1–2 sentences

### 4th to 6th Grade
- Fonts: 16–20pt headers, 11–13pt body
- Page density: MODERATE-HIGH — structured layouts with clear sections
- Visuals: modern workbook aesthetic — clean, slightly elevated, "smart" feel
- Writing areas: standard lined or open response boxes
- Directions: 2–3 sentences, can include multi-step directions
- Must avoid anything that feels "babyish" — image-aware students in this band will disengage

### 7th to 8th Grade (Middle School)
- Fonts: 14–18pt headers, 11–12pt body
- Page density: HIGH — efficient use of space, professional layouts
- Visuals: minimal and purposeful — diagrams, graphs, and charts over decoration. No clip art. Think textbook supplement, not worksheet pack.
- Writing areas: standard lined or open response boxes, with extended response areas for multi-paragraph writing
- Directions: concise and direct, can be multi-step
- Tone: respectful of emerging adolescent identity — never condescending. Content should feel relevant and connected to the real world.
- Include "Why This Matters" or real-world connection callouts to maintain engagement

### 9th to 12th Grade (High School)
- Fonts: 13–16pt headers, 10.5–11.5pt body
- Page density: HIGH — clean, dense, professional. Mirrors college-prep materials.
- Visuals: functional only — graphs, diagrams, data tables, coordinate planes. Zero decorative elements.
- Writing areas: college-ruled lines or open response boxes
- Directions: concise, assumes student independence. Can reference prior knowledge.
- Tone: treats students as capable young adults. Direct, clear, professional.
- Include formula reference boxes, vocabulary sidebars, and "Key Concept" callouts
- For AP/honors content: match the rigor and format of released exam questions
- For SAT/ACT prep: mirror the exact question formats and timing expectations

---

## State Standards Reference

Read `references/standards-guide.md` for the full standards mapping. The skill supports all 50 US states. Key approach:

- When a user configures their state, the skill maps to that state's published academic standards.
- If the exact state standards document isn't available, use Common Core as a baseline and note the alignment.
- Most states have adopted or closely mirror Common Core for ELA and Math; deviations are noted in the guide.
- For states with distinctive frameworks (Texas TEKS, Virginia SOLs, Indiana Academic Standards), use the state-specific names and codes.
- Always cite the specific standard code in footer text on worksheets.

### Standards by Subject

**English Language Arts (K–12):**
- K–5: Reading Literature, Reading Informational Text, Foundational Skills (phonics/fluency), Writing, Language (grammar/vocabulary), Speaking & Listening
- 6–8: Reading Literature, Reading Informational Text, Writing (argument, informative, narrative), Language, Speaking & Listening
- 9–12: Reading Literature, Reading Informational Text, Writing (argument, informative, narrative, research), Language, Speaking & Listening. Align to grade-band standards (9–10, 11–12).

**Mathematics (K–12):**
- K–5: Operations & Algebraic Thinking, Number & Operations (Base Ten, Fractions), Measurement & Data, Geometry
- 6–8: Ratios & Proportional Relationships, The Number System, Expressions & Equations, Functions (8th), Geometry, Statistics & Probability
- 9–12: Organized by course — Algebra I, Geometry, Algebra II, Precalculus, Statistics. Use state-specific course standards or CCSS high school domains (Number & Quantity, Algebra, Functions, Geometry, Statistics & Probability, Modeling).

**Science (K–12):**
- K–5: Life Science, Earth/Space Science, Physical Science, Engineering/Design
- 6–8: Life Science, Earth/Space Science, Physical Science, Engineering/Design (NGSS or state equivalent)
- 9–12: Organized by course — Biology, Chemistry, Physics, Earth Science, Environmental Science. Align to NGSS Performance Expectations or state course standards.

**Social Studies (K–12):**
- K–5: Geography, History, Civics, Economics (state-specific scope and sequence)
- 6–8: World History/Geography, US History, Civics/Government (state-specific)
- 9–12: US History, World History, Government, Economics, AP-level courses. Align to state course standards.

**Additional High School Subjects:**
- World Languages, Health/PE, Financial Literacy, Computer Science — generate practice materials when requested, aligned to state standards where available.

---

## PDF Generation

### Tool Selection
- **ReportLab**: Use for math-heavy content requiring precise alignment — vertical arithmetic, grids, number lines, fraction models, area models. Also for flashcards and anything needing custom Flowables.
- **WeasyPrint**: Use for text-heavy content — reading passages, writing prompts, parent guides. HTML/CSS approach allows faster iteration on text-heavy layouts.
- **Hybrid**: For full packets mixing text and math, generate sections with the appropriate tool and merge with pypdf.

### Print Specifications
- Page size: US Letter (8.5" × 11")
- Margins: 0.75" minimum on all sides (safe for home printers)
- Resolution: 300 DPI for any raster elements
- Color: design for color but ensure readability in grayscale
- Binding: leave 0.25" extra on the left margin if the packet will be stapled/bound

### Known Technical Patterns
- ReportLab `StackedProblem.__init__`: argument order is `color` before `width` — mismatches cause float-as-color errors.
- Number line tick marks: use explicit x-coordinates, not calculated spacing.
- WeasyPrint SVG: `linearGradient` fills render blank — use adjacent solid-color `<rect>` elements instead.
- Fraction bar models and area model grids: use custom Flowables for accuracy.
- QC rendered pages with `pdftoppm -jpeg -r 105`; check specific pages with `-f` and `-l` flags.

### File Naming Convention
- Single worksheets: `[Subject]_[Skill]_Grade[N].pdf` — e.g., `Math_Multiplication7s_Grade3.pdf`
- Packets: `[Type]_Week[NN]_[Topic].pdf` — e.g., `SummerMath_Week03_Fractions.pdf`
- Assessments: `[Subject]_SkillCheck_[Topic]_Grade[N].pdf`
- Save all outputs to `/mnt/user-data/outputs/`

---

## Quality Control Checklist

Before presenting any output, verify:

- [ ] Age-appropriate content and visuals for the target grade band
- [ ] Standards alignment is correct and cited
- [ ] All answer key entries match the questions exactly
- [ ] Grammar and spelling are correct throughout
- [ ] Directions are clear and child-friendly
- [ ] Confidence-building tone — no shame language
- [ ] Print margins are safe (0.75" minimum)
- [ ] Pages are visually balanced and uncluttered
- [ ] Interest anchoring feels natural (not forced)
- [ ] Challenge progression goes easy → medium → hard
- [ ] Parent/tutor notes are included where helpful

---

## Example Interaction Patterns

**User says:** "Make a multiplication worksheet for my 3rd grader"
→ Check profile for child's name, interests, and state. Generate a worksheet with 20 problems progressing from single-digit review to introducing two-digit × one-digit, with word problems themed to their interests. Include answer key.

**User says:** "I need a summer reading packet for kindergarten"
→ Check profile for the K student. Generate 5–10 short passages (80–120 words each) with large print, picture cues, and 3–4 comprehension questions per passage. Include a reading log and parent guide.

**User says:** "Create a weekly learning schedule for both my kids"
→ Generate a structured weekly plan with daily activities for each child at their level, balancing subjects across the week. Include time estimates and materials needed.

**User says:** "Set up my learning studio"
→ Run the configuration interview. Save the profile.

**User says:** "My kid loves Minecraft now, update their interests"
→ Update the child's interest list in the profile and confirm.

**User says:** "My 7th grader needs help with proportional relationships"
→ Check profile. Generate a worksheet with ratio tables, proportion setups, and real-world word problems (themed to interests — e.g., a basketball fan gets stats-based proportions). Include 3 worked examples at the top, 10 practice problems scaffolded easy→hard, and a separate answer key with solutions.

**User says:** "Create an Algebra 1 review packet for my 9th grader"
→ Check profile for interests and state. Build a multi-page packet covering key Algebra 1 domains: solving equations, graphing linear functions, systems of equations, exponents, polynomials. Each section has a concept summary, worked examples, and practice problems. Include a formula reference sheet and full answer key with worked solutions.

**User says:** "I need ACT math practice for my junior"
→ Generate a practice set mirroring ACT math format: 60 questions, multiple choice, covering pre-algebra through trigonometry. Include timing guidance and a scoring rubric. Answer key with explanations for commonly missed problem types.

**User says:** "Make a biology study guide on cell division"
→ Check profile. Generate a two-page study guide: key vocabulary with definitions, diagram labeling activity (mitosis phases), comparison chart (mitosis vs. meiosis), and 8–10 review questions mixing multiple choice and short answer. Include answer key.

**User says:** "Create a summer bridge packet for my kid going into 6th grade"
→ Build a multi-week packet reviewing 5th grade ELA and math standards while previewing 6th grade concepts. Daily structure with reading passages, math practice, vocabulary, and a weekly writing prompt. Include parent guide and answer keys.