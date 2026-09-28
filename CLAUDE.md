# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

There is no code to build, lint, or test here. This is a content repository: a durable Markdown archive for the `mba-research` skill, which researches a business type through an MBA lens and produces a "teardown memo." The repo has three parts:

- `.claude/skills/mba-research/SKILL.md` — the skill definition (full process, section-by-section framework, and publishing steps).
- `.claude/skills/mba-research/template-example.html` — the canonical HTML/CSS template (a worked fix-and-flip example) that every memo's Claude Artifact must reuse verbatim.
- `research/*.md` — one Markdown file per business type researched, plus `research/compare.md`, a living cross-memo index.

## The `mba-research` pipeline

Each invocation of the `mba-research` skill fans out to three destinations, and all three must stay in sync:

1. **Claude Artifact** (HTML) — the styled version, using `template-example.html`'s CSS verbatim.
2. **Notion** — a condensed summary sub-page under the "Modern MBA" hub page (id `3d4ba21e-32d4-804a-bb07-fb3912f005ad`), built around the five ★ tables only.
3. **This repo** (`research/<slug>.md`) — the full memo as plain Markdown, every section and exhibit table included, no HTML/CSS. This is the durable, complete backup and the only one meant to stay diffable/greppable.

Every memo follows the same fixed 11-section structure (Section 00–10: executive summary, market capacity, industry structure, value chain, domain factors, unit economics, annual operating model, sensitivity, optional comparative insight, risk register, recommendation). Sections marked ★ (00, 01, 03, 05, 07) must always contain their core table — see [MEMORY: Memo core tables] — even if surrounding prose is trimmed. Full detail on each section lives in `SKILL.md`.

**`research/compare.md`** is not a memo — it has no Notion page and no Section 00–10 structure. It is regenerated as the last step of *every* `mba-research` run (new or revised memo), pulling Section 00 and Section 06 figures from every file in `research/*.md`, and republished to the same Artifact URL (`https://claude.ai/code/artifact/dfeb0ddb-3c34-4fc8-af93-0a76addb5053` — always `url`-updated, never recreated). A request to "just update the compare table" re-triggers this same regeneration step against current `research/*.md` state, with no new research required.

## Working in `research/*.md`

- One file per business type, directly under `research/` (no subfolders), named `research/<slug>.md`.
- Each memo file starts with links back to its Artifact and Notion page, then mirrors the full section structure in Markdown (tables as Markdown tables, verdict callouts as blockquotes, footer as an "ANALYTICAL BASIS" + frameworks-applied note).
- If the user is iterating on the *same* business type within one chat, update the existing memo/Artifact/Notion page in place rather than creating a new one; a genuinely new business type always gets its own file and its own Notion sub-page.
- Numbers are directional, sourced estimates — not certified forecasts — and should be framed that way, consistent with the existing memos' footers.
