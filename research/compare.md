# Eleven Teardowns, One Table

**Artifact:** https://claude.ai/code/artifact/dfeb0ddb-3c34-4fc8-af93-0a76addb5053

Every business type this hub has torn down, side by side — capital, revenue, the bottom line after charging the owner's own time, the verdict, and the one constraint that actually decided it.

This is an index, not a new analysis. Every figure below is pulled directly from the named memo's own Section 00 (executive summary) and Section 06 (annual operating model). If a linked memo has since been updated, its own file in this directory is the current source of truth, not this table. **Regenerate this file and its artifact after every new or revised memo** — see the note at the bottom.

---

## CLEARS A REAL RETURN

| Business | Geography | Startup capital | Revenue / headline | Bottom line | Verdict | Real binding constraint |
|---|---|---|---|---|---|---|
| **[The Flipper's Underwriting Memo](used-vehicle-retail-florida.md)** — used-vehicle retail | Florida | $170,000 | $2.65M | $128,000 (econ. profit) | Proceed | Technician's own hours — the return is mostly donated skilled labor |
| **[Fifteen Thousand Cars a Day](coffee-kiosk-south-florida.md)** — drive-thru coffee kiosk | South Florida | $190,000 | $613,000 | $82,270 (econ. profit) | Proceed | Site traffic — needs 15,000+ vehicles/day passing the lease |
| **[Ninety Seconds a Pie](pizzeria-manhattan.md)** — Neapolitan pizzeria | Manhattan, NY | $305,000 | $1.12M | $88,024 (econ. profit) | Proceed, contingent | Pedestrian capture at a $26 ticket — needs a genuinely skilled pizzaiolo |

## CONDITIONAL — WORKS ONLY UNDER SPECIFIC TERMS

| Business | Geography | Startup capital | Revenue / headline | Bottom line | Verdict | Real binding constraint |
|---|---|---|---|---|---|---|
| **[Five Percent Above Breakeven](entry-level-cargo-ship-ownership.md)** — entry-level cargo ship ownership | Worldwide trade | $3.0M equity ($6.0M vessel, 50% LTV) | $15,800/day TCE (5% above cash breakeven) | $232,850 (residual owner income, base case) | Financeable, marginal | Freight-rate cycle timing — a leveraged single-asset bet, not a steady yield |
| **[Controlling Interest](gc-license-umbrella-florida.md)** — GC crew & lead brokerage | South Florida | n/a (existing GC license) | $1.58M | $69,799 (vs. ($152,042) if reclassified) | Works, legal risk open | Worker misclassification exposure under the federal control test |
| **[The Board Meets Once a Month](parking-lpr-miami.md)** — parking LPR compliance startup | Miami-Dade / Broward, FL | <$50,000 | $253,000 (@ 15 sites, growth year) | ($9,100) (econ. profit @ 15 sites) | Build it, solo first | HOA board sales-cycle velocity — not capital, hardware, or demand |
| **[The Ad Costs More Than the Cut](junk-removal-app-miami.md)** — junk-removal marketplace app | Miami-Dade, FL | <$30,000 | $183,040 (platform revenue @ 20 drivers) | $2,784 (econ. profit @ 20 drivers) | Local grind, not ad-funded | Customer-acquisition channel mix — paid ads cost more than the commission |
| **[The Platform Fee Is the Business](ai-receptionist-nyc.md)** — AI phone receptionist & booking agent | New York City | <$50,000 | $167,400 (@ 62 clients) | $620 (econ. profit @ 62 clients) | Rent first, build second | Owner trust & booking-system onboarding — not compute cost or demand |

## DOES NOT CLEAR A REAL RETURN, AS MODELED

| Business | Geography | Startup capital | Revenue / headline | Bottom line | Verdict | Real binding constraint |
|---|---|---|---|---|---|---|
| **[The Rent Eats First](coffee-walkin-manhattan.md)** — walk-in coffee counter | Manhattan, NY | $185,000 | $554,400 | ($8,582) (econ. profit) | Do not sign | Rent — occupancy alone runs ~25% of revenue |
| **[Three At-Bats a Year](fix-and-flip-houses-florida.md)** — residential fix-and-flip | Florida | ~$140,000 (working capital) | $1.02M (3 deals/yr) | ($9,062) (econ. profit) | Do not go full-time | Deal concentration — 3 at-bats/yr, no volume to average variance against |
| **[Sixty Pairs a Month, Still Underwater](sneaker-resale-nyc.md)** — sneaker resale | New York City | $75,000 | $123,600 (720 pairs/yr) | ($19,506) (econ. profit) | Do not go full-time | Operator's own hours — bandwidth-capped, not capital-capped |
| **[The Courts Are the Marketing](pickleball-gym-manhattan.md)** — pickleball club (segment) | Manhattan, NY | ~$10.76M (whole-club buildout est.) | $443,600 (pickleball segment only) | ($1.03M) (segment result; whole-club EBITDA $1.85M) | Not a profit center | N/A — a deliberate marketing/amenity spend, not a capacity problem |

---

## Three patterns across twelve businesses

**The analytical question:** What, if anything, generalizes across a coffee kiosk, a cargo ship, and an AI phone receptionist?

- **Capital is almost never the real constraint.** Only the cargo ship and the pickleball club are genuinely capital-bound at entry; every other memo's real ceiling is time, a site's traffic, a legal test, a counterparty's decision calendar, or a trust/sales problem — not the size of the check the founder can write.
- **"Charge the owner's time at market rate" flips more verdicts than any other single move in this hub.** Several of the non-"Proceed" rows above look genuinely good on a cash basis and only turn negative (or barely break even) once the owner's own hours are priced honestly — the fix-and-flip, the sneaker resale, the Manhattan coffee counter, and the AI receptionist's own $620-of-daylight base case all read as a fine business until that line is added.
- **Manhattan rent, volunteer/committee-style decision-makers, and crowded commodity-tech categories are the three recurring adversaries.** Every Manhattan memo in this hub (coffee, pizza, pickleball) is decided by occupancy cost or space allocation; every memo with a board, committee, or classification test (parking LPR, GC brokerage) is decided by how slowly or unpredictably an external party can move; and the AI receptionist memo shows a fourth pattern — a genuinely good margin built entirely on commodity inputs that any funded competitor can copy just as easily.

---

**ANALYTICAL BASIS** — "Bottom line" isn't a single uniform metric: most rows are economic profit after charging the owner's own time at market rate (each memo's Section 06); the cargo-ship memo instead shows residual owner income against a daily cash-breakeven rate, and the pickleball memo shows an isolated segment result against whole-club EBITDA, because those two businesses don't run on an owner-operator's priced-out labor the way the other nine do.

**MAINTENANCE NOTE** — This file and its companion Artifact (`https://claude.ai/code/artifact/dfeb0ddb-3c34-4fc8-af93-0a76addb5053`) must be regenerated as the last step of every future `mba-research` run — both for a brand-new memo and for an update to an existing one. See `.claude/skills/mba-research/SKILL.md` for the step and the artifact URL to republish to (not recreate).
