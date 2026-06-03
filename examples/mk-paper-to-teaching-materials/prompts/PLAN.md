# PLAN.md — build the three teaching skills

Three self-contained tasks. Each is copy-pasteable into a fresh Claude Code session
started in this folder, and the three can run in parallel (no shared writes during the
build). Read the shared context first.

> **Status:** all four skills are now built — `/teaching-case`, `/discussion-plan`,
> `/objection-audit` (the three tasks below) plus `/quiz`. Their `SKILL.md` files and
> validated `examples/` are under `../.claude/skills/`, and the promoted demo outputs are
> in `../output/`. The tasks below remain as the **record of how each was built** and as a
> template you can copy to spec a new skill from scratch.

---

## Shared context (read before any task)

**Required reading, in order:**
1. [CLAUDE.md](CLAUDE.md) — especially "The self-referential point" and "Alignment
   with the paper (the hard constraints)."
2. [claude-thoughts.md](claude-thoughts.md) — sections C (skills) and E (guardrails).
3. [../output/README.md](../output/README.md) and the corpus it indexes.
4. The paper: [../inputs/grant_behrends_basl.pdf](../inputs/grant_behrends_basl.pdf). At minimum read
   the abstract, §3 (due consideration), §5, and §7.

**Hard constraints (all tasks):**
- Claude produces *teaching material* and *augments the instructor*; it never renders
  the verdict about how a person should be treated.
- The Explainability Thesis is hedged, not absolute. Keep transparency and due
  consideration distinct. Interpretable ≠ immune. Black box ≠ any algorithm.
- Cite by section (e.g., §5.2). Give a page number only if verified against the PDF.
- No emojis. Stable IDs (C1–C4, S1–S3). Markdown links for file refs.

**Output conventions:**
- Build each skill at `.claude/skills/<skill-name>/` — at minimum a `SKILL.md` plus
  any supporting reference files.
- Validate against the corpus and save worked examples to
  `.claude/skills/<skill-name>/examples/`.
- The SKILL.md description must follow the workshop's trigger convention (what it
  does + when to use it / the slash command).

---

## Task 1 — Build `/teaching-case`

**Behavior:** given a target move (accuracy §5.1, ignoring-evidence §5.2,
inadmissible-evidence §5.3, decision-rules §7.1, or agential-consideration §7.2–7.3)
and optionally a domain (bail, hiring, lending, admissions, medicine), produce a
**student-facing case** (a system dossier or a thought experiment) plus **separate
instructor notes** that name the move, tie it to the section, and flag the trap. Match
the shape of the corpus cases. Offer to generate a "decoy" variant (a C3-style case
that should pass) when asked.

**Good output looks like:** a case a seminar can read cold; instructor notes that
defend every claim by section; no foregone conclusion stated to students.

**Avoid:** cases that presuppose "AI bad"; cases that conflate transparency with due
consideration; inventing page numbers.

**Validate:** regenerate a case for §5.2 and confirm it isolates ignoring-available-
evidence the way [C1](../output/cases/C1-recidivism.md) does; generate one decoy and
confirm it would pass an audit (cf. [C3](../output/cases/C3-interpretable-alt.md)). Save
both to `examples/`.

---

## Task 2 — Build `/discussion-plan`

**Behavior:** given a case (e.g. C1) or a section of the paper, produce a Socratic
discussion sequence: (a) warm-up that elicits the intuitive transparency answer; (b)
the core dilemma; (c) the positions students will likely take — **anticipating S1–S3**;
(d) the objection to steer toward (one of the three Problems); (e) the move in the
paper that addresses it; (f) an honest note on what the case can and cannot show.

**Good output looks like:** a plan that walks students *from* transparency *to* due
consideration rather than asserting the destination; each anticipated position linked
to its corpus file and the section that answers it.

**Avoid:** lecturing the conclusion; treating the thesis as absolute; skipping the
substantive/procedural or evidential/practical distinctions where they do work.

**Validate:** build a plan around [C1](../output/cases/C1-recidivism.md) and confirm it
anticipates [S1](../output/student-arguments/S1-accuracy-is-all.md) and routes to §5.2.
Save to `examples/`.

---

## Task 3 — Build `/objection-audit`

**Behavior:** given a student argument (S1–S3 or a real submission), **steelman it
first**, then diagnose it against the framework: which distinction it misses or which
Problem (Definition / Double Standard / Grounding) it falls to, with section citations,
and a closing prompt for the student to push back on. Always "right about X, misses Y,"
never a flat "wrong."

**Good output looks like:** a memo a TA could hand back; the steelman is genuine; the
diagnosis is specific to a section; it ends by inviting the student's response, not
closing the question.

**Avoid:** strawmanning; verdict-without-steelman; denying true premises (e.g. for S2,
do not deny that humans are opaque — deploy the third option instead).

**Validate:** run it on all three of S1–S3 and confirm each diagnosis matches the
"flaw the paper names" note in the corpus files. Save the three memos to `examples/`.

---

## After all three return

Audit each skill's examples against the corpus (the most common failure is
plausible-but-overclaimed citations — verify every section/page reference against the
PDF). Then run the demo sequence from claude-thoughts.md §F: `/teaching-case` →
`/discussion-plan` (around C1) → `/objection-audit` (on S1), and promote the validated
outputs into `output/`. The throughline to show the room: at every step Claude is
*augmenting the teacher's reasoning*, never deciding — which is the paper's own thesis,
demonstrated rather than asserted.
