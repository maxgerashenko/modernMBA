# Fifty-Eight Cups to Breakeven

*Full styled memo: [Claude Artifact](https://claude.ai/code/artifact/f6d3e073-5a71-4156-a225-9449f45cad36) · [Notion summary](https://app.notion.com/p/3e0ba21e32d4819db05ef8eacc1efde9?pvs=204)*

**Underwriting Memo · Bubble Tea Concession Table · Inside a 16-Court Pickleball Facility**

An MBA-style teardown of a single manual-mix bubble tea table operating rent-free inside a 16-court pickleball facility — where a captive, exercising audience and a near-zero fixed-cost structure combine to make hired labor the only real cost in the business.

**SUBJECT:** one-table hand-mixed drink concession, no automation, hired counter labor
**VENUE:** dedicated 16-court indoor pickleball facility, 6:30am–10pm, informal zero-fee vendor arrangement
**BASE CASE:** $5,350 startup capital, 100 cups/day at an $8.00 ticket
**COMPANION TO:** [the retail hand-shaken bubble tea memo](bubble-tea-nyc.md) and [the Manhattan pickleball club memo](pickleball-gym-manhattan.md) in this repo

---

## Section 00 — Executive summary

**The analytical question:** Should an operator run a single hand-mixed drink table inside a busy pickleball facility under a zero-fee vendor arrangement, and what does the deal actually depend on?

| KPI | Value | Note |
|---|---|---|
| Startup capital | $5,350 | a water boiler, a POS, and opening inventory |
| Revenue, base case | $280,000 | 100 cups/day, $8.00 ticket, 350 days/yr |
| EBITDA pre-owner comp | $96,075 | 34.3% of revenue |
| Economic profit | **$88,575** | after charging owner's oversight time at market rate |
| Breakeven volume | 58 cups/day | vs. 100/day base case — a 1.7x margin of safety |

> **Recommendation:** Proceed — this is the most favorable unit economics in this hub, and it isn't close. But the entire model rests on one thing that currently has zero legal protection: the facility's willingness to keep letting this table operate for free.
>
> Strip out rent, a payment-processing fee, marketing, and almost every fixed cost a retail bubble tea shop carries, and what's left is close to the purest possible version of this business: one person, one table, one water boiler, selling into a room full of people who just finished exercising and have nowhere else to buy a drink. Hired labor at $21/hour is effectively the only real cost in the model, and it's a fixed daily cost, not one that scales with cups sold — every cup past the 58th cup of the day is nearly pure margin.
>
> Section 01 estimates the facility can plausibly deliver ~437 player-visits a day at realistic utilization; capturing just 13.3% of that traffic covers the day's costs, and the base case assumes 23% — roughly 1.7x the breakeven rate. Section 07 shows this holds up even under a fairly severe combined adverse scenario.
>
> The one line item this memo cannot model with a spreadsheet is the arrangement itself. "Zero fee for using equipment" is not a lease — it's a handshake, and Section 04 and Section 09 treat it as the central risk it is. Section 10's first recommendation is not a growth idea; it's getting this deal in writing before scaling it.

---

## Section 01 — Market definition and capacity

**The analytical question:** How much daily traffic does a 16-court facility actually generate, and what capture rate does this table need to break even?

This isn't a TAM/SAM story — pickleball's broader growth is irrelevant to a single table inside one specific building. What matters is the facility's own court-hours, and how much of that traffic a single, exclusive vendor can convert into a cup sold.

**Exhibit 1 — Traffic funnel: court capacity to daily cups**

| Layer | Definition | Value |
|---|---|---:|
| Facility ceiling | 16 courts × 4 players × 12.4 turns/day (100% utilization, 75-min sessions, 15.5 hrs open) | 794 visits/day |
| Realistic traffic | At 55% blended utilization — busier mornings/evenings, lighter midday | 437 visits/day |
| **SOM — base case** | **At a 23% assumed capture rate (sole vendor, captive post-exercise audience)** | **100 cups/day** |
| Breakeven | Minimum capture rate that covers fixed costs (Section 07) | 13.3% → 58 cups/day |

*Even at the facility's full 100% theoretical utilization, breakeven only requires capturing 7.3% of traffic (58 ÷ 794) — a very low bar for the only drink table in the building.*

Capacity math, stated directly:
- **Session length:** pickleball reservations typically run 60–90 minutes; this model blends to 75 minutes including changeover.
- **Turns/court/day:** 15.5 open hours ÷ 1.25 hours = 12.4 turns, if a court were booked continuously.
- **Concurrent capacity:** 16 courts × 4 players (doubles) = 64 players present at any given fully-booked moment.
- **Capture rate:** unlike the retail bubble tea memo's ~1% street-corridor capture, a captive, single-vendor, post-exercise crowd with no walk-away option plausibly converts at 15–25% — this model uses 23% as the base case.

Labor throughput is not the constraint here. Manual hand-mixing at roughly 2–3 minutes per cup gives one person a realistic capacity of 20–25 cups/hour — 310–388 cups across a full 15.5-hour shift, several times the 100-cup base case. The constraint is entirely traffic and capture rate, not production.

---

## Section 02 — Industry structure: Five Forces

**The analytical question:** What return does this position earn, and why is it structurally different from a street-retail bubble tea shop?

**Exhibit 2 — Force assessment**

| Force | Rating | Evidence |
|---|---|---|
| Supplier power (tea, tapioca, sweeteners) | Low–Medium | Same commodity inputs as any bubble tea operation; no meaningful lock-in. |
| Buyer power | **Low** | The inverse of the retail memo's finding. A player who just finished a match, inside a building with no other beverage vendor, has no real walk-away option in the moment — a genuinely captive audience. |
| Threat of entry | **Low, contingent** | Low *as long as the arrangement stays exclusive*. If the facility can bring in a second vendor or a vending machine at will, this rating flips to High overnight — see Section 04. |
| Substitutes | Medium | Players can bring their own water or a cooler. Real, but weaker than in a street setting — many don't plan ahead, and a cold, ready-made drink after a match is a genuine impulse purchase. |
| Rivalry | **None currently** | Sole vendor inside the facility, per the stated arrangement. |

*Four of five forces favorable — almost a mirror image of the retail bubble tea memo in this hub, where four of five forces were unfavorable. The one force that matters most here isn't on this list at all: whether the facility keeps the arrangement exclusive and in place.*

---

## Section 03 — Value chain and margin pool

**The analytical question:** Of every dollar a player spends, who takes what — and who carries the risk?

**Exhibit 3 — Value extracted per $8.00 cup, base-case volume**

| Participant | Take | Capital / risk at stake | Quality |
|---|---:|---|---|
| Payment processor | $0.00 (0%) | No processing fee in this model — cash/no-fee payment assumed. | N/A |
| Tea, ingredient & packaging suppliers | $2.00 (25.0%) | None. Paid on delivery. | Excellent |
| Facility ("landlord") | $0.00 (0%) | **None — and that's the whole story.** No rent, no revenue share, no equipment fee, as currently arranged. | — |
| Hired production labor | $3.26 (40.8%) | Wage risk only. Shown here allocated at base-case volume — the underlying cost is actually a fixed $325.50/day regardless of cups sold (Section 05). | Good |
| Overhead | $0.00 (0%) | No marketing, no allocated overhead in this model. | — |
| **Owner, before charging own time** | **$2.74 (34.3%)** | **All of it** — the full $5,350 invested, and total exposure to whether an informal, unwritten arrangement continues. | Best |

*With the landlord's usual 15–25% cut removed entirely, the owner's residual take (34.3% before even charging their own time) is dramatically higher than any other memo in this hub. The near-total absence of a "landlord" row is the single biggest driver of that result.*

---

## Section 04 — Facility-arrangement-specific structural factors

**The analytical question:** What does depending on someone else's free equipment and floor space do to this model that a generic bubble tea analysis would miss?

**Exhibit 4 — Arrangement-specific factors and their transmission**

| Factor | Effect | Mechanism |
|---|---|---|
| No written vendor agreement | **Dominant risk** | "Zero fee" is currently a verbal or informal understanding, not a lease or contract. It can be revoked, renegotiated, or made non-exclusive at the facility's discretion, with no notice period and no recourse. |
| Food-service permitting still applies | Mandatory, modest cost | Operating for free doesn't exempt the table from local health-department mobile/temporary food-service permitting — already budgeted at $600 in Section 05, but confirm the specific permit class with the local health department before opening. |
| Vendor liability insurance | Mandatory, modest cost | Operating inside someone else's facility typically requires a certificate of insurance naming the facility as additional insured — budgeted at $200/yr in Section 05; confirm the facility's specific requirement. |
| Electricity/water dependency | Operational dependency | The water boiler and any refrigeration draw power and water the facility is currently providing free as part of the arrangement — a real operating cost if that ever changes. |
| Indoor, weather-independent | Favorable | A 6:30am–10pm indoor facility has none of the seasonal foot-traffic swings a street-retail memo in this hub has to model — a genuine structural advantage. |
| Facility's own hours and policies | Dependency | Revenue is entirely downstream of the facility's own operating hours and any future changes to them (e.g., reduced hours, a private-event closure, a change in session length). |

---

## Section 05 — Unit economics

**The analytical question:** What does it cost to open, and what does one cup actually earn?

### What it costs to open

**Exhibit 5 — Startup capital, 16 lines**

| # | Line | Amount | Note |
|---|---|---:|---|
| 1 | Lease security deposit | $0 | No lease — informal facility arrangement |
| 2 | Buildout / tenant improvement | $0 | A table inside existing facility space |
| 3 | Water boilers & tea brewing station | $3,500 | The only real capital equipment purchase |
| 4 | Cup sealing machines | $0 | None used — simplified menu |
| 5 | Hand-shake mixing station | $0 | Fully manual |
| 6 | Commercial refrigeration | $0 | Provided free by the facility |
| 7 | Ice maker | $0 | Provided free by the facility |
| 8 | POS system & hardware | $250 | |
| 9 | Furniture & fixtures | $0 | One table, provided |
| 10 | Signage | $0 | None planned |
| 11 | Initial ingredient inventory | $400 | |
| 12 | Cups, lids, straws, packaging | $400 | |
| 13 | Permits & licenses | $600 | Mobile/temporary food-service permit |
| 14 | Opening marketing | $0 | Captive audience — none planned |
| 15 | Insurance | $200 | Vendor liability, facility as additional insured |
| 16 | Working capital buffer | $0 | **Zero cushion — flagged directly in Section 09** |
| **—** | **Total startup capital** | **$5,350** | |

*The water boiler is 65% of total startup capital. This is about as lean as a food-and-beverage business can be built — which is exactly why the $0 working capital buffer is worth taking seriously rather than treating as a rounding error.*

### Per-cup P&L

Labor here is a fixed daily cost — one person staffing the table for the facility's full 15.5-hour day at $21/hour, or $325.50/day — not a cost that scales per cup. The table below allocates it at the base-case 100 cups/day for illustration; the real breakeven math is done on a daily basis in Section 07.

**Exhibit 6 — Per-cup P&L, base case**

| Line | Amount | Note |
|---|---:|---|
| Ticket price | $8.00 | |
| COGS | ($2.00) | Simplified single-line ingredient cost |
| Card processing (0%) | $0.00 | No processing fee in this model |
| Hand-shake production labor (allocated at base-case volume) | ($3.26) | $325.50/day ÷ 100 cups — actually fixed, not per-cup |
| Occupancy (allocated) | $0.00 | Zero-fee facility arrangement |
| Overhead (allocated) | $0.00 | |
| **Net before owner's own time** | **$2.74** | 34.3% of ticket |
| Owner's oversight time (allocated) | ($0.21) | $7,500/yr ÷ 35,000 cups |
| **Economic net** | **$2.53** | 31.6% of ticket — positive on every cup sold |

---

## Section 06 — Annual operating model

**The analytical question:** What does a full year earn once the owner's own oversight time is priced in?

**Exhibit 7 — Annual P&L, base case**

| Line | Amount | Note |
|---|---:|---|
| Revenue | $280,000 | 100 cups/day × $8.00 × 350 days |
| COGS | ($70,000) | $2.00/cup, 25.0% |
| Card processing | $0 | 0% |
| Hired production labor | ($113,925) | 15.5 hrs/day × 350 days × $21/hr — the only real fixed cost |
| Occupancy | $0 | Zero-fee facility arrangement |
| Overhead / marketing | $0 | |
| **EBITDA before owner compensation** | **$96,075** | 34.3% of revenue |
| Owner's oversight time at market rate (5 hrs/wk × 50 wks × $30/hr — sourcing, facility relationship, bookkeeping) | ($7,500) | Not the hands-on table shift, which the $21/hr hire covers |
| **Economic profit** | **$88,575** | 31.6% of revenue |

*350 operating days/year assumed, allowing for occasional facility closures/holidays. Every dollar of the $113,925 labor line buys 15.5 hours of table coverage matching the facility's own operating hours — the single lever most worth testing against actual traffic patterns (Section 10).*

### The early-trial scenario: 20 cups/day

Before traffic and capture rate are validated, 20 cups/day is a realistic first-weeks number — well below the 58-cup breakeven. Run the same annual model at that volume, holding full 15.5-hour staffing fixed, to see exactly what an under-trafficked trial period costs:

**Exhibit 7b — Annual P&L, 20 cups/day scenario**

| Line | Amount | Note |
|---|---:|---|
| Revenue | $56,000 | 20 cups/day × $8.00 × 350 days |
| COGS | ($14,000) | $2.00/cup, 25.0% |
| Card processing | $0 | 0% |
| Hired production labor | ($113,925) | Unchanged — still 15.5 hrs/day × 350 days × $21/hr |
| Occupancy | $0 | |
| Overhead / marketing | $0 | |
| **EBITDA before owner compensation** | **($71,925)** | Labor alone exceeds revenue by over 2x |
| Owner's oversight time | ($7,500) | |
| **Economic profit** | **($79,425)** | Matches Exhibit 8's 20-cups/$8.00 cell exactly |

*At 20 cups/day, revenue doesn't even cover the fixed labor line — let alone COGS or owner comp. This is the clearest evidence in the memo that staffed hours must track validated traffic rather than the facility's full 15.5-hour window: at this volume, cutting to roughly 3–4 staffed hours/day (covering only the highest-traffic window) would turn a $79,425 loss into something close to breakeven, without losing meaningful sales the other 11+ hours weren't generating anyway.*

---

## Section 07 — Sensitivity analysis

**The analytical question:** What's the breakeven traffic level, and how does economic profit move with daily cups and average ticket?

**Exhibit 8 — Economic profit by daily cups and average ticket — zoomed on the breakeven zone**

| Cups/day | $6.00 | $7.00 | $8.00 — base ticket | $9.00 |
|---|---:|---:|---:|---:|
| 5 | ($114,425) | ($112,675) | ($110,925) | ($109,175) |
| 10 | ($107,425) | ($103,925) | ($100,425) | ($96,925) |
| 15 | ($100,425) | ($95,175) | ($89,925) | ($84,675) |
| 20 | ($93,425) | ($86,425) | ($79,425) | ($72,425) |
| 25 | ($86,425) | ($77,675) | ($68,925) | ($60,175) |
| 30 | ($79,425) | ($68,925) | ($58,425) | ($47,925) |
| 35 | ($72,425) | ($60,175) | ($47,925) | ($35,675) |
| 40 | ($65,425) | ($51,425) | ($37,425) | ($23,425) |
| 45 | ($58,425) | ($42,675) | ($26,925) | ($11,175) |
| 50 | ($51,425) | ($33,925) | ($16,425) | $1,075 |
| 55 | ($44,425) | ($25,175) | ($5,925) | $13,325 |
| 60 | ($37,425) | ($16,425) | $4,575 | $25,575 |

*Fixed costs held at $121,425/yr throughout (labor + owner oversight time). At the $8.00 base ticket, the sign flips between 55 cups/day (still ($5,925)) and 60 cups/day (+$4,575) — consistent with the exact 58-cup/day breakeven computed above. This range deliberately zooms into the early-trial volume band; the wider 100-cup/day base case ($88,575) and 130-cup/day upside ($151,575) sit well above what's shown here.*

Breakeven, restated in traffic terms: 58 cups/day against an estimated 437 realistic daily visits is a **13.3% capture rate** — roughly 1.7x below the 23% base-case assumption. Even at the facility's full theoretical 794-visit ceiling, breakeven only needs a 7.3% capture rate. For reference, the wider volume range: 80 cups/day at the $8.00 ticket clears $46,575; the 100-cup/day base case clears $88,575; 130 cups/day clears $151,575 — all well outside Exhibit 8's zoomed-in range, which exists specifically to make the first few weeks of a real trial legible against breakeven, cup by cup.

### The scenario the grid doesn't show

Exhibit 8 varies cups and ticket. It holds the facility arrangement, staffing, and utilization fixed. A realistic adverse case, stacking three ordinary events onto the base case:

**Exhibit 9 — Adverse case — nothing exotic**

| Event | Impact | Comment |
|---|---:|---|
| Base case profit | $88,575 | |
| Realized utilization runs well below plan (55%→40%), cups fall 100→73/day | ($56,700) | The single largest lever in this memo — traffic, not price |
| Facility renegotiates to a 10% revenue-share fee after seeing the table succeed | ($20,440) | A realistic outcome of an informal, unwritten arrangement (Section 04) |
| Hired staff calls out; 2-week temp coverage at +$4/hr | ($868) | Ordinary staffing gap |
| **Adverse case result** | **$10,567** | Still positive — but an 88% drop from the base case |

*Even a materially worse traffic outcome, a new facility fee, and a staffing hiccup — all in the same year — leave this business barely above breakeven rather than in a loss. That resilience comes entirely from the near-zero fixed-cost base; it does not protect against the arrangement being terminated outright, which no sensitivity grid can price (Section 09).*

---

## Section 08 — What zero rent is actually worth

**The analytical question:** How does this compare to the retail hand-shaken bubble tea memo in this hub, selling the same product?

This hub already underwrote a hand-shaken bubble tea counter as a street-retail business (Flushing/Elmhurst, Queens). Same product, same manual-mixing method, wildly different result — and the difference isolates almost entirely to two line items: rent, and buyer power.

**Exhibit 10 — Retail storefront vs. captive-venue concession**

| Dimension | Retail bubble tea (this hub) | Pickleball concession (this memo) |
|---|---|---|
| Startup capital | $193,000 | $5,350 |
| Occupancy cost | 15.1% of revenue | 0% |
| Buyer power | High — dozens of competing boba shops nearby | Low — captive, single-vendor audience |
| Card processing | 3.0% | 0% |
| Labor as % of revenue | 31.0% | 40.7% |
| **Economic profit** | **($24,856)** | **$88,575** |

*Labor eats a slightly larger share of revenue here — but with rent, card fees, and buyer-power-driven price competition all removed, the business still ends up over $113,000 better off on the bottom line. Rent alone was worth roughly $72,000/year in the retail memo; that entire line is zero here.*

**The lesson isn't "captive venues beat retail" in the abstract** — it's that a single removed cost line (rent) and a single flipped structural force (buyer power) did more for this business's economics than any menu, pricing, or automation decision could. That's also exactly why Section 04 and Section 09 treat the informality of the arrangement that makes both of those things true as the single largest risk in the memo.

---

## Section 09 — Risk register

**The analytical question:** What can end this business, how likely is it, and what specifically prevents it?

**Exhibit 11 — Ranked exposures**

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Informal arrangement revoked or made non-exclusive | Unknown — untested | Catastrophic | **The single most important action in this memo.** Get a simple written vendor agreement — even a short-form license with a 30/60-day notice period and an exclusivity clause — before investing further or scaling hours. |
| Zero working capital buffer | Certain exposure | High | Retain the first 4–6 weeks of profit as a cash cushion rather than distributing it, given the $5,350 startup carries no built-in buffer. |
| Utilization runs below the 55% assumption | Medium | High | Track actual court bookings for 2–4 weeks before finalizing staffed hours; the largest single lever in Section 07's adverse case. |
| Facility later imposes a fee or revenue share | Medium | Moderate | Address proactively in the written agreement (above) rather than reactively; the business tolerates a modest fee (Section 07) but not an open-ended one. |
| Single point of labor failure | Medium | Moderate | Cross-train a second person; the business has no coverage plan if the one hired staffer is unavailable. |
| Permit/insurance gap | Medium | Moderate–High | Confirm the specific mobile/temporary food-service permit class and the facility's insurance requirement before opening, not after (Section 04). |

---

## Section 10 — Recommendation

**The analytical question:** Given all of it, what should this operator do?

Five findings converge:
1. **The base case clears a strong economic profit** — $88,575 on $5,350 of startup capital — the best capital efficiency of any memo in this hub (Section 06).
2. **Breakeven traffic is low and forgiving** — 58 cups/day against a 100/day base case, or just 13.3% of estimated realistic traffic (Section 01, 07).
3. **Four of five competitive forces favor this position**, inverting nearly every problem the retail bubble tea memo found (Section 02, 08).
4. **The business tolerates real adversity** — a traffic shortfall, a new facility fee, and a staffing gap together still leave it barely positive (Section 07).
5. **None of that resilience covers the one risk that actually matters** — the arrangement has no contract, no notice period, and no exclusivity guarantee (Section 04, 09).

> **Recommended structure:** Proceed, but sequence it correctly: get a written vendor agreement with the facility before scaling past a trial period, hold back the first several weeks of profit as a cash buffer instead of the modeled $0, and validate actual court utilization against the 55% assumption before committing to full-day staffing.
>
> Because labor is the only real fixed cost and it's tied to the facility's full operating hours, the highest-leverage optimization once the arrangement is secure is matching staffed hours to actual traffic patterns — likely reducing coverage during the lowest-traffic midday window rather than staffing all 15.5 hours uniformly.

### What would change this recommendation
- **The facility declining to formalize the arrangement** — a hard stop on scaling, regardless of how good the unit economics look on paper.
- **Actual measured utilization coming in well under 40%** — Section 07's adverse case shows this alone cuts profit by nearly two-thirds.
- **A facility-imposed fee beyond roughly 10–15% of revenue** — the point at which the arrangement starts to resemble the retail memo's rent burden rather than a genuine zero-cost advantage.

### Metrics to run it on
- **Cups/day** — against the 100 base case and the 58-cup breakeven floor, tracked daily from week one.
- **Capture rate** — cups ÷ estimated daily player-visits, against the 23% base case and 13.3% breakeven.
- **Staffed hours vs. actual traffic curve** — the clearest lever to cut the $113,925 labor line without losing sales.
- **Status of the written vendor agreement** — not a financial metric, but the one item this memo treats as a precondition for scaling.
- **Cash reserve built** — against a self-imposed 4–6 week buffer target, given the $0 modeled working capital.

---

**ANALYTICAL BASIS** — Figures are directional estimates for a single-table, manually-operated bubble tea concession inside a 16-court indoor pickleball facility, built for structural analysis rather than as an audited forecast. Court utilization, capture rate, and staffing hours are the most consequential unvalidated assumptions in this memo and should be checked against 2–4 weeks of actual facility traffic before capital commitments beyond the modeled $5,350. The zero-fee vendor arrangement is treated throughout as the memo's central structural risk, not a stable input; it is not a substitute for a written agreement and is not legal advice.

**FRAMEWORKS APPLIED** — Venue-capacity funnel (court-hours to daily cups) in place of a traditional TAM/SAM/SOM · Porter's Five Forces, adapted for a single-vendor captive-audience setting · Value chain and margin-pool analysis · Arrangement-specific structural risk analysis in place of geography-specific factors · Bottom-up unit economics with startup-capital decomposition and fixed-vs-allocated labor treatment · Two-variable sensitivity with breakeven-traffic solve · Adverse-case scenario · Cross-memo structural comparison (captive venue vs. retail storefront) · Risk register · Economic profit adjustment for owner labor.
