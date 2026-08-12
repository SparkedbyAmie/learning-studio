# Learning Studio

**A Claude skill that turns AI into your family's personal curriculum designer.**

Generate premium, print-ready educational materials — worksheets, workbooks, reading passages, math packets, study guides, test prep, assessments, flashcards, and more — personalized to your children's grade levels, state standards, and individual interests. Pre-K through 12th grade.

---

## What It Does

Learning Studio works as a Claude skill that gives Claude the expertise of an elite private tutor, curriculum specialist, and educational publisher — all at once. Every output is:

- **Standards-aligned** to your state's academic framework (all 50 states supported)
- **Scaffolded for confidence** — easy wins first, then gradual challenge
- **Interest-anchored** — your child's hobbies and favorites woven into reading passages, word problems, and examples
- **Print-ready** — US Letter PDFs with safe margins, answer keys, and clean layouts
- **Age-appropriate** — five distinct design systems from Pre-K through 12th grade ensure materials feel right for every student

### What You Can Generate

**Elementary (K–6)**
- Single-skill worksheets (math, reading, grammar, science, social studies)
- Multi-week learning packets with daily structure
- Summer bridge workbooks to prevent learning loss
- Reading comprehension passages (original, copyright-free)
- Math practice with visual models (number lines, arrays, area models, fraction bars)
- Assessments framed as "skill checks" (not stressful tests)
- Flashcard sets with cut lines
- Parent guides with pacing suggestions
- Progress trackers, skill checklists, and completion certificates

**Middle School (7–8)**
- Skill-specific practice (proportions, equations, grammar, writing)
- Study guides with key concepts, worked examples, and practice problems
- Reading passages with inference and analysis questions
- Essay/writing practice with graphic organizers and rubrics
- State assessment prep materials

**High School (9–12)**
- Course-specific practice (Algebra, Geometry, Biology, Chemistry, Physics, US History, etc.)
- Study guides mirroring textbook supplement quality
- SAT/ACT/PSAT prep worksheets in authentic test formats
- AP exam practice aligned to College Board course descriptions
- Essay writing practice with planning organizers and rubrics
- Formula reference sheets and vocabulary review

### Grade Levels Supported

- **Pre-K** (early learning / kindergarten readiness)
- **Kindergarten through 12th Grade**

---

## How to Use It

### Option 1: Install as a Claude Skill (Recommended)

1. Download the `learning-studio.skill` file from the [Releases](../../releases) page.
2. In Claude.ai, go to **Settings → Skills → Add Skill**.
3. Upload the `.skill` file.
4. Say **"Set up my learning studio"** to configure your family profile.

### Option 2: Claude Project (Copy-Paste)

1. In Claude.ai, create a new **Project**.
2. Open `SKILL.md` from this repo and copy its entire contents.
3. Paste it into the Project's **custom instructions**.
4. Do the same with the three files in `references/` — add them as **Project Knowledge**.
5. Start a conversation in the project and say **"Set up my learning studio."**

### Option 3: Just Start Talking

You don't *need* to install anything. You can paste the contents of `SKILL.md` directly into any Claude conversation as your first message, then follow up with your request. The skill file teaches Claude how to be your curriculum designer — installation just saves you from pasting it every time.

---

## Quick Start

After setup, try these prompts:

| What You Want | What to Say |
|---|---|
| Configure your family | *"Set up my learning studio"* |
| A math worksheet | *"Make a multiplication worksheet for my 3rd grader"* |
| A reading passage | *"Write a reading passage about space for my 2nd grader"* |
| A full summer packet | *"Create a 1-week summer bridge packet for my rising 4th grader"* |
| Kindergarten readiness | *"Make a letter tracing and counting packet for my Pre-K kid"* |
| An assessment | *"Create a skill check on fractions for 4th grade"* |
| Middle school math | *"My 7th grader needs practice with proportional relationships"* |
| Algebra practice | *"Create an Algebra 1 review packet for my 9th grader"* |
| ACT/SAT prep | *"I need ACT math practice for my junior"* |
| Science study guide | *"Make a biology study guide on cell division"* |
| Essay practice | *"Create an argumentative writing worksheet for my 8th grader"* |
| AP exam prep | *"Generate AP US History practice questions on the Civil War era"* |
| Update interests | *"My kid is really into Minecraft now, update their profile"* |

---

## Configuration

The skill works best when you set up a **family profile** — but it also works without one (Claude will just ask you the basics each time).

### What the Profile Stores

- **Your state** — for standards alignment (Indiana Academic Standards, Texas TEKS, Common Core, etc.)
- **Each child's grade level** — completed grade and entering grade
- **Interests** — hobbies, favorite shows/games/characters, sports, art forms
- **Learning style notes** — e.g., "needs confidence scaffolding," "loves competition"
- **Focus areas** — known skill gaps or priority subjects
- **Avoid list** — e.g., "babyish visuals," "timed activities"

### Sample Profile

```markdown
## State & Standards
- **State:** Indiana
- **Standards framework:** Indiana Academic Standards

## Children

### Maya
- **Current grade completed:** 3rd grade
- **Entering grade:** 4th grade
- **Interests:** painting, sculpture, K-pop, Avatar: The Last Airbender
- **Learning style notes:** Gives up when things look complicated — needs confidence scaffolding. Dislikes anything that looks "babyish."
- **Focus areas:** Reading comprehension, multiplication fluency
- **Avoid:** Overly cartoonish design, dense text walls

### Kofi
- **Current grade completed:** Pre-K
- **Entering grade:** Kindergarten
- **Interests:** dinosaurs, trucks, building blocks
- **Learning style notes:** Very energetic, needs short activities. Loves hands-on tasks.
- **Focus areas:** Letter recognition, counting to 20, name writing

### Amara
- **Current grade completed:** 10th grade
- **Entering grade:** 11th grade
- **Courses:** AP US History, Algebra II, Chemistry, English 11
- **Interests:** basketball, music production, photography, anime
- **Learning style notes:** Learns best with real-world examples and worked solutions. Strong reader but struggles with math confidence.
- **Focus areas:** Algebra II (logarithms, polynomials), ACT math prep, essay writing
- **Avoid:** Anything condescending, worksheets that look like "baby work"
```

---

## How It Works

### Instructional Design

Every activity follows evidence-based principles:

1. **Confidence-first scaffolding** — warm-up problems establish momentum before harder content
2. **Interest anchoring** — original characters and scenarios drawn from each child's real interests
3. **One concept per activity** — focused skill practice, not content overload
4. **Standards alignment** — every worksheet cites the specific state standard in the footer
5. **Spiral review** — earlier concepts revisited across multi-page packets

### PDF Generation

The skill uses two rendering pipelines:

- **ReportLab** — for math-heavy content requiring pixel-perfect alignment (vertical arithmetic, grids, number lines, fraction models)
- **WeasyPrint** — for text-heavy content (reading passages, writing prompts, parent guides)

All outputs are US Letter (8.5" × 11") with 0.75" margins, safe for home printers.

### Design System

Five grade-band visual systems ensure age-appropriate presentation:

| Band | Aesthetic | Font Size | Density |
|---|---|---|---|
| Pre-K to 1st | Warm, playful, spacious | 18–36pt | Low |
| 2nd to 3rd | Clean, educational | 13–24pt | Moderate |
| 4th to 6th | Modern, "smart" | 11–20pt | Moderate-high |
| 7th to 8th | Professional, textbook-style | 10.5–18pt | High |
| 9th to 12th | College-prep, minimal | 10–16pt | High |

---

## Repository Structure

```
learning-studio/
├── SKILL.md                              # Core skill — paste into Claude Project instructions
├── README.md                             # This file
├── LICENSE                               # CC BY 4.0 License
└── references/
    ├── standards-guide.md                # State standards mapping (all 50 states)
    ├── design-system.md                  # Typography, layout, color specs by grade band
    └── user-profile-template.md          # Blank family profile template
```

---

## Tips for Best Results

1. **Be specific about what you want.** "A multiplication worksheet focusing on 7s and 8s for my 3rd grader" gives better results than "a math worksheet."
2. **Let it use your child's interests.** The more interests you configure, the more varied and engaging the content.
3. **Request answer keys.** They're generated automatically for packets, but for single worksheets, ask if you want one.
4. **Iterate.** If a worksheet is too easy or too hard, say so — Claude will adjust the difficulty.
5. **Build packets over time.** Start with a single worksheet to confirm the style, then request multi-week packets.
6. **Use with Claude's file creation.** For best results, use this in a Claude.ai conversation with the "Create & analyze files" feature enabled so Claude can generate actual PDFs.

---

## License

This work is licensed under Creative Commons Attribution 4.0 International (CC BY 4.0). You're free to use, adapt, and share it — even commercially — as long as you credit the original.

---

## Credits

Built by a parent who wanted better for their kids. Powered by Claude.

If you find this useful, star the repo and share it with another parent who could use it.
