---
name: mba-research
description: Research a specific type of business through an MBA lens, produce a "teardown memo" artifact in the house style, and create a summary page in the Modern MBA Notion hub. Use when the user wants to research, analyze, or evaluate a business idea or business type (e.g. "research flipping cars", "should I open a food truck", "analyze vending machines as a business").
---

# MBA business teardown

Produces one memo per business type researched, in a fixed visual and analytical format, published as a Claude Artifact, with a matching entry created in Notion.

## Reference

`template-example.html` in this skill directory is a full worked example (fix-and-flip houses, Florida). Reuse its `<style>` block and article scaffolding **verbatim** for every new memo — only the content changes. Study its class vocabulary before writing:

- `.masthead` / `.stamp` / `h1` / `.dek` / `.byline` — title block with tag pills and a one-line subject/market/base-case byline
- `section` + `.snum` (`Section 00`, `Section 01`, ...) + `h2` + `.q` (the analytical question the section answers)
- `.kpi` — headline metrics grid (executive summary only)
- `.verdict` / `.verdict.warn` — callout boxes for the recommendation and any hard warning
- `.exhibit.wide` / `.exhead` (`Exhibit N` label + title) / `.exscroll` / `table` with `.n` (numeric, right-aligned), `.sub`/`.tot`/`.grand` row classes, `.pill.p-good/.p-mid/.p-bad`
- `.heat` table with `.h1c`–`.h4c` cell shading for the sensitivity grid
- one inline `svg.chart` if a chart earns its place (not required every time)
- `footer` — analytical-basis disclaimer + one-line list of frameworks applied

## Process

1. **Clarify the subject** (AskUserQuestion, unless the user already gave enough detail): the specific business type, target geography/market, the operator's profile (what edge or skills do they bring?), capital available, and time horizon. This maps directly to the byline and Section 01 capacity math.

2. **Research** (WebSearch/WebFetch): market size, typical costs/margins/cycle times, structural industry factors, and anything geography- or regulation-specific. Favor concrete, sourceable numbers over generic ranges.

3. **Apply the framework, in this order, every time.** Sections marked ★ are the core tables the user specifically wants in every memo — never skip the table itself on these, even if a section gets trimmed for time:
   - `Section 00` ★ Executive summary — KPI grid (the "first table") + a `.verdict` (or `.verdict warn`) with the recommendation stated in one bold sentence, then justified in 2-4 short paragraphs.
   - `Section 01` ★ Market definition & capacity — TAM → SAM → SOM funnel exhibit table, ending in whatever *actually* caps throughput (capital, cycle time, physical capacity — not demand).
   - `Section 02` Industry structure — Porter's Five Forces exhibit with a rating + one evidence-based sentence per force.
   - `Section 03` ★ Value chain / margin pool — exhibit table showing who extracts what from one transaction and who carries the risk for it.
   - `Section 04` Domain/geography-specific structural factors — the local rules, regulations, or market quirks a generic analysis would miss.
   - `Section 05` ★ Unit economics — exhibit table isolating any operator-specific advantage (labor, skill, network) separately from the deal P&L, then a second table with the full P&L for one transaction.
   - `Section 06` Annual operating model — scale to a full year, add overhead, and **charge the owner's time at market rate** to get to economic profit (not just cash profit).
   - `Section 07` ★ Sensitivity analysis — a two-variable heat-table plus one concrete adverse-case scenario table built from ordinary (not exotic) bad events.
   - `Section 08` (optional) — a comparative or structural insight, e.g. contrasting against a similar business archetype, if it sharpens the conclusion.
   - `Section 09` Risk register — ranked exposures with likelihood, impact, and a specific mitigation each.
   - `Section 10` Recommendation — restate the findings that converge on it, the recommended structure, what would change the recommendation, and 3-5 metrics to run the business on.

4. **Publish as a Claude Artifact** (HTML, using the template CSS verbatim). Give it a distinctive `<title>`, a favicon emoji, and a one-sentence `description`.

5. **Create the Notion entry.** The Notion Modern MBA hub page is `Modern MBA` (id `3d4ba21e-32d4-804a-bb07-fb3912f005ad`, under `Courses`). For a new business type, use `notion-create-pages` to create **one new sub-page under it**, named for the business type. Content is a condensed summary, not the full memo:
   - the recommendation (one bold sentence)
   - the KPI grid numbers
   - the top 2-3 risks
   - a link to the published Artifact for the full memo
   Keep this short — Notion is the index the user reads from; the Artifact is where the depth lives.

6. **Save the full memo to GitHub as Markdown.** Create `research/<slug>/README.md` (slug = the business type, e.g. `research/food-truck-austin/README.md`) with the entire memo converted faithfully to Markdown — every section, every exhibit table, every verdict callout (as blockquotes), the footer's analytical-basis note and frameworks-applied line. No CSS/HTML, just the data and text, so it stays diffable and greppable. Include links back to the Artifact and the Notion page at the top. This is the durable, complete backup; Notion holds the short summary, the Artifact holds the styled version, GitHub holds all the data.

7. Confirm to the user: what was researched, the one-line verdict, the Artifact link, the Notion page link, and the GitHub file path.

## Notes

- Every new chat about a *new* business type gets its own Notion sub-page under Modern MBA — never append multiple business types into one page.
- If the user is iterating on the *same* business type across messages in one chat, update the existing Artifact/Notion page rather than creating a new one.
- Numbers should be directional and clearly framed as estimates (see the footer's "ANALYTICAL BASIS" note in the example) — this is a structural teardown, not a certified forecast.
