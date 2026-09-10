# The Board Meets Once a Month

**Artifact:** https://claude.ai/code/artifact/143dbcc7-d8b2-4dc3-89e5-fc717be04e20
**Notion:** https://app.notion.com/p/3d7ba21e32d48155a51add52cb9da989?pvs=204

An MBA-style teardown of a camera-and-license-plate-recognition startup selling parking compliance to gated HOA and condo communities in South Florida — and why the real ceiling on growth is a volunteer board's calendar, not capital, hardware, or demand.

**SUBJECT:** bootstrapped technical founder (<$50K), buys/integrates commodity LPR hardware + cloud recognition API, sells direct to HOA boards
**MARKET:** Miami-Dade / Broward gated & access-controlled communities, ~600-space sites
**BASE CASE:** 4-camera install, $1,350/mo subscription, scaling toward 15–20 communities over 1–3 years, 2 employees

---

## Section 00 — Executive summary

**The analytical question:** Should a bootstrapped technical founder build a camera-based parking-compliance product for South Florida HOAs, and how many communities does it take to be worth doing?

| KPI | Value | Note |
|---|---|---|
| Revenue / site | $16,200/yr | $1,350/mo, ~88% gross margin |
| Install payback | ~2 months | recurring margin repays install cost fast |
| Break-even (2 staff) | 9 sites | cash, before paying the owner anything |
| Owner at market pay | 15 sites | the real economic break-even |
| Economic profit @15 | ($9,100) | after charging owner's labor at $85K/yr |

> **Recommendation: Build it — but solo through the first 8–10 sites, and don't hire the second employee until the sales motion is proven repeatable.**
>
> The unit economics are genuinely good: an all-in $1,350/month bundle undercuts both the ~$27,000/year a community already pays a person to walk the lot twice a day, and the ~$10,000–12,000/year an enterprise LPR vendor charges for bare camera hardware with no HOA-specific workflow on top. At 88% gross margin per site with a two-month payback on install cost, this is a good product to sell.
>
> The catch isn't the product, the market, or the founder's capital. It's the buyer. A community's ~600 spaces and its chronic guest-parking problem are real and permanent, and Miami-Dade and Broward together hold hundreds of communities large enough to matter — demand is not the constraint. **The constraint is that a volunteer HOA board meets monthly, votes as a group, and moves at the pace of the slowest board member's schedule.** A sales cycle measured in months, not weeks, means the founder can plausibly close 20–24 sites in three years — almost exactly the number this memo finds is needed to make the business genuinely worth running.
>
> At 15 sites, the owner is earning roughly what a market-rate outside sales rep earns — no better. At 20, there's a real ~$60,000/year of profit above that. Below 9, two employees can't be justified at all. The recommendation is to run this as a solo operation until the pipeline is proven, then scale headcount only against signed contracts, not projected ones.

---

## Section 01 — Market definition and capacity

**The analytical question:** How large is the opportunity, and what actually limits how many communities this founder can sign?

South Florida's older housing stock is structurally exposed to this problem. Much of the region's condo and HOA inventory was built in the 1970s and '80s for one car per unit, and guest and visitor overflow has been a chronic, unresolved friction point ever since — this demand is not going away and does not need to be created. The question is entirely about throughput.

**Exhibit 1 — Market funnel, TAM to SOM**

| Layer | Definition | Communities | ARR if captured |
|---|---|---|---|
| TAM | Registered community associations, statewide FL | ~46,000 | ~$746M |
| SAM — region | Miami-Dade + Broward registered condo/HOA associations | ~6,000–8,000 | — |
| SAM — segment | Gated / access-controlled, 300+ units, chronic guest-parking pressure | ~600–900 | ~$10–15M |
| **SOM — 3-yr** | **Capacity-bound: board sales-cycle length × one founder + one install tech** | **20–24** | **~$340–390K** |

*TAM value is illustrative only — most of Florida's 46,000 associations are too small, ungated, or without a guest-parking problem to be real prospects. The collapse from ~750 addressable communities to 20–24 signed is not a demand problem. It is a sales-velocity problem.*

The capacity math that actually governs the business:

- **HOA/condo boards approve vendor contracts as a group**, typically at a monthly meeting, sometimes requiring a budget-line or reserve-fund sign-off. A realistic first-contact-to-signed-contract cycle runs **10–16 weeks** even for an enthusiastic board.
- One founder, doing sales alone, can realistically run 6–10 concurrent board conversations at a time in the early going. That supports roughly **8–12 closes a year** once the pitch and references exist.
- One install technician can complete **~2 installs a month** (2 days on-site plus travel) — install capacity is not the binding constraint until well past 20 sites.
- Bootstrapped capital (<$50K) can float roughly **~$2,100 of net install cost per new site** (Section 05) — enough for 15–20 sequential installs before revenue starts fully self-funding growth, so capital is a soft constraint, not the real ceiling.

Sales-cycle velocity, not capital or hardware, is the number that sets how fast this can scale — and it's the number this memo returns to in Sections 07 and 10.

---

## Section 02 — Industry structure (Five Forces)

**The analytical question:** What return does a participant in this niche earn, structurally, before any firm-specific advantage?

**Exhibit 2 — Force assessment**

| Force | Rating | Evidence |
|---|---|---|
| Supplier power (camera + cloud LPR API vendors) | Moderate | Camera-agnostic cloud LPR (Rekor Scout-style, roughly $12–15/camera/month) and generic ONVIF IP cameras are commodities with several interchangeable vendors. No lock-in for the startup — but it is dependent on a small number of viable cloud-recognition providers for the core read accuracy the whole product depends on. |
| Buyer power (HOA / condo boards) | High, early — falls over time | Volunteer boards are price-sensitive, risk-averse, and slow, and can simply decline or defer any discretionary spend. But once a system is installed and the board has retired its paper guest log, switching cost is real — a signed community is a defensible, sticky account. |
| Threat of new entry | Moderate–high | The startup itself is a "buy/integrate" reseller of commodity parts — anyone with basic dev skills can replicate the packaging. Enterprise players (Flock Safety, Genetec) or a regional camera-installation company could bundle a comparable workflow. Low technical barrier; the defense has to be relationships and speed, not proprietary technology. |
| Substitutes | High | The status quo — a person walking the lot twice a day — already exists and works well enough that most boards have not acted. DIY community-management software (e.g., Parking Boss–style tools) offers a cheaper, camera-free partial substitute. And simply tolerating the problem, which most communities already do, is always an option. |
| Rivalry | Low, for now | No vendor found is positioned specifically at mid-size South Florida HOA guest-parking compliance. Flock and Genetec sell security/crime products to HOAs, not guest-parking workflow; DIY software sells workflow without hardware. The niche is currently uncontested — which is also exactly why entry threat above is rated the way it is. |

*Structurally mixed: two forces (suppliers, and buyers once retained) favor the startup; entrants and substitutes do not. The niche is open today because no one has bundled hardware and HOA-specific workflow at this price point — not because the idea is hard to copy.*

---

## Section 03 — Value chain and margin pool

**The analytical question:** Of what a community pays each month, who takes what — and who carries the risk?

**Exhibit 3 — Value extracted per site, per month ($1,350 subscription)**

| Participant | Take | Risk carried | Quality |
|---|---|---|---|
| Cloud LPR / recognition API vendor | $60 | None. Paid per camera per month regardless of read accuracy or renewal. | Excellent |
| Cloud storage & cellular backup providers | $100 | None. Metered, paid monthly. | Excellent |
| Camera / hardware manufacturers (amortized from one-time install) | ~$0 recurring | None after sale — warranty only. | Excellent |
| **The startup** | **$1,190** | **All of it.** Fronts the $4,600 install cost, carries the customer relationship, false-positive/negative liability, and churn risk. | Concentrated, but high-margin |

*Unlike a typical resale or labor-arbitrage business, the startup keeps the large majority of the transaction (~88%) because the commodity inputs it resells are genuinely cheap. The risk it carries is concentrated but small in dollar terms per site — the real risk (Section 09) is losing the account, not losing money on any single month.*

This is the opposite margin pattern from a typical flip or resale business: here, the party taking the transaction risk (the startup) also keeps most of the money, because the inputs — cloud API calls, storage, commodity cameras — are structurally cheap relative to what a board will pay to solve a chronic, visible problem.

---

## Section 04 — Miami-Dade / Broward-specific structure

**The analytical question:** What does this specific region and its regulatory environment do to the model that a generic parking-tech pitch would miss?

**Exhibit 4 — Regional factors and their transmission**

| Factor | Effect | Mechanism |
|---|---|---|
| FL towing/immobilization statute (F.S. 715.07) | Value-add | Florida requires specific notice and signage before a vehicle can be towed from private property. Timestamped, photographic plate evidence directly strengthens the HOA's documentation for a towing decision — a genuine feature, not just detection, and a strong point in the sales pitch. |
| Condo/HOA governance (Ch. 718 / 720, F.S.) | Sales-cycle driver | Vendor contracts typically require board approval as an agenda item, sometimes with a competing-quote requirement if funded from reserves rather than the operating budget. This is the direct statutory root of the 10–16 week sales cycle in Section 01. |
| No FL private-sector LPR privacy statute — but resident sentiment is real | Friction risk | Florida's LPR-specific retention rules target law-enforcement use, not HOAs, so there's no compliance requirement here. But "surveillance" objections from residents at open board meetings are a documented friction point in other markets' HOA camera rollouts and can stall or reverse a signed deal — mitigated by a written data-retention/no-resale policy presented proactively. |
| 1970s–80s housing stock, one space per unit | Sustains demand | Much of South Florida's condo/HOA inventory predates modern parking ratios, so guest and unauthorized-vehicle overflow is structural, not seasonal noise — the underlying problem this product solves isn't going away. |
| Snowbird seasonality | Timing lever | Guest-parking pressure peaks roughly November–April as seasonal residents' visitors arrive. Boards feel the pain live in-season — the best time to pitch is during or just after high season, not in the slow summer months. |
| Hurricane season / grid outages | Cost + timing driver | Outdoor housings and cellular backup power (already priced into the install cost) are necessary, not optional. Separately, communities deprioritize discretionary vendor spend for months after a direct storm hit — a real seasonal drag on the sales pipeline, distinct from the hardware cost itself. |

---

## Section 05 — Unit economics

**The analytical question:** What does one signed community actually cost and earn, and what does it beat?

### The advantage, isolated

The founder brings no proprietary technology — every component is bought, not built. The advantage is entirely in packaging cheap commodity parts into something a board can actually approve, at a price between the two existing alternatives.

**Exhibit 5 — Status quo vs. enterprise LPR vs. this startup — one 600-space community**

| Capability | Human patrol (status quo) | Enterprise LPR (e.g. Flock-style lease) | This startup |
|---|---|---|---|
| Coverage | 2 snapshots/day | 24/7 continuous | 24/7 continuous |
| Catches overstays between checks | No | Yes, if configured | Yes — built for it |
| Guest / authorized-list workflow | Manual spreadsheet or paper log | Not included | Included, purpose-built |
| Photographic evidence for towing | Rare, informal | Yes | Yes |
| Monthly cost, 4 cameras/gates | $2,250 | $833–1,000 (camera lease only) | $1,350 (all-in) |
| **Annual cost** | **$27,000** | **~$10,000–12,000 (+ separate workflow software)** | **$16,200 (+ $2,500 one-time install)** |

*Human patrol time-and-rate assumption: 1.5 hours per check (partial-lot + guest-zone audit, not a full 600-space census), twice daily, at a $25/hr contractor bill rate — a directional estimate, not a quoted figure. The startup prices between the two alternatives and is the only one that is workflow-complete out of the box.*

**Exhibit 6 — Per-site P&L, install and steady-state month**

| Line | Amount | Note |
|---|---|---|
| One-time install fee charged to HOA | $2,500 | Billed at signing, before install begins |
| Cameras — 4× outdoor ONVIF PoE, LPR-capable | $880 | Entry, exit, 2× guest zones |
| Mounting, housings, PoE switch, edge box | $1,300 | |
| Cellular/LTE backup modem | $250 | Grid-outage resilience, hurricane season |
| Electrical/conduit subcontractor | $1,200 | |
| Install labor + admin (own tech) | $950 | ~2 days on site |
| **Total install cost** | **$4,580** | |
| **Net install cash cost (one-time)** | **($2,080)** | Recovered in ~2 months of recurring margin |
| Recurring subscription | $1,350/mo | |
| Cloud LPR SaaS — 4 cameras | $60 | |
| Storage — 4 cameras | $32 | |
| Cellular data plan | $45 | |
| Monitoring/alerting infra allocation | $20 | |
| **Recurring variable cost** | **$157/mo** | |
| **Recurring gross margin** | **$1,193/mo (88%)** | Before any staff or overhead allocation |

*Every dollar of the recurring cost stack is a metered cloud service — there is essentially no marginal labor cost to serving an already-installed site, which is the structural difference from a patrol-labor competitor (Section 08).*

---

## Section 06 — Annual operating model

**The analytical question:** What does a real portfolio of communities earn once two employees, overhead, and the owner's own market wage are charged?

**Exhibit 7 — Annual P&L, 15 communities (a year of growth from 11)**

| Line | Annual | Per site |
|---|---|---|
| Recurring subscription revenue | $243,000 | $16,200 |
| Install fees — 4 new sites this year | $10,000 | $2,500 |
| **Total revenue** | **$253,000** | — |
| Cloud LPR, storage, cellular (recurring) | ($28,800) | ($1,920) |
| Hardware & install cost, 4 new sites | ($18,400) | ($4,600) |
| **Gross margin** | **$205,800** | — |
| Field install/service technician (loaded) | ($58,000) | — |
| Customer success / ops (loaded) | ($52,000) | — |
| Software/infra fixed, insurance, vehicle | ($19,900) | — |
| **Business overhead** | **($129,900)** | — |
| **Profit before owner compensation** | **$75,900** | — |
| Owner compensation at market (outside B2B security/proptech sales rep, FL) | ($85,000) | — |
| **Economic profit** | **($9,100)** | — |

*2 employees plus software/insurance/vehicle overhead run about $130,000/year fixed. At 15 sites, cash in the owner's pocket ($75,900) is close to what a market-rate sales role would pay — meaning 15 is the point where running this business stops being clearly better than taking a job, not the point where it becomes clearly good.*

**Profit before owner compensation is the number that matters for the plain question "does this pay for 2 employees, software, and something for me."** At 15 sites, the answer is yes — $75,900 cash to the owner after both salaries and every software/insurance line. Charging that same owner's labor as if it were a market-rate hire turns it slightly negative. Those two numbers are both true, and both matter: the owner is being paid close to what the job is worth, no more.

---

## Section 07 — Sensitivity analysis

**The analytical question:** Which matters more to the outcome — how many communities are signed, or what they're charged?

**Exhibit 8 — Cash profit before owner compensation, by community count and price**

| Communities | $1,100/mo | $1,250/mo | $1,350/mo (base) | $1,500/mo |
|---|---|---|---|---|
| 10 | ($17,100) | $900 | $12,900 | $30,900 |
| **15 (base)** | $39,300 | $66,300 | **$84,300** | $111,300 |
| 20 | $95,700 | $131,700 | $155,700 | $191,700 |
| 25 | $152,100 | $197,100 | $227,100 | $272,100 |

*Steady-state view: no new installs in the modeled year, $129,900 fixed overhead held constant. Note the grid is far more sensitive to rows (community count) than columns (price) — because gross margin is already 85–90% at every price point tested, the $130K fixed cost of two employees is what has to be cleared, not the price umbrella. Volume, not pricing power, is the lever that matters here.*

### The scenario the grid does not show

Exhibit 8 varies price and count. It holds churn, install overruns, and vendor pricing fixed — a realistic adverse year at the 15-site base case:

**Exhibit 9 — Adverse case, nothing exotic**

| Event | Impact | Comment |
|---|---|---|
| Base case profit (Exhibit 7) | $75,900 | |
| 2 signed communities delay install a full quarter | ($7,140) | Board turnover after an election re-opens the vote |
| 1 community churns after 6 months | ($7,140) | New management company cancels the contract |
| Hardware failure, 2 sites, unplanned truck-roll | ($2,400) | Outside warranty window |
| Cloud LPR vendor raises per-camera price 25% | ($1,350) | Small vendors do this; 6 months' impact |
| One install runs over budget | ($1,800) | Unexpected electrical trenching, older building |
| **Adverse case profit** | **$56,070** | Still solidly positive |

*Unlike a concentrated bet-per-deal business, 15 independent, small monthly contracts diversify ordinary bad luck well — no single event here comes close to erasing the year, because no single site is worth enough to matter that much on its own. The real tail risk is pricing power, not operations: if a well-funded competitor forces price down toward $900/mo, cash profit before owner comp at 15 sites falls to roughly $3,300 — a near-wipeout, and the one adverse scenario genuinely worth watching for.*

---

## Section 08 — Why this beats the obvious alternative business

**The analytical question:** Why build a camera SaaS product instead of simply running a cheaper patrol-labor company undercutting the incumbent checkers?

A founder with the same market insight could instead start a patrol-labor company — hire checkers, undercut existing providers on the $25/hr bill rate, and sell the identical value proposition of "we make sure your guest parking is legal." It's a real alternative business, and it fails for a structural reason that has nothing to do with effort or sales skill.

**Exhibit 10 — Camera SaaS bundle vs. a patrol-labor company, same market**

| Dimension | Camera SaaS (this startup) | Patrol-labor company |
|---|---|---|
| Revenue per site / mo | $1,350 | $2,250 |
| Marginal cost to add one site | ~$157/mo + $4,580 one-time | ~$1,700–1,800/mo, recurring, forever |
| Gross margin per site | ~88% | ~20–30% |
| Cost to grow 15→20 sites | 5 installs (one-time) + ~$800/mo recurring | ~5 sites' worth of new guard-hours hired continuously, ~$8,800/mo new recurring labor cost |
| Coverage quality | 24/7 continuous, photographic evidence | 2 snapshots/day, rarely photographed |
| **Gross margin dollars at 20 sites/yr** | **~$285,600** | **~$135,000** |

*The patrol company's cost scales almost linearly with revenue — every new site requires roughly proportional new labor-hours. It never escapes that ceiling, which is why at the same 20-site scale it barely clears two salaries before any owner profit, while the camera model clears both salaries with real profit left over.*

**Exhibit 11 — Gross margin at 20 sites, by model:** Camera SaaS (this startup) 88% vs. patrol-labor company 25%.

---

## Section 09 — Risk register

**The analytical question:** What can stall or break this, and what specifically prevents it?

**Exhibit 12 — Ranked exposures**

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Board sales-cycle stalls or declines | High | High | Offer a one-month pilot at a friendly reference community; build 3–5 case studies fast; pitch during peak season (Section 04) when the board feels the problem live. |
| Enterprise competitor (Flock, Genetec, a regional installer) bundles a comparable HOA workflow | Medium | High | Move fast on reference sites; lock in multi-year contracts; compete on the HOA-specific workflow layer, not the camera itself, since that's the one thing not trivially copied overnight. |
| False positive/negative plate read causes a wrongful-tow dispute or a missed violator | Medium | High | Startup supplies data only — the HOA/management makes the actual tow decision; keep the full photo/timestamp evidence trail; carry E&O/cyber insurance. |
| Resident privacy/surveillance objection at a board meeting | Medium | Medium | Written data-retention and no-resale policy presented proactively, before a resident raises it reactively. |
| Founder is the only salesperson | High, at current stage | High | Document a repeatable sales playbook from site 1; don't hire a dedicated salesperson until the motion is proven — hire ops/install support first (Section 10). |
| Named storm damages hardware or stalls the pipeline | Medium, seasonal | Medium | Cellular backup and weatherproof housings already priced into install cost; replacement-hardware SLA in the contract; expect a slow Q4 after a direct hit. |
| Bootstrapped cash float runs thin mid-install-run | Medium | Medium | Collect the install fee plus first month upfront before starting install; stagger installs against confirmed cash on hand, not projected signings. |

---

## Section 10 — Recommendation

**The analytical question:** Given all of it, what should this founder actually do, and on what timeline?

Four findings converge:

1. **The product genuinely beats both alternatives on cost and coverage** (Section 05) — cheaper than the human patrol, more complete than the enterprise LPR lease.
2. **Demand is not the constraint** (Section 01) — Miami-Dade and Broward hold hundreds of large enough gated communities against a need for only 20–24.
3. **The sales cycle, set by how a volunteer board governs itself, is the real ceiling** (Sections 01, 04, 07) — not capital, not install capacity, not hardware cost.
4. **The cost structure, not the price charged, is what determines whether two employees and a real owner profit are affordable** (Sections 06–08) — and it structurally beats the obvious labor-based alternative business at any relevant scale.

> **Recommended structure and sequence**
>
> **Year 1: founder sells and installs solo.** Close and install the first 8–10 reference communities personally — no hires yet. This proves the real sales-cycle length, refines the pitch, and stays comfortably inside the <$50K bootstrapped budget (roughly $2,100 net cash per install, or ~$17,000–21,000 total for 8–10 sites).
>
> **Hire 1 (field install/service tech) once the pipeline reliably supports 2+ new installs a month** — freeing the founder to focus entirely on sales rather than truck-rolls.
>
> **Hire 2 (customer success/ops) around 12–15 signed sites**, once support and board-relationship volume justifies dedicated headcount. Target **20–24 communities within the three-year horizon** for a genuinely profitable outcome (~$60K–$150K/yr of owner profit above both salaries); treat 15 as the floor at which the business is merely as good as taking a job, not the goal.

> **What would change this recommendation**
>
> If the board sales-cycle stays above ~4 months per deal even once references exist, 20+ sites in three years is not realistic, and the right move is to accept a smaller, employee-free lifestyle business at 9–12 sites rather than force a hire the pipeline can't support. If Flock, Genetec, or a regional installer launches an HOA-specific guest-parking workflow product, the niche's low-rivalry window (Section 02) closes fast — reassess pricing power before committing to the second hire.

### Metrics to run it on

- **Board sales-cycle length** — days from first pitch to signed contract. Target under 90 days by year 2; this is the single number that determines whether the 20-site case is achievable.
- **Net new sites per month** — the direct throughput number against the Section 01 capacity math.
- **Gross margin per site** — target ≥85%; a drop here signals cloud-vendor price creep (Exhibit 9) before it shows up anywhere else.
- **Net install cash cost per site** — target ≤$2,500, to protect the bootstrapped capital base.
- **Annual churn rate** — target <10%; a lost site costs a full install-cost payback period, not just a month of margin.

---

**ANALYTICAL BASIS** — Figures are directional estimates for a bootstrapped camera-and-LPR parking-compliance startup selling to gated HOA/condo communities of roughly 600 spaces in Miami-Dade and Broward County, built for structural analysis rather than as an audited forecast. Hardware, install, and vendor-pricing figures are drawn from published ranges for camera-agnostic cloud LPR and commodity ONVIF hardware and will vary by site conditions and vendor selected; Exhibits 8 and 9 exist because these inputs must be re-underwritten per deal before committing install capital. Regulatory references — Florida's towing/notice statute (F.S. 715.07) and condo/HOA governance statutes (Ch. 718/720, F.S.) — are summarized at a level suitable for planning judgment and are not legal advice; confirm current requirements with counsel before relying on them.

**FRAMEWORKS APPLIED** — Market funnel (TAM/SAM/SOM) with a sales-velocity capacity cap · Porter's Five Forces · Value chain and margin-pool analysis · Region-specific structural analysis · Bottom-up unit economics with isolated advantage decomposition · Two-variable sensitivity · Adverse-case scenario · Cross-business-model structural comparison · Risk register · Economic profit adjustment for owner labor.
