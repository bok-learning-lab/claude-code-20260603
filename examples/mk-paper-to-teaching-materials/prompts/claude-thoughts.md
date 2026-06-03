# claude-thoughts — brainstorm for a teaching project on Grant, Behrends & Basl (2025)

A working brainstorm of ways a philosopher could use Claude Code to **teach** the
ethics of automated decision-making, grounded in this specific paper and aligned with
Jeff Behrends' framework. Skills first; the workshop demo scopes three of them.

## A. What the paper gives a teacher to work with

The paper is unusually teachable because it is *built from distinctions and cases*:
- A headline thesis with careful hedges (the Explainability Thesis — "often," "prima
  facie," overridable).
- A reframing move (transparency → due consideration) that students can be walked
  *through*, not just told.
- A clean taxonomy (evidential vs. practical; substantive vs. procedural; global vs.
  local rules) that maps onto discussion structure.
- Memorable cases already in the text: Sacco & Vanzetti / TEALEAVES, the brain-tumor
  neurologist, the Amazon "women's" résumé tool, Juror Substitution, lethal
  autonomous weapons.
- Three named "problems" (Definition, Double Standard, Grounding) that are ready-made
  objection-handling exercises.

## B. Teaching use cases (the menu)

1. **Generate cases engineered to isolate one move** (accuracy, ignoring evidence,
   inadmissible evidence, agential consideration) — varying domain (lending, bail,
   admissions, medicine, hiring) so students see the structure recur.
2. **Build Socratic discussion plans** that walk students from the intuitive
   transparency answer to the due-consideration reframing.
3. **Stress-test student arguments** against the framework — steelman, then diagnose
   which distinction is missed or which Problem the argument falls to.
4. **Map the argument** of the paper to a one-page diagram for a lecture.
5. **Generate a reading guide / pre-class questions** tied to section and page.
6. **Produce an exam or problem-set item** with a rubric keyed to the distinctions.
7. **Run a structured debate** — assign the three Problems as positions, with prep
   memos for each side.
8. **Cross-domain transfer set** — take one case (say bail) and reskin it into
   medicine and lending so students practice spotting the same duty.

## C. Skills catalog (each tied to the paper)

- `/teaching-case` — generate a student-facing case (system dossier or thought
  experiment) plus instructor notes, engineered to surface a chosen move, tagged to a
  section/page. *(Demo skill 1.)*
- `/discussion-plan` — a Socratic sequence for a given case or section: warm-up, core
  dilemma, the positions students will take (anticipating S1–S3), the objection to
  steer toward, and the move that addresses it; honest about what the case can and
  can't show. *(Demo skill 2.)*
- `/objection-audit` — steelman a student argument, then diagnose it against the
  framework with citations; never just "wrong," always "right about X, misses Y."
  *(Demo skill 3.)*
- `/quiz` — generate a short-answer comprehension check on the core argument, with a
  student version and an instructor answer key. *(Built.)*
- `/map-argument` — render the paper's structure as a diagram/outline for lecture. *(Unbuilt.)*
- `/reading-guide` — pre-class questions keyed to sections. *(Unbuilt.)*
- `/rubric-item` — exam/problem-set prompt + rubric keyed to the distinctions. *(Unbuilt.)*

The first four (`/teaching-case`, `/discussion-plan`, `/objection-audit`, `/quiz`) are now
built under `.claude/skills/`, each with a `SKILL.md` and validated `examples/`; demo runs
are promoted to `../output/`. The last three remain open extensions.

The demo trio — `/teaching-case`, `/discussion-plan`, `/objection-audit` — covers the
arc a teacher actually runs: make the material, plan the conversation, anticipate the
pushback. They mirror the gallery's interview-coding trio (build / write-up /
counter-evidence) but in a teaching register.

## D. MCP candidates (Code-only; mention, don't necessarily build)

- A **Canvas** MCP to push generated cases, reading guides, and rubrics straight into
  a course site.
- A **PDF/citation** MCP to pull exact page numbers from the source paper so every
  generated claim is anchored.
- A **Drive** MCP to drop discussion plans into a shared teaching folder.

## E. What to avoid in front of Jeff (the alignment guardrails)

This section is the analog of "never pitch LLMs as discovering themes in front of
Mary." Get these wrong and the project undercuts the paper it teaches.

1. **Never frame Claude as the decision-maker about a person.** The whole paper is
   about the limits of that. Claude makes *teaching material*; it does not adjudicate.
2. **Never present the Explainability Thesis as absolute.** It is hedged throughout
   ("often," "prima facie," "potentially overridable"). A case or plan that says "never
   use AI for decisions" misrepresents the authors.
3. **Never collapse transparency into due consideration.** The paper's contribution is
   that the second is broader. Losing the distinction loses the paper.
4. **Never treat interpretable models as a cure-all** (§6). Safer, not immune.
5. **Never equate "black box" with "any algorithm."** §4 is specific: high
   flexibility + high dimensionality + low rule transparency.
6. **Never fabricate citations.** Anchor to a section; only give a page number when
   you can verify it against the PDF.

## F. Recommended demo sequence

For a live session: `/teaching-case` (generate or pull C1) → `/discussion-plan`
(build the seminar around it, anticipating S1–S3) → `/objection-audit` (run it on S1
live to show the steelman-then-diagnose pattern). That order — material, plan,
pushback — is the teacher's actual workflow, and it ends on the move that best
demonstrates Claude-as-augmentation rather than Claude-as-oracle.
