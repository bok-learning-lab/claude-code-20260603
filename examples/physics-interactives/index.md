# physics-interactives — folder index

A self-contained bundle for making PhET-style single-file HTML interactive simulations. Start with [summary.md](summary.md); everything else is here for browsing.

## Top-level

- [summary.md](summary.md) — what this project is, how we built it, what you can translate it to
- [CLAUDE.md](CLAUDE.md) — project-level instructions loaded by Claude Code on session start
- [index.md](index.md) / [index.html](index.html) — this file

## inputs/

Source material the skills can be exercised against.

- [inputs/heat-pumps-teaching-brief.md](inputs/heat-pumps-teaching-brief.md) — sample faculty teaching brief on thermodynamics, Carnot efficiency, and heat-pump calculations (first-year Harvard STEM audience)

## operations/

Prompts, skills, and the working skill-draft kept as a reference.

- [operations/deep-research-prompt.md](operations/deep-research-prompt.md) — prompt that commissioned the background-research artifacts now in `outputs/`
- operations/skills/
  - [phet-sim/](operations/skills/phet-sim/) — author a new simulation from a learning goal, after a structured pedagogical interview
  - [phet-activity/](operations/skills/phet-activity/) — Wieman-style Predict → Observe → Explain → Synthesize lesson plan around an existing sim
  - [phet-accessibility-audit/](operations/skills/phet-accessibility-audit/) — categorized audit report (Blockers / Warnings / Notes)
  - [phet-rationale/](operations/skills/phet-rationale/) — 600–1,000-word department-facing rationale
- operations/skill-draft/
  - [SKILL.md](operations/skill-draft/SKILL.md) — original draft of `/phet-sim`, kept as reference
  - rubrics/
    - [simulation-quality-rubric.md](operations/skill-draft/rubrics/simulation-quality-rubric.md) — 8-dimension scoring rubric
    - [accessibility-checklist.md](operations/skill-draft/rubrics/accessibility-checklist.md) — accessibility floor
    - [pedagogical-design-worksheet.md](operations/skill-draft/rubrics/pedagogical-design-worksheet.md) — paper-friendly long-form version of the pedagogical interview
  - templates/
    - [single-file-svg-sim.html](operations/skill-draft/templates/single-file-svg-sim.html) — SVG default starter
    - [single-file-canvas-sim.html](operations/skill-draft/templates/single-file-canvas-sim.html) — Canvas starter (particle systems, fields)
    - [single-file-linked-graph-sim.html](operations/skill-draft/templates/single-file-linked-graph-sim.html) — canonical PhET layout (model + live graph)
  - [accessibility-v2-ideas.md](operations/skill-draft/accessibility-v2-ideas.md) — design notes for a next-generation accessibility audit

## outputs/

Produced artifacts — background essays, research reports, and any sims faculty generate.

- [outputs/essay-phet-tradition.md](outputs/essay-phet-tradition.md) / [outputs/essay-phet-tradition.html](outputs/essay-phet-tradition.html) — historical context for the design tradition
- [outputs/essay-manipulable-artifact.md](outputs/essay-manipulable-artifact.md) — companion essay placing PhET in the learning-sciences tradition
- [outputs/research-basis.md](outputs/research-basis.md) — empirical research basis (PhET design + Wieman/active-learning evidence)
- [outputs/AI-Built-Simulations-Faculty-Guide.md](outputs/AI-Built-Simulations-Faculty-Guide.md) — faculty-facing guide on building simulations with AI
- [outputs/deep-research-report.md](outputs/deep-research-report.md) — output of the deep-research prompt

---

*To run end-to-end against the sample brief: open this folder in Claude Code, then `/phet-sim` with `inputs/heat-pumps-teaching-brief.md` as the learning context; then `/phet-activity` against the generated sim; then `/phet-accessibility-audit`; then `/phet-rationale` for the department-facing argument.*
