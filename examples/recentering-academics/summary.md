# Recentering academics

A workshop project scaffold whose inputs are the **Harvard College Fields of Concentration** descriptions for academic year 2026–2027 — every primary and secondary field, captured from the official PDF as one markdown file per field, with provenance frontmatter (source PDF, page range, capture date, status). The project ships the corpus and the empty `operations/` and `outputs/` folders; the substantive work — what skills, prompts, or operations to apply to the corpus, and what artifacts to produce from it — is open for the workshop attendee to fill in.

This is the structural model the other day-4 example projects (`interview-coding`, `physics-interactives`, `texts-and-translation`, `research_helper`) follow: an `inputs/`-`operations/`-`outputs/` triad at the top of each project folder.

---

## What it is

The corpus is in `inputs/fields-of-concentration/`, split into two parallel directories:

- `primary/` — every primary field of concentration offered by Harvard College for 2026–2027, one markdown file per field. Coverage runs from Anthropology and Applied Mathematics through Theater, Dance, and Media; Women, Gender, and Sexuality; and the Special Concentrations option.
- `secondary/` — every secondary field, parallel structure.

Each file carries provenance frontmatter — source document, page range in the source PDF, capture date, owner, status — and then the field's official description. The source PDF itself is preserved at `inputs/fields-of-concentration.pdf`.

The `operations/` and `outputs/` directories are present and empty. The project does not yet ship skills, prompts, or generated artifacts. The shape is the contract: any workshop attendee who opens this folder is invited to fill the empty halves of the triad with their own work against the corpus.

---

## How we built it

The build to date is the corpus assembly:

1. **Acquire the source.** The official Harvard College *Fields of Concentration 2026–2027* PDF was captured as `inputs/fields-of-concentration.pdf`.
2. **Split into per-field markdown.** Each field's section was extracted into a standalone markdown file with provenance frontmatter (source PDF, printed pages, capture date, slug). The split into `primary/` and `secondary/` mirrors the source document's organization.
3. **Preserve, do not edit.** The field descriptions are reproduced as written. Edits and transformations belong in `outputs/`, not in the corpus.

The work past this point — the operations applied to the corpus, the artifacts produced from it — is what the empty halves of the folder structure invite.

---

## What you can translate this to

Because this project ships only the corpus, the translation pattern is simpler than the other day-4 projects: **a clean corpus with provenance metadata, ready for skills to operate on.**

Domains where the same shape applies almost without modification:

- **Any institutional catalog** — course catalogs, faculty directories, fellowship programs, departmental policy archives. Split into per-entry markdown with provenance frontmatter; skills then operate on the indexed corpus.
- **Comparative analyses across fields, programs, or institutions** — what concepts appear across humanities concentrations vs. STEM ones; how secondary fields position themselves relative to their primary counterparts; how a single field's description changed from year to year (when prior-year captures are added).
- **Generating teaching artifacts from a structured catalog** — handouts for prospective students, advising scripts, comparative tables, summary writeups.

Candidate operations the workshop attendee could implement against this corpus:

- A skill that, given a student's intellectual interests, surfaces three to five candidate fields with the official descriptions that map to those interests.
- A skill that produces a comparative analysis of two fields (e.g. History and History and Literature) — what each program emphasizes, what they share, where they diverge.
- A skill that generates a single-page advising handout for any field, drawn verbatim from the official description with a section the advisor can edit.
- An analysis pass that surfaces vocabulary and conceptual patterns across the corpus — what words recur in humanities descriptions, what words recur in STEM descriptions, and what the rhetorical conventions of each are.

---

## Alignment constraints

These apply if work is added to this project:

- **Preserve the official descriptions verbatim** in `inputs/`. Edits, summaries, or comparative analyses go in `outputs/`.
- **Cite by field name and source PDF page**, not by file path. The corpus's structure is the catalog, not the file system.
- **Provenance is part of the artifact.** Any output should be traceable back to the source descriptions it drew on.
- **No emojis.** Markdown link syntax for file references.
