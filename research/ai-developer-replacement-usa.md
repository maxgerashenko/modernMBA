# The Cluster Is Not the Developer

**Artifact:** https://claude.ai/artifact/W1kcyA5nYTzimgDhrULt36
**Notion:** https://app.notion.com/p/413ba21e32d4815980fdd79459e1d203?pvs=204

An MBA-style teardown of a "virtual developer" business: own a GPU cluster, run a frontier-class coding model on it, and sell each agent seat to US companies at a price set from the hardware's amortized cost plus a 75% margin, pitched as a replacement for a salaried engineer. The memo states the hypotheses behind that idea first, tests each one against current numbers, and corrects the source conversation where it was wrong.

**SUBJECT:** an operator selling full-time AI coding-agent seats to US employers, built either on an owned 16× H100 cluster (the source formula) or on a frontier model's API (the corrected base case)
**MARKET:** US software developers and QA testers, ~1.9M people (BLS, 2025)
**BASE CASE:** API-based agent seat at $36,000/yr, one agent working a 2,080-hour year, 250 seats at steady state
**SOURCE:** a long chat with another AI assistant that built the formula `((1.28 TB / 80 GB × $40K) / (4Y × 8,760H)) × 2,080H × 2X + 75%M = $132,968`. Its numbers are treated as claims to test, not as facts.

---

## Preface — Hypotheses, stated before the verdict

**The analytical question:** What would have to be true for "replace a US developer with a GPU cluster running a frontier model, priced cost-plus" to be a good business — and is each of those things true?

The source chat moved from hardware prices to a pricing formula to a $387B "market" without stopping to name its assumptions. They are named here, each with the test this memo runs and the result. Everything after this table is the evidence.

**Exhibit A — Hypotheses, tests, and results**

| # | Hypothesis (from the source chat) | How it is tested | Result |
|---|---|---|---|
| H1 | A frontier-class coding agent can work a full 2,080-hour year for well under a developer's loaded cost. | Price one agent's token use on Claude Opus 5.5 list prices ($4 in / $20 out / $0.20 cached per million tokens); price a batched self-hosted cluster. | **Supported, strongly.** About $18,500/yr on the API, $2,000–9,000/yr self-hosted at full batching, against ~$177,000 for a median-wage developer. Compute is not the obstacle. |
| H2 | The formula `(cluster cost ÷ lifetime hours) × 2,080 × 2X × 1.75` is a valid cost-plus price for one agent seat. | Rebuild the real annual cost of the cluster the formula describes, and compare. | **Rejected.** It contains two errors that happen to offset. It bills only 2,080 of 8,760 hours (23.7% of depreciation) and leaves out power, space and staff, so a *dedicated* 2X cluster costs ~$560,000/yr against a $132,968 price. But one agent does not need a dedicated cluster: a batched cluster serves ~30 agents, so the true cost per seat is ~$19,000. The price is right only by accident, and has no link to cost. |
| H3 | Owning the hardware beats renting it or buying API tokens. | Owned cost per GPU-hour vs. the October 2026 rental market; what model the hardware can actually run. | **Rejected for this operator.** An owned H100 costs ~$2.00/GPU-hr at 100% utilization vs. a $3.49 rental median and a $1.70 floor. More important, Claude Opus cannot be self-hosted at all — its weights are not sold — so owned hardware runs a weaker open-weights model. |
| H4 | One agent seat replaces one developer, so the buyer will pay up to a developer's salary. | Compare what a buyer gains (share of a developer's work the agent completes) with what it costs (price plus review time). | **Not supported.** Agents complete tasks, not jobs, and need review. At a $36,000 price the buyer only comes out ahead if the agent does at least ~33% of a median developer's output. The price ceiling is set by that share, not by the salary. |
| H5 | The market is $300B+ (the chat's $387B, or 2.9M "agent equivalents"). | Rebuild payroll from BLS; separate the payroll pool from the revenue a vendor can capture. | **Partly supported.** US developer + QA payroll is real and large: ~$330–350B loaded. But that is a ceiling on displaced spending, not a market. The revenue pool vendors can capture is ~$10–30B. The 2.9M-agent figure is circular (salary ÷ price × headcount just restates payroll). |
| H6 | A 75% margin is achievable and defensible. | Check the arithmetic; check who sets the input price. | **Rejected as stated.** A 75% *markup* is a 42.9% gross margin, and the chat mixed the two. The model lab sets the main input price and also sells competing seats, so a reseller's margin is held down by its own supplier. |

> **How the hypotheses resolve:** H1 is true and is the reason the idea feels inevitable. H2, H3 and H6 are why this particular business — owning GPUs and pricing off their cost — does not work. H4 and H5 are why the price can't be set off a developer's salary either. What survives is a narrower, API-based agent-operations service that has to earn its price by how much finished, reviewed work each seat delivers.

---

## Section 00 — Executive summary

**The analytical question:** Should an operator buy a GPU cluster and sell "virtual developer" seats to US companies priced at amortized hardware cost plus 75% — and if not, what version of the idea works?

| KPI | Value | Note |
|---|---|---|
| Source formula price | $132,968 / seat-yr | 16× H100 at $40K, 4-yr life, 2,080 h, 2X, +75% |
| True cost, dedicated 2X cluster | ~$560,000 / yr | the formula recovers ~14% of it |
| True cost, one agent-year on Opus 5.5 API | ~$18,500 | 2,080 h at ~$8.90/agent-hour |
| US dev + QA payroll (ceiling, not market) | ~$330–350B | 1.905M people, BLS May 2025, ×1.3 loaded |
| Vendor revenue pool (SAM) | ~$10–30B | share of work automatable × price capture |
| Corrected base case | $1.41M econ. profit @ 250 seats | breakeven ~164 seats; API-based, $36K/seat |

> **Recommendation: Do not buy the cluster, and do not price off a salary. The replacement math is real, but the margin goes to the model lab and to the buyer, not to whoever owns the GPUs. The only version that clears is an API-based agent-operations service priced on delivered work.**
>
> The core intuition in the source chat is correct: a frontier coding agent is now cheap to run. Working a full 2,080-hour year at a realistic token load, an Opus 5.5 agent costs about $18,500 at list price. A median US software developer costs about $177,000 a year to employ. That gap is why this idea feels like a $300B opportunity.
>
> The formula built to capture that gap does not hold up. It bills the cluster for 2,080 hours but pays for it for 8,760, and leaves out power, space and staff. A cluster really dedicated to one seat, with the formula's 2X redundancy, costs about $560,000 a year to own and run, and the formula charges $132,968 for it. The formula only lands on a sane number because a single agent never needed its own 16-GPU cluster in the first place: batched, one cluster serves about 30 agents. Once that is understood, the cluster stops being an asset and becomes a cost line — one that rents for less than it costs to own, and that can't run Claude Opus at all, since Opus is only available as a service.
>
> The demand side has the same problem. An agent seat doesn't replace a developer; it replaces some share of a developer's tasks and needs someone to review its work. At a $36,000 price the buyer only saves money if the agent does about a third of a median developer's output. That share, not the salary, sets the ceiling price. The business that survives is a managed agent-seat service on the API, at roughly $36,000 per seat-year with ~45% gross margin. It needs ~164 seats to pay its team and founder, and an ordinary bad year (a competitor price cut plus token overruns) erases its profit.

---

## Section 01 — Market definition and capacity

**The analytical question:** How large is the developer-replacement opportunity in the US, and what actually caps how much of it one operator can take?

**Exhibit 1 — Market funnel, payroll ceiling to SOM**

| Layer | Definition | Value |
|---|---|---|
| Payroll pool (ceiling) | US software developers (1,717,800) + QA analysts/testers (187,600), BLS 2025; wage bill ~$253B, ×1.3 for employer cost | ~$330–350B / yr |
| Automatable work | Share of developer hours on tasks an agent can complete with review — **assumption: 20–30% by 2028** | ~$66–105B of labor value |
| SAM — vendor revenue pool | Vendors capture ~15–30% of displaced labor value as price (the rest is buyer savings) — **assumption** | ~$10–30B / yr |
| SAM — this segment | Mid-market US employers buying managed agent seats rather than self-serve tools (~20% of the pool) — **assumption** | ~$2–6B / yr |
| **SOM — 3 yr** | **250 seats × $36,000 — bound by distribution and trust, not compute or demand** | **$9.0M / yr** |

*Cross-check on the SAM: paid AI coding tools are already a multi-billion-dollar category — Cursor alone passed $2B in annualized revenue in March 2026 (Bloomberg, TechCrunch). The source chat's $387B figure is the payroll pool, not a market; its $51.45B and $1.67T figures are payroll pools for subsets and for other industries, with no capability test applied.*

The capacity math that actually governs this business:

- **Compute is not the cap.** At list prices, a whole year of one agent's tokens costs about a tenth of the developer it supports. Any operator can buy as many tokens as it can sell.
- **The cap is how much work a seat finishes that a customer accepts.** Every assumption in the funnel above (20–30% of work automatable, 15–30% price capture) is a statement about that. Neither is measured yet for this operator, and Exhibit 9 shows the business is very sensitive to both.
- **Distribution is the second cap.** Each seat is sold to an engineering manager who has to trust the agent with a codebase, set up review, and justify it against tools the team already has (Claude Code, Cursor, GitHub Copilot). That is a sales cycle, not a sign-up.

---

## Section 02 — Industry structure (Five Forces)

**The analytical question:** What return does an agent-seat operator earn, structurally, before any firm-specific advantage?

**Exhibit 2 — Force assessment**

| Force | Rating | Evidence |
|---|---|---|
| Supplier power (model labs, GPU vendors, clouds) | Very high | Frontier coding models come from a handful of labs, and Claude Opus is only available as a service (Anthropic API, AWS, Google Cloud, Microsoft Foundry). The lab sets the input price — Opus 5.5 lists at $4 / $20 per million tokens, 20% below Opus 5 — and can change it at any time. |
| Buyer power (engineering managers, CTOs) | High | Buyers can measure output directly (merged pull requests, tickets closed), can cancel monthly, and already pay for agent tools at $20–200 per developer per month. |
| Threat of new entry | Very high | The same API is open to everyone. A competing agent-seat service needs no capital, only an orchestration layer that can be built in weeks. |
| Substitutes | Very high | Claude Code, Cursor, GitHub Copilot and similar tools used by the buyer's own staff; offshore contractors; and simply hiring. Each is cheaper to try than a new vendor. |
| Rivalry | Very high | Model labs sell agents directly, so the supplier is also a competitor. Well-funded coding-agent companies compete on price and capability every quarter. |

*Five of five forces unfavorable. The one structural tailwind — compute keeps getting cheaper — helps every competitor equally and pushes cost-plus prices down over time.*

---

## Section 03 — Value chain and margin pool

**The analytical question:** Of what a buyer pays for one agent seat, who takes what — and who carries the risk?

**Exhibit 3 — Value extracted per seat-year, $36,000 price**

| Participant | Take | Risk carried |
|---|---|---|
| Model lab (Opus 5.5 tokens, 2,080 h × ~$8.90) | $18,470 | None. Billed per token whether or not the code is accepted. |
| Cloud sandbox, CI runners, tooling | $1,200 | None. Metered. |
| **The operator** | **$16,330** | **Token overruns on a flat price, uptime, onboarding each codebase, and the reputational and contractual risk when an agent ships a bad change.** |
| Buyer — value of work done (agent does 30% of a median developer's output) | $53,000 of labor value | Pays the $36,000 price plus ~$21,000 of senior review time (4 h/week). Carries code-quality and security risk in its own systems. |

*At 30% substitution the buyer is about $4,000 a year worse off than doing nothing. The buyer only comes out ahead above ~33%. The operator keeps 45% of the price, but every dollar of it depends on the buyer's math staying positive.*

> **Where the 75% margin went:** the source chat priced the seat at cost × 1.75 and called the extra "a 75% margin." That is a 75% markup, which is a 42.9% gross margin (0.75 ÷ 1.75). The chat then used both definitions on the same $51.45B: once as $22.05B of margin with $29.40B of compute, and once as $38.59B of margin with $12.86B of compute. Later it labeled a $300B pool as 43% compute and 57% margin, which is the split reversed. The correct split of any price at a 75% markup is 57% cost, 43% margin.

---

## Section 04 — Domain-specific structural factors

**The analytical question:** What does the AI-model and US-employment landscape do to this model that a generic SaaS plan would miss?

**Exhibit 4 — Structural factors and their transmission**

| Factor | Effect | Mechanism |
|---|---|---|
| Closed model weights | Decisive against the hardware plan | Claude Opus is sold only as a service. "Running Opus 5.5 at 4-bit on Mac Studios or DGX Sparks," as the source chat suggested, is not possible. Owned hardware can only run open-weights models, which have generally trailed the frontier on long agentic coding work. |
| Model size and memory are not public | The 1.28 TB sizing is a guess | Anthropic does not publish parameter counts or memory footprints. The chat's "~600 GB unquantized," "350–400 GB at 4-bit," and "1.2 TB with context" are estimates for open models of a similar class, stated as fact. |
| Token prices fall each model generation | Cost-plus prices ratchet down | Opus 5.5 lists 20% below Opus 5 for the same tier. A price set as cost × 1.75 has to fall with it; a price set on delivered work does not. |
| Hardware economic life is 2–4 years, not 5 | Accelerates write-downs | Hyperscalers depreciate GPUs over 5–6 years for accounting, but NVIDIA now ships a new architecture roughly yearly. The chat's own 2-year case moves the formula price from $132,968 to $265,936. |
| Batching | One cluster serves many agents | Inference servers run many conversations at once. A 16× H100 cluster with ~280 GB left after model weights holds roughly 30–40 long-context agent sessions. Pricing one seat as if it owned the cluster is the formula's largest error. |
| Layoffs and WARN Act | Slows "replacement" sales | Replacing staff at scale triggers 60-day notice duties for employers with 100+ workers, plus internal politics. Buyers more often redirect hiring budgets than fire people, which lengthens the sale. |
| Copyright of AI-generated code | Contract issue for buyers | The US Copyright Office's position is that protection requires human authorship. Buyers will want IP warranties and indemnities that an operator must stand behind. |

---

## Section 05 — Unit economics

**The analytical question:** What does one agent seat really cost to run, and what does the operator's choice of how to run it change?

### The advantage, isolated

**Exhibit 5 — Annual cost of one agent seat, by how it is run**

| Option | Annual cost per seat | Note |
|---|---|---|
| Source formula, as written (no margin) | $75,982 | Bills 2,080 of 8,760 hours of a 4-yr, $640K cluster, ×2; no power, space or staff |
| **Dedicated 2X cluster, honestly costed** | **~$560,000** | 2 × ($160K depreciation + ~$23K power + ~$37K colocation + ~$60K ops) |
| Owned cluster, batched (~30 agents per cluster), 2X | ~$18,700 | Same hardware, shared; runs an open-weights model, not Opus |
| **Opus 5.5 API, one agent working 2,080 h** | **~$18,500** | ~120 turns/h, ~100K-token context 95% cached, ~1.5K output tokens per turn |
| Median US developer, loaded | ~$177,000 | BLS median wage $135,980 × 1.3 |

*Per GPU-hour, the owned cluster costs ~$2.00 at 100% utilization and ~$4.00 at 50%, against an October 2026 rental median of $3.49 and a floor of $1.70. Owning only wins at very high utilization, and even then it buys a weaker model. The operator's advantage, if it has one, is in the orchestration and review workflow, not in the hardware.*

**Exhibit 6 — Per-seat P&L, annual (API-based base case)**

| Line | Amount | Note |
|---|---|---|
| Seat price | $36,000 | $3,000/month; ~20% of a median developer's loaded cost |
| Opus 5.5 tokens | ($18,470) | $8.88/agent-hour × 2,080 h |
| Sandbox, CI, tooling | ($1,200) | |
| **Gross margin / seat** | **$16,330** | **45.4%** |

*The token estimate is the line most likely to be wrong. Light agentic use runs ~$3–4/hour; heavy use with large uncached context or fast mode ($8 / $40 per million tokens) runs $15–25/hour. Exhibit 8 shows the effect.*

---

## Section 06 — Annual operating model

**The analytical question:** How many seats does it take to cover a real team and pay the founder a market wage?

**Exhibit 7 — Annual P&L at 250 seats (steady state, year 3)**

| Line | Annual | Per seat |
|---|---|---|
| Revenue — 250 seats × $36,000 | $9,000,000 | $36,000 |
| Model tokens | ($4,617,500) | ($18,470) |
| Sandbox, CI, tooling | ($300,000) | ($1,200) |
| **Gross margin** | **$4,082,500** | **$16,330** |
| Engineering & on-call (4 × $230K loaded) | ($920,000) | — |
| Sales & customer success (3 × $200K loaded) | ($600,000) | — |
| Marketing / paid acquisition | ($500,000) | — |
| G&A, E&O and cyber insurance, legal | ($350,000) | — |
| **Profit before owner compensation** | **$1,712,500** | — |
| Owner compensation at market (founder-CEO / staff engineer) | ($300,000) | — |
| **Economic profit** | **$1,412,500** | — |

*Breakeven after paying the founder at market is ~164 seats. Below that, the founder is subsidizing the company with their own wage.*

For comparison, the source formula's hardware version at the same scale: 250 seats on batched owned clusters needs ~9 batched clusters, or ~18 with the formula's 2X redundancy (~$11.5M of capex at $40K/GPU), to run a weaker model, at a cost per seat no lower than the API. Priced at the formula's $132,968, it would earn a large paper margin on seats no buyer has a reason to choose over cheaper Opus-backed seats. Priced at the market, it earns about the same gross margin as the API version, with $11.5M of hardware at risk of obsolescence.

---

## Section 07 — Sensitivity analysis

**The analytical question:** Which matters more — what the operator pays for tokens, what it charges, or how much work each seat actually does?

**Exhibit 8 — Operator gross margin per seat, by token cost and seat price**

| Token cost per agent-hour | $24,000 | $36,000 (base) | $48,000 | $60,000 |
|---|---|---|---|---|
| $4 (light use) | $14,480 | $26,480 | $38,480 | $50,480 |
| **$8.88 (base)** | $4,330 | **$16,330** | $28,330 | $40,330 |
| $15 (heavy) | ($8,400) | $3,600 | $15,600 | $27,600 |
| $25 (very heavy / fast mode) | ($29,200) | ($17,200) | ($5,200) | $6,800 |

*2,080 agent-hours per seat-year; $1,200 sandbox cost per seat. A flat seat price leaves the operator holding the token risk: one step down this grid erases most of the base-case margin.*

**Exhibit 9 — Buyer's net saving per seat, by share of a developer's work done and seat price**

| Agent's share of a median developer's output | $24,000 | $36,000 (base) | $48,000 | $60,000 |
|---|---|---|---|---|
| 20% | ($9,645) | ($21,645) | ($33,645) | ($45,645) |
| 30% | $8,032 | ($3,968) | ($15,968) | ($27,968) |
| 40% | $25,710 | $13,710 | $1,710 | ($10,290) |
| 60% | $61,064 | $49,064 | $37,064 | $25,064 |

*Value of work = share × $176,774 (BLS median wage × 1.3); less the seat price and ~$21,000 of senior review time. This grid, not the developer's salary, is the price ceiling. At 100% substitution (the source chat's assumption) any price below ~$156,000 would work, which is why the chat's prices looked reasonable.*

### The scenario the grid does not show

Exhibits 8 and 9 vary one side of the trade at a time. An ordinary bad year at the 250-seat base case:

**Exhibit 10 — Adverse case, nothing exotic**

| Event | Impact | Comment |
|---|---|---|
| Base case economic profit (Exhibit 7) | $1,412,500 | |
| A model lab or funded rival bundles agent seats; price cut 15% to $30,600 | ($1,350,000) | The supplier is also a competitor |
| Token use runs 30% over plan (longer contexts, retries, harder repos) | ($1,385,250) | Flat seat price; operator absorbs it |
| 15% of seats churn mid-year after a quarter of low acceptance | ($306,188) | Lost half-year gross margin |
| One agent-caused production incident: credits, legal | ($150,000) | |
| **Adverse case economic profit** | **($1,778,938)** | |

*None of these is unusual for a 2026 AI product. Any two together wipe out the year. The business has no fixed assets to fall back on, which is good, and no pricing power, which is the problem.*

---

## Section 08 — What the source conversation got wrong

**The analytical question:** Which claims in the source chat survive checking, and which should be dropped from any pitch built on it?

**Exhibit 11 — Error log**

| # | Claim in the source chat | What is actually true | Effect on the case |
|---|---|---|---|
| 1 | Opus 5.5 needs ~600 GB unquantized, 350–400 GB at 4-bit, 1.2 TB with full context | Anthropic does not publish model size. These are estimates for open models, stated as fact. Opus cannot be self-hosted at any precision. | The whole hardware branch is hypothetical. |
| 2 | Anthropic serves Claude on "over 1 million Trainium2 chips" and Inferentia2 handles API traffic | Anthropic says it runs Claude on AWS Trainium, Google TPUs and NVIDIA GPUs, and Amazon announced a ~1M Trainium2 plan. Which chip serves which request is not public. | Irrelevant to the business; should not be cited. |
| 3 | Opus 5.5 is "40% cheaper and 30% faster" and included in a $20 plan | Not verifiable from the chat's sources. Published API list price is $4 / $20 per million tokens, 20% below Opus 5. | Use list prices only. |
| 4 | `(cost ÷ 5Y × 8,760) × 2,080` is the hourly cost of one seat | It recovers 23.7% of depreciation. True only if the other 76% of hours are sold to someone else. | Formula price has no link to cost (Section 05). |
| 5 | One agent needs one 16-GPU cluster | Inference is batched; one cluster serves ~30–40 long-context agents. | True cost per seat is ~$2–19K, not $76K. |
| 6 | `2X` means redundancy, `4A` means four agents | Doubling all hardware is not standard practice (N+1 is). 4A multiplies the price by four for four agents that would share the same batched cluster. | Inflates cost and price. |
| 7 | "+75% margin" | A 75% markup is a 42.9% margin. The chat used both on the same $51.45B ($22.05B vs. $38.59B of margin) and reversed the split on $300B. | Margin overstated by up to 1.75×. |
| 8 | "Top 15% earn $196K+, 262,500 people" | A $196K *loaded* cost is a ~$145K wage — roughly the top ~45%. A $196K *salary* is near the top ~10–15% (BLS 90th percentile wage: $214,670). The chat mixed the two. | $51.45B figure is undefined. |
| 9 | L1–L7 ladder: 25/40/20/10/4/0.8/0.2% split; L6 at $1.15M, L7 at $2.4M | The split is invented. L6/L7 pay exists at a few big tech firms, not across 1.75M developers. Ladder total $387B vs. ~$330–350B from BLS. | Overstates the pool ~10–15%; tiers are not data. |
| 10 | "Agents per tier" = salary ÷ $132,968, giving 2.9M agents | Circular: dividing payroll by a price and multiplying back returns payroll. It says nothing about what an agent can do. | Remove from any pitch. |
| 11 | Top 10 / top 20 industries, agent counts, $1.67T and $2.33T "capitalization" | No sources given; numbers not traceable. | Remove. |
| 12 | 9.34M jobs lost; robotics 3.7M, later 8.72M | Unsourced, and inconsistent within the chat. | Out of scope; remove. |
| 13 | Healthcare is 7.5% of GDP, later 23.7%; shadow economy 10–12% of GDP | The chat contradicts itself on healthcare. Shadow-economy estimates vary by method and are usually lower for the US. | Macro section is a thought experiment, not a forecast. |
| 14 | `($300K × 10,000 ÷ 43,800) × 90`, then "if $6.1M is 20%" | The 10,000 and 90 were never defined; the arithmetic is right but measures nothing. | Ignore. |

*What survives checking: H100 purchase and rental ranges are in line with October 2026 market data; BLS developer counts (1,717,800) and median wage ($135,980) are correct; Opus 5.5 API prices ($4 / $20, fast mode $8 / $40) are correct; the arithmetic of each individual formula evaluation is correct. The errors are in what the formulas assume, not in the multiplication.*

---

## Section 09 — Risk register

**The analytical question:** What can stall or break the corrected business, and what specifically prevents it?

**Exhibit 12 — Ranked exposures**

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Model labs or funded coding-agent companies sell equivalent seats directly | High | High | Specialize where a general tool is weakest: a vertical (e.g., legacy migrations, test backfill, dependency upgrades) with its own evaluation harness and review workflow. |
| Token use above plan on a flat seat price | High | High | Price per accepted pull request or per task, or include a token allowance with overage. Track cost per merged change weekly. |
| Agent completes too small a share of work for the buyer to save money (Exhibit 9) | Medium | High | Sell only into backlogs the agent has been measured on in a paid pilot; publish acceptance rates per repo. |
| Agent ships a harmful change to production | Medium | High | Agents open pull requests only; human review and CI gates are mandatory; E&O and cyber cover; contractual liability caps. |
| Supplier price or terms change (model deprecation, rate limits) | Medium | Medium | Keep the harness model-agnostic; hold accounts with at least two model providers or cloud channels. |
| Buyer IP and data-handling requirements (SOC 2, on-prem demands) | Medium | Medium | SOC 2 early; for regulated buyers, offer a private-cloud deployment through AWS, Google Cloud or Microsoft rather than owned hardware. |
| Reputational and political backlash to "replacing developers" | Medium | Medium | Sell capacity on backlogs, not headcount cuts; that is also what buyers actually buy. |

---

## Section 10 — Recommendation

**The analytical question:** Given all of it, what should this operator actually do?

Four findings converge:

1. **Compute is cheap and getting cheaper** (Section 05) — a full agent-year costs ~$18,500 on the API. That is real, and it is why the idea is attractive.
2. **Owning GPUs adds cost, risk and a weaker model, and removes nothing** (Sections 04–05) — Opus is only sold as a service, and owned hardware costs about what renting does.
3. **The price ceiling is the share of work an agent finishes, not the developer's salary** (Section 07, Exhibit 9). Below ~33% at $36,000, the buyer loses money.
4. **Five of five forces are unfavorable and the supplier is also a competitor** (Section 02) — margin is held down from both sides, and an ordinary bad year erases it (Exhibit 10).

> **Recommended structure and sequence**
>
> **Drop the hardware and the salary-based price. If the idea is pursued, build a managed agent-operations service on the API.** Pick one narrow, measurable kind of work — dependency upgrades, test backfill, framework migrations — where an agent's acceptance rate can be measured in a paid pilot before a seat is sold. Price per accepted change, or a seat price with a token allowance, so token overruns are not the operator's alone. Include human review in the offer, because that is what makes the buyer's math work.
>
> Target ~164 seats (about $5.9M of revenue at $36,000) as the floor for paying a team and the founder at market, and 250+ for a real outcome. Run the first 20–30 seats as priced pilots to measure the two numbers this memo cannot: the share of work accepted, and tokens per accepted change.

> **What would change this recommendation**
>
> If open-weights models reach parity with frontier models on long agentic coding work *and* a buyer group requires fully on-premises deployment (defense, some finance and healthcare), owned hardware gets a real niche, and the corrected per-token cost from Exhibit 5 (not the source formula) should price it. If measured acceptance rates come in at 50%+ of a developer's output, Exhibit 9 supports prices of $60,000+ and the economics improve sharply. If a model lab cuts agent-seat prices below ~$25,000, the reseller version stops working at any scale.

### Metrics to run it on

- **Accepted changes per seat per week** — the number that sets the buyer's savings and the ceiling price.
- **Token cost per accepted change** — tracked weekly against the $8.88/agent-hour base case; the early warning on margin.
- **Buyer net saving per seat** (Exhibit 9 inputs, measured) — if negative for a customer, that seat will churn.
- **Gross margin per seat** — target ≥40% after tokens and sandbox.
- **Seats under contract vs. the 164-seat floor** — the number that decides whether the founder is paid.

---

**ANALYTICAL BASIS** — Figures are directional estimates for an operator selling AI coding-agent seats to US employers, built for structural analysis rather than as an audited forecast. Developer counts and wages are from the US Bureau of Labor Statistics (May 2025); the 1.3× loaded-cost factor is an assumption. Model prices are Anthropic's published API list prices for Claude Opus 5.5 ($4 input / $20 output / $0.20 cached input per million tokens; fast mode $8 / $40). The per-hour token profile (~120 turns, ~100K-token context 95% cached, ~1.5K output tokens per turn) is an assumption and the most uncertain input in the memo. H100 rental prices are from an October 2026 survey of 45 providers ($1.70 floor, $3.49 median); purchase price uses the source chat's $40K/GPU, close to new 8-GPU server pricing per GPU. Cluster opex (power at $0.10/kWh, colocation at $150/kW-month, ~$60K/yr operations) and batching capacity (~30 long-context agents per 16× H100 cluster) are engineering estimates. Market-share, automation-share and price-capture figures in Exhibit 1 are assumptions, labeled as such. Claims from the source conversation are treated as hypotheses; Section 08 lists which were corrected.

**FRAMEWORKS APPLIED** — Hypothesis-first problem framing with explicit tests · Market funnel (payroll ceiling → automatable work → vendor revenue pool → SOM) · Porter's Five Forces · Value chain and margin-pool analysis, both sides of the trade · Domain-specific structural analysis (closed weights, batching, hardware life, labor law) · Cost-plus formula audit and build-vs-rent decomposition · Two two-variable sensitivities (operator margin, buyer saving) · Adverse-case scenario · Source-claim error log · Risk register · Economic profit adjustment for owner labor.
