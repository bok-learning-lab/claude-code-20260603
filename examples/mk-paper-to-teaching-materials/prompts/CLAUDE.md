# CLAUDE.md — Decision-subject ethics (teaching project)

## What this project is

A worked example of using Claude Code to **build and run teaching material** for an
ethics-of-AI session, grounded in Jeff Behrends' co-authored paper:

> Grant, D. G., Behrends, J., & Basl, J. (2025). "What we owe to decision-subjects:
> beyond transparency and explanation in automated decision-making."
> *Philosophical Studies* 182, 55–85. (Open access, CC BY 4.0.)

Built for the *Summer of Claude* faculty workshop at Harvard's Bok Center. Jeff
Behrends is among the workshop participants, so the design choices throughout are made
to align with **his** paper's framework and its careful hedges — not with a generic
"AI ethics" take.

This folder is meant to be opened as a standalone Claude Code project — `cd` into it,
run `claude`, and everything you need is here.

## The self-referential point (read this first)

The workshop is teaching faculty to lean on an AI tool. Behrends' paper is precisely
about the **limits of relying on AI for consequential decisions about people.** That
tension is the lesson, not a problem to hide. So this project models the relationship
the paper *prescribes*:

- Claude **augments the instructor's own reasoning** and generates teaching material.
- Claude **never makes the consequential call** — it surfaces candidates for human
  judgment, drafts cases, maps arguments. The human stays the moral agent.
- That is exactly the "human-in-the-loop with genuine agential consideration" the
  paper contrasts (§7.3) with blind deference / automation bias.

If a skill or output ever positions Claude as the *decider* about how a person should
be treated, it has violated the paper it is built on.

## If you just opened this folder

The project follows an **inputs → prompts → output** trajectory. The source paper is in
`inputs/`, the planning/prompt docs (this file, the plan, the brainstorm, the walkthrough)
are in `prompts/`, and everything Claude generates lands in `output/`. The skills live in
`.claude/skills/`. Only `index.html` sits at the project root. Paths below are relative to
this `prompts/` folder.

Read in this order:

1. [../output/walkthrough.md](../output/walkthrough.md) — the conversational steps that
   produced this project, prompts shown verbatim, with the prompting principles called
   out. (It lives in `output/` because it is itself a generated artifact — a model of
   process documentation.)
2. [claude-thoughts.md](claude-thoughts.md) — the longer brainstorm; especially the
   skills catalog and the "what to avoid in front of Jeff" section.
3. [PLAN.md](PLAN.md) — three skill-build tasks designed to run in parallel.
4. [../output/README.md](../output/README.md) — the synthetic teaching corpus (generated output).
5. The paper itself: [../inputs/grant_behrends_basl.pdf](../inputs/grant_behrends_basl.pdf)
   (or the markdown digest [../inputs/grant_behrends_basl.md](../inputs/grant_behrends_basl.md)).

## What you might be here to do

- **Build one of the three teaching skills** (`/teaching-case`, `/discussion-plan`,
  `/objection-audit`). Open PLAN.md, find your task, follow it. Skills build to
  `.claude/skills/<skill-name>/`, which resolves under *this* folder, so they travel
  with the project when shared.
- **Run a session prep end-to-end** after the skills exist: generate a case, build a
  discussion plan around it, then pre-stress-test the student positions you expect.
- **Extend the corpus** with a case from your own course.

## The framework these skills apply (one-screen summary of the paper)

The paper defends the **Explainability Thesis**: in many contexts, decision-makers are
morally obligated *not* to base decisions about people on the outputs of black-box AI
systems. It grounds this not in **duties of transparency** (the standard "you must be
able to explain it" defense, which the paper argues is too narrow — the *Grounding
Problem*) but in the duty to show **due consideration** to decision-subjects.

Due consideration decomposes into **duties of consideration**:

- **Evidential consideration** (§5, constrains fact-finding). Black-box reliance fails
  three ways: degraded field **accuracy** / overfitting (§5.1, the "Jared" screener);
  **ignoring readily available evidence** a human wouldn't (§5.2, COMPAS + the excised
  brain-tumor neurologist); relying on **morally inadmissible evidence** (§5.3,
  redundantly-encoded race/gender, the Amazon "women's" résumé tool, proxies).
- **Practical consideration** (§7, constrains decision-making). Prohibited **decision
  rules** / the Kantian injunction against treating people as mere things (§7.1); and
  **agential consideration** (§7.2–7.3) — some decisions (jury verdicts, lethal force,
  punishment) must be made by full-blown moral agents who take responsibility. The
  **Juror Substitution** thought experiment carries this; HITL doesn't escape it if
  the human merely defers.

Two framing problems the paper also solves: the **Definition Problem** (what "black
box" means: high flexibility + high dimensionality + limited **rule transparency**,
§4) and the **Double Standard Problem** (why hold machines to a higher bar than human
experts, §6 — partly it generalizes to humans, but **interpretable models** are the
safer third option and humans have agential capacities).

## Alignment with the paper (the hard constraints)

These bind everything Claude does in this project:

- **Claude is never the decision-maker about a person.** See the self-referential
  point above. Frame Claude as augmenting the instructor and generating material.
- **Don't collapse transparency into due consideration.** The paper's central move is
  that due consideration is *broader* than, and not reducible to, transparency. Cases
  and discussion plans must keep the distinction live.
- **The Explainability Thesis is not absolute.** The authors say "often," "prima
  facie," "potentially overridable," "context-sensitive." Never present it as "never
  use black boxes." Don't oversell.
- **Interpretable models are safer, not a panacea** (§6). They are *less* prone to the
  failures, not immune.
- **Keep the three Problems distinct** (Definition, Double Standard, Grounding) and
  tie claims to a section or page when you can. Defensible beats vibes.
- **Black-box ≠ "any AI."** The paper's target is high-flexibility, high-dimensional,
  low-rule-transparency systems (§4) — not all automation.

## Conventions for this project

- **Skills live in `.claude/skills/<skill-name>/`** (at the project root) — project-scoped,
  so they travel.
- **`inputs/` is the read-only source paper.** Don't modify it. The planning/prompt docs
  live in `prompts/`. Everything Claude generates — cases, student arguments, quizzes —
  goes in `output/`.
- **Case and argument IDs are stable.** C1–C4 (cases) and S1–S3 (student arguments)
  must be preserved consistently across every skill output.
- **No emojis in any file.** Workshop-wide convention.
- **Markdown link syntax for file references** — `[C1](../output/cases/C1-recidivism.md)`
  — so they are clickable in the IDE.
- **Citations point to the paper.** Use section numbers (§5.2) and, where you have
  them, page numbers, so an instructor can defend any claim in front of the author.

## A note on the corpus

The cases and student arguments in `output/` are **synthetic** (generated artifacts), each
engineered to surface a specific move in the framework — including
[C3](../output/cases/C3-interpretable-alt.md), which is designed to *pass* the audit (the
construct-validity stress test), and the three student arguments, which are designed to be
instructively wrong in ways the paper diagnoses. See [../output/README.md](../output/README.md)
for the design rationale.
