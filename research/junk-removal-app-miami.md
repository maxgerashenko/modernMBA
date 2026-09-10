# The Ad Costs More Than the Cut

**Artifact:** https://claude.ai/code/artifact/d07c02c6-2f78-45bb-b058-4870d8125f41
**Notion:** https://app.notion.com/p/3d7ba21e32d4818d94e7eb46104ee99b?pvs=204

An MBA-style teardown of an "Uber for junk removal" marketplace app in Miami-Dade — matching independent haulers with customers — and why paid advertising on either side of the marketplace is a trap the founder has to out-hustle, not fund.

**SUBJECT:** bootstrapped founder (<$30K), manual recruiting on both sides before paid spend
**MARKET:** Miami-Dade junk & bulk-item removal (furniture, appliances, debris)
**BASE CASE:** 20% commission per job, $220 avg job, scaling to 20–35 active drivers

---

## Section 00 — Executive summary

**The analytical question:** Should a bootstrapped founder build a driver-marketplace app for junk removal in Miami-Dade, and can advertising realistically fill either side of it?

| KPI | Value | Note |
|---|---|---|
| Avg job / commission | $220 / $44 | 20% take rate, before processing |
| Manual-channel CAC | ~$0 cash | FB groups, word of mouth — time-bound, not money-bound |
| Paid-ad cost / booked job | ~$115 | exceeds the entire $44 commission earned |
| Drivers for owner market-pay | ~20 | only if paid channels stay under ~15% of volume |
| Economic profit @20 drivers | $2,800 | essentially break-even vs. a market-rate job |

> **Recommendation: Proceed, but only as a grind-it-out local hustle — not an ads-fund-the-growth business.**
>
> The core arithmetic problem is direct: at a 20% commission on a $220 average job, the platform earns $44. A Facebook or Google lead for junk removal costs roughly $30–45 and converts to a booked job at best 25–35% of the time — call it ~$100–130 per booked customer once you pay for the ad. **Regular advertisement, run on its own, costs more than the platform makes on the job it buys.** Buying leads from Thumbtack instead doesn't fix it: junk-removal leads there run $18–60, commonly reported near 30% of the job's value — $60–70 on a $220 job, again close to or above the entire commission.
>
> The one channel with workable unit economics is the one the founder is already leaning toward: manually watching local Facebook groups, Marketplace "free stuff" and "services" posts, and community boards, and personally reaching out — not scraping them. Automated scraping of Facebook Marketplace/groups violates Meta's Terms of Service (it prohibits automated collection outright, and Meta has sued scrapers who used the data to send unsolicited messages) and is enforced with IP bans and account restriction. The manual version of the same idea is legal, and it's also the only channel in this model that's actually cheap — its real cost is founder time, not ad spend.
>
> Run that way, the model works: about 20 disciplined, mostly-organic drivers get the owner to roughly what a market-rate ops job pays. Lean on paid ads instead and the driver count needed to hit the same bar roughly triples — and at that point, simply becoming a driver on an already-built competing app (Section 08) pays about the same with none of the platform risk. This is a business that has to be built slowly and locally before it's worth funding with ad spend at all.

---

## Section 01 — Market definition and capacity

**The analytical question:** How large is the Miami-Dade junk-removal market, and what actually caps how fast this app can grow?

**Exhibit 1 — Market funnel, TAM to SOM**

| Layer | Definition | Value / yr |
|---|---|---|
| TAM | US professional junk-removal spend, 2025 | ~$15B |
| SAM — county | Miami-Dade share, by population (~2.7M of ~335M US) | ~$120M |
| SAM — segment | Residential furniture/appliance/debris jobs (excludes commercial contracts, franchised bulk waste) | ~$60–70M |
| **SOM — 1–2 yr** | **Capacity-bound: driver count × jobs/driver/week, not ad budget or demand** | **~$900K–1.6M (20–35 drivers)** |

*SAM figures are directional, apportioned from national industry revenue by population share — not a county-specific survey. The gap between ~$60–70M of addressable local spend and ~$1M of realistic year-1/2 volume is not a demand shortfall; it's bounded by how many drivers a bootstrapped founder can personally recruit and vet.*

The capacity math that actually governs this business:

- **Supply (drivers) is the harder side to build and the one paid ads can't efficiently solve.** Industry benchmarks for delivery/gig-platform driver acquisition run **$3,000–5,000 per driver** once you include recruitment marketing, background checks, onboarding, and early-churn losses — a figure built for companies with venture-scale budgets and national ad buys, not a <$30K bootstrap.
- The realistic channel is manual recruiting from Miami's existing pool of independent movers and haulers — the same people already listing "junk removal" and "hauling" services on Facebook Marketplace, Craigslist, and local classifieds. A background check runs ~$30–40/driver; that is the real cash cost per recruited driver, not $3,000+.
- One founder doing manual outreach on both sides can realistically recruit and vet a handful of drivers a month and generate a modest, steady trickle of customer leads from local groups — a few hours a day, capped by time, not money.
- A driver doing 3–5 jobs/week is a realistic utilization ceiling for a part-time gig vehicle owner; more than that starts to look like a full-time job, which changes who is willing to sign up.

Everything downstream in this memo — Sections 05 through 08 — is about what happens to the unit economics depending on whether growth is bought (ads, bought leads) or built (manual recruiting, word of mouth).

---

## Section 02 — Industry structure (Five Forces)

**The analytical question:** What return does a participant in this market earn, structurally, before any firm-specific advantage?

**Exhibit 2 — Force assessment**

| Force | Rating | Evidence |
|---|---|---|
| Supplier power (drivers/haulers) | Low–moderate | Miami has a real, visible pool of independent movers and truck/van owners already advertising hauling services — supply exists and is largely interchangeable. The problem is not their bargaining power, it's the cold-start cost of finding and vetting them. |
| Buyer power (customers) | High | A customer can get a quote from 1-800-GOT-JUNK, College Hunks, Junkluggers, an unbranded Marketplace hauler, or simply give the item away free on a local "Buy Nothing" group. Switching cost is zero and the service is fully commoditized on price and speed. |
| Threat of new entry | High | Several national "Uber for junk removal" apps (GoShare, Curb-It, LoadUp) already exist and can enter any metro, including Miami, with far more capital. The technical barrier to building a similar marketplace app is low. |
| Substitutes | High | Miami-Dade offers scheduled bulk-item municipal pickup, typically bundled into existing solid-waste service — free to the resident. Giving usable furniture/appliances away on Facebook Marketplace or a "Buy Nothing" group is a strong, genuinely free substitute for exactly the item types this app targets. Renting a truck and self-hauling is a third. |
| Rivalry | High | National franchises, national apps, and a long tail of unbranded independent haulers already compete for the same Miami customer, with no obvious differentiation available to a new entrant besides possibly a lower commission or hyper-local responsiveness. |

*Four of five forces are unfavorable. The one bright spot — driver supply being available and low-power — is exactly the side of the marketplace paid advertising is worst suited to fix, which is the crux of this memo.*

---

## Section 03 — Value chain and margin pool

**The analytical question:** Of what a customer pays for one job, who takes what — and who carries the risk?

**Exhibit 3 — Value extracted per $220 job, 20% commission**

| Participant | Take | Risk carried |
|---|---|---|
| Payment processor | ~$7 | None. Metered per transaction. |
| Landfill / transfer station (tipping fee, paid by driver) | ~$20–40 | None — paid on delivery of the load. |
| Driver — fuel & vehicle wear | ~$15 | Owns and maintains the truck; carries the physical labor and any load/property damage risk on-site. |
| **Driver — net take-home** | **~$131** | For roughly 1–1.5 hours of work — a genuinely attractive gig rate, which is the platform's real pitch to drivers. |
| **The platform** | **$44 gross / ~$37 net of processing** | **Carries the customer-acquisition cost** (Section 05) and the marketplace liability exposure, but no vehicle, no dump fee, no physical labor. |

*The platform's $37 net take per job looks attractive until it is weighed against what it costs to generate the job in the first place — which is the entire subject of Section 05.*

---

## Section 04 — Miami-Dade-specific structure

**The analytical question:** What does this county's rules do to the model that a generic "gig marketplace" plan would miss?

**Exhibit 4 — Regional factors and their transmission**

| Factor | Effect | Mechanism |
|---|---|---|
| Miami-Dade Local Business Tax Receipt | Per-driver compliance burden | Anyone providing a service to the public in the county — including a one-person operation — must hold a Local Business Tax Receipt. In a 1099 model, this is most cleanly each driver's own obligation, but it's friction at onboarding that a generic gig-app plan wouldn't budget for. |
| Miami-Dade General/Small Hauler Permit | Open legal question — resolve before scaling | The county's Public Works & Waste Management department requires a hauler permit for "collection, removal or transport for disposal, hire or salvage" of solid waste over public right-of-way, and requires permit/LBT numbers marked on both sides of the vehicle. Whether an individual gig driver hauling occasional residential furniture/debris falls under this the same way a commercial waste hauler does is not clearly settled by the public guidance — get a specific answer from counsel before recruiting drivers at scale, not after. |
| Municipal bulk-item pickup programs | Free substitute | Many Miami-Dade municipalities bundle scheduled bulky-waste pickup into the existing solid-waste fee residents already pay — a free alternative that directly competes with exactly the job type (furniture, appliances) this app targets for non-urgent removals. |
| Facebook/Meta platform dependency | Growth-channel risk | The cheapest viable acquisition channel (Section 05) runs through Facebook groups and Marketplace, a platform the founder doesn't control. Automated scraping breaches Meta's Terms of Service and is actively enforced (IP blocks, account bans, and precedent litigation over unsolicited outreach from scraped data); manual, personal outreach at human pace is the only durable version of this channel. |
| Year-round demand, no strong seasonality | Stable | Unlike snowbird-driven categories, junk/bulk removal demand in Miami-Dade is driven by moving, renovation, and estate turnover, which runs fairly evenly year-round — a mild structural positive relative to seasonal local businesses. |

---

## Section 05 — Unit economics

**The analytical question:** What does it actually cost to fill each side of the marketplace, and does the arithmetic survive it?

### Driver-side acquisition: manual vs. paid

**Exhibit 5 — Cost to recruit one driver**

| Channel | Cost / driver | Note |
|---|---|---|
| Paid recruitment marketing, at scale (industry benchmark) | $3,000–5,000 | Includes ad spend, onboarding, and early-churn losses at large delivery platforms — built for venture-scale budgets, not this business. |
| **Manual outreach + background check (recommended)** | **$30–40** | Founder personally recruits from existing local mover/hauler pools already visible on Marketplace and Craigslist; the only real cash cost is the background check. |

*Regular paid advertisement to recruit drivers is not economically viable at bootstrapped scale — the industry's own acquisition-cost benchmark is 75–150× what a manually-recruited driver costs.*

### Demand-side acquisition: three channels compared

**Exhibit 6 — Effective cost per booked job, by channel**

| Channel | Lead cost | Close rate | Cost / booked job |
|---|---|---|---|
| Thumbtack-style bought lead | $18–60 (often ~30% of job value) | shared with 4–5 pros | ~$60–70 |
| Facebook/Google paid ads, own brand | $30–45 | ~25–35% | **~$100–130** |
| **Manual FB-group / Marketplace outreach + word of mouth** | **$0 cash** | time-bound | **~$0 cash** |

*Both paid channels cost more per booked job than the $44 the platform earns from a 20%-commission job — buying customer acquisition is a losing trade on a single-job basis at this commission rate. Manual outreach is the only channel that isn't.*

**Exhibit 7 — Per-job P&L, disciplined channel mix (15% paid)**

| Line | Amount | Note |
|---|---|---|
| Job price | $220 | Blended average across single-item and multi-item loads |
| Platform commission (20%) | $44.00 | |
| Payment processing (~3%) | ($6.60) | |
| Blended CAC — 15% paid-channel mix | ($13.50) | 0.15 × ~$90 blended paid-channel cost |
| Ops / support / per-job liability rider | ($4.00) | |
| **Net platform margin / job** | **$19.90** | 9% of job price — before fixed overhead |

*At a heavier, more ad-reliant mix (Section 07), this same job can go net-negative. The margin here depends entirely on keeping paid channels a minority of volume.*

---

## Section 06 — Annual operating model

**The analytical question:** What does a real driver fleet earn once overhead and the owner's own market wage are charged?

**Exhibit 8 — Annual P&L, 20 drivers, disciplined acquisition mix**

| Line | Annual | Per job |
|---|---|---|
| Jobs — 20 drivers × 4/week × 52 | 4,160 | — |
| Gross job volume | $915,200 | $220 |
| Platform commission revenue (20%) | $183,040 | $44.00 |
| Payment processing | ($27,456) | ($6.60) |
| Blended customer acquisition (15% paid mix) | ($56,160) | ($13.50) |
| Ops / support / liability rider | ($16,640) | ($4.00) |
| **Gross margin** | **$82,784** | **$19.90** |
| Fixed overhead (app/infra, background checks, base liability policy, admin/legal) | ($15,000) | — |
| **Profit before owner compensation** | **$67,784** | — |
| Owner compensation at market (platform ops/growth manager, FL) | ($65,000) | — |
| **Economic profit** | **$2,784** | — |

*At 20 drivers, holding paid-channel reliance to 15% of volume, the owner clears almost exactly a market-rate salary and nothing more. This is the real break-even scale, not the point at which the business becomes clearly worth building.*

**The number that moves this the most isn't driver count — it's channel discipline.** Push the paid-channel share from 15% toward 50% at the same 20% commission and net margin per job falls from $19.90 to roughly negative territory (Section 07); the entire annual model above collapses before it ever reaches the owner. Growing driver count without controlling the acquisition mix does not fix this — it just loses more money faster.

---

## Section 07 — Sensitivity analysis

**The analytical question:** Which matters more — the commission rate charged, or how much of the growth is bought versus built?

**Exhibit 9 — Net margin per job, by paid-channel share and commission rate**

| Paid-channel share | 15% commission | 20% commission | 25% commission | 30% commission |
|---|---|---|---|---|
| 0% | $22.40 | $33.40 | $44.40 | $55.40 |
| **15% (base)** | $8.90 | **$19.90** | $30.90 | $41.90 |
| 30% | ($4.60) | $6.40 | $17.40 | $28.40 |
| 50% | ($22.60) | ($11.60) | ($0.60) | $10.40 |

*$220 job, $6.60 processing, $4 ops/liability, ~$90 blended paid-channel cost. Reading down any column shows how fast paid-channel reliance erodes margin; reading across any row shows commission alone can't fully rescue a heavily-bought acquisition mix. Channel discipline is the more powerful lever, and it's the one the founder actually controls day to day — commission rate is constrained by what keeps drivers from leaving for a competing app.*

### The scenario the grid does not show

Exhibit 9 varies mix and commission. It holds job volume and close rates steady — an ordinary bad quarter at the 20-driver base case:

**Exhibit 10 — Adverse case, nothing exotic**

| Event | Impact | Comment |
|---|---|---|
| Base case profit before owner comp (Exhibit 8) | $67,784 | |
| Organic channel underperforms; paid mix drifts to 30% for the year | ($39,624) | 4,160 jobs × ($19.90 − $6.40) margin difference |
| 3 drivers churn mid-year, replaced with a 6-week gap each | ($3,443) | 3 × 6 weeks × 4 jobs/week × $19.90 lost margin |
| A Facebook policy change throttles group visibility for a quarter | ($5,000) | Forces a temporary shift toward paid ads to cover the gap |
| **Adverse case profit before owner comp** | **($19,717)** | Below the owner's market-rate salary bar entirely |

*Unlike the base case's comfortable margin, this business has very little cushion — a single ordinary shift in acquisition mix (not even a catastrophic event) is enough to erase the entire year's profit before the owner is paid anything. The adverse case here is really just "the base case's key assumption doesn't hold," which is the honest read of how fragile this model is.*

---

## Section 08 — Why simply becoming a driver might beat building the platform

**The analytical question:** Given the platform's thin margin at break-even scale, how does it compare to just being one of the drivers on someone else's app?

The founder doesn't have to build anything to test this market. GoShare, Curb-It, and LoadUp already run comparable marketplaces in most US metros, including Miami, and accept independent drivers today.

**Exhibit 11 — Own the platform vs. drive on an existing one**

| Dimension | Own the platform (20 drivers, disciplined mix) | Drive on an existing app, solo |
|---|---|---|
| Capital & time to first dollar | Months of app-building/vetting, <$30K spent | Days — sign up, pass a background check |
| Regulatory exposure | Miami-Dade hauler-permit question across a fleet (Section 04), marketplace liability insurance, LBT compliance for every recruited driver | Own LBT/permit question only, same as any driver on any platform |
| Net annual income to the owner/driver | $67,784 before owner comp; economic profit ~$2,784 | ~$26,000–66,000, part-time to full-time, at ~$131 net/job, 4–10 jobs/week |
| Downside if it doesn't work | Sunk app-build cost, recruited-driver relationships to unwind, signed liability policy | Stop logging into the app |
| **Effort-adjusted comparison** | Materially higher risk and complexity for a similar or only modestly better outcome at break-even scale | **Comparable income, a fraction of the risk** |

*At exactly the 20-driver break-even scale this memo finds, owning the platform doesn't clearly beat simply becoming a full-time driver on an app that already exists. The platform only pulls ahead once volume reaches the 35-driver range (Section 10) — and only if the acquisition-channel discipline in Section 07 actually holds.*

---

## Section 09 — Risk register

**The analytical question:** What can stall or break this, and what specifically prevents it?

**Exhibit 12 — Ranked exposures**

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Cold-start: need drivers to attract customers and customers to attract drivers, simultaneously | Certain, early | High | Recruit a handful of committed drivers first; soft-launch in one or two zip codes rather than county-wide; have the founder personally source the first customer leads. |
| Paid-channel share creeps up without being noticed | High | High | Track cost-per-booked-job by channel weekly (Exhibit 6); set a hard cap on paid-channel spend as a share of weekly bookings. |
| Miami-Dade hauler-permit applicability to individual gig drivers is unresolved | Medium | High | Get a specific written opinion from counsel before recruiting drivers at scale; build permit/LBT compliance into driver onboarding regardless. |
| Established competitor (GoShare, Curb-It, LoadUp, national franchises) already serving Miami | High | High | Compete hyper-locally on commission and responsiveness in a specific underserved pocket rather than head-on county-wide. |
| Facebook enforcement against automated data collection or spam-flagged outreach | Medium | Medium | Never automate group/Marketplace monitoring; keep outreach manual, low-volume, and personally written. |
| Driver churn to a bigger platform or full independence | Medium | Medium | Keep commission competitive; the real retention lever is consistent lead-flow a driver can't easily replicate solo. |
| On-job property damage, injury, or improper dumping by a driver | Medium | High | Per-job contingent liability insurance rider, driver insurance verification at onboarding, clear platform-liability limits in terms of service. |

---

## Section 10 — Recommendation

**The analytical question:** Given all of it, what should this founder actually do?

Four findings converge:

1. **Structure is mostly unfavorable** (Section 02) — free substitutes and established competitors already crowd this market.
2. **Paid acquisition, on either side of the marketplace, costs more than the model can absorb at a reasonable commission rate** (Sections 01, 05, 07) — this directly answers the founder's original question: no, regular advertisement does not work as a primary channel here.
3. **The one channel that works — manual, personal outreach into local Facebook groups and Marketplace — must stay manual to stay both cheap and legal** (Section 04); scraping it is a Meta ToS violation with real enforcement risk.
4. **At the scale this manual approach can realistically reach in year one (~20 drivers), the owner is barely doing better than simply driving for an existing competing app** (Section 08).

> **Recommended structure**
>
> **Build it as a slow, local, manually-fueled business — not an ads-driven growth story — and don't spend meaningfully on paid acquisition until organic channels have proven they can't keep up.** Start in one or two Miami-Dade zip codes with 3–5 hand-recruited drivers before expanding county-wide. Track cost-per-booked-job by channel from week one, and cap paid-channel volume at roughly 15% until commission economics or job value improve enough to justify more.
>
> Target **35 active drivers within 18–24 months**, at which point (Section 06/07, scaled) the model clears both a part-time ops hire and a genuine ~$40K/year of profit above the owner's own market-rate pay — the point where owning the platform is unambiguously better than driving for someone else's.

> **What would change this recommendation**
>
> If manual recruiting and organic lead-sourcing can't sustain growth past the first 10–15 drivers without leaning on paid channels, the honest move is to stop and become a driver on an existing competing app (Section 08) rather than keep funding a platform whose unit economics only work under a discipline that isn't holding. Conversely, finding a higher-value niche within junk removal — small commercial or light-construction debris jobs, which run well above the $220 residential average and face less free-substitute competition — would materially improve the commission-per-job math and could justify more paid-ad spend than this base case supports.

### Metrics to run it on

- **Cost per booked job, by channel** — tracked weekly, separately for manual/organic, bought leads, and paid ads. This is the single number that determines whether the model is working.
- **Paid-channel share of total bookings** — hard cap around 15% until commission or job value improves.
- **Active drivers doing ≥3 jobs/week** — the real utilization/retention signal, not total registered drivers.
- **Net margin per job** — target ≥$15; below that, growth in driver count stops translating into owner profit.
- **Driver-side CAC** — target ≤$50/driver; a drift toward paid recruitment marketing is the first sign the manual model is breaking down.

---

**ANALYTICAL BASIS** — Figures are directional estimates for a bootstrapped two-sided marketplace app matching independent haulers with residential junk/bulk-item removal customers in Miami-Dade County, built for structural analysis rather than as an audited forecast. Job pricing, lead-cost, and driver-acquisition figures are drawn from published industry ranges and will vary by neighborhood, job type, and season; Exhibit 9 exists because the acquisition-channel mix must be tracked and re-underwritten continuously, not assumed. The Miami-Dade hauler-permit and Local Business Tax Receipt discussion (Section 04) is summarized at a level suitable for planning judgment and is not legal advice; confirm current requirements and their applicability to individual gig drivers with counsel before recruiting at scale. The Meta/Facebook Terms of Service discussion is likewise a planning-level summary, not legal advice.

**FRAMEWORKS APPLIED** — Market funnel (TAM/SAM/SOM) with a recruiting-velocity capacity cap · Porter's Five Forces · Value chain and margin-pool analysis · Region-specific structural and regulatory analysis · Bottom-up unit economics with channel-level CAC decomposition · Two-variable sensitivity · Adverse-case scenario · Cross-business-model (platform-owner vs. driver) comparison · Risk register · Economic profit adjustment for owner labor.
