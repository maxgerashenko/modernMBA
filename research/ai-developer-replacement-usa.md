# How Many Agents Make an Engineer

**Artifact:** https://claude.ai/artifact/W1kcyA5nYTzimgDhrULt36
**Notion:** https://app.notion.com/p/413ba21e32d4815980fdd79459e1d203?pvs=204

An MBA-style teardown of one question in four parts. What does it cost to run AI coding agents at pure cost, meaning infrastructure and its support only, with no profit on top? How does that compare with paying US engineers from L1 to L7? Could agents replace the whole market, or do hardware, token supply or the technical limits of LLMs stop it? And if clients paid what they pay their engineers today, what margin would the business earn?

**SUBJECT:** running frontier-size coding agents on owned GPU racks at pure cost, and selling them as engineer replacements to US employers
**MARKET:** US software developers and QA testers, ~1.9M people and ~$346B of loaded payroll (BLS 2025), split into seven levels (L1–L7)
**BASE CASE:** one NVIDIA GB300 NVL72 rack (~$5.7M deployed, 3-year life) running ~36 agents 24/7 at a 1M-token context and 80 tokens/s, with 2X compute for a future model. Pure cost $8.58 per agent-hour, or $17,841 per engineer-year of agent work (2,080 h). Agents per level double from 1 (L1) to 64 (L7) and do all the work, including review.
**SOURCE:** a chat with another AI assistant that built the formula `((1.28 TB / 80 GB × $40K) / (4Y × 8,760H)) × 2,080H × 2X + 75%M`, a hypothesis review with Max that set the inputs above, and an independent second memo (research/ai-developer-agents-independent-usa.md) used as a cross-check.
**REVISED 18 NOV 2026:** base case moved from GB200 NVL72 to GB300 NVL72. Rack ~$5.7M deployed (GB200: ~$3.9M), 140 kW (132 kW), ~20.7 TB of memory (13.4 TB), the same 576 TB/s of bandwidth, and ~36 agents per rack (30). Pure cost per agent-hour rises from $7.84 to $8.58.

---

## Preface — Hypotheses, stated before the verdict

**The analytical question:** What has to be true for agents to replace US engineers from L1 to L7, at a cost below their salaries, at the scale of the whole market, and is each of those things true?

**Exhibit A — Hypotheses, tests, and results**

| # | Hypothesis | How it is tested | Result |
|---|---|---|---|
| H1 | Running an agent at pure cost is a small fraction of a salary. | Build the agent-hour from rack write-off, power, space, rack operations, sandbox and support staff, with no margin. | **Supported.** $8.58 per agent-hour, $17,841 per engineer-year of agent work: 17% of an L1's $105K loaded cost. |
| H2 | At pure cost, agents are cheaper than engineers at every level, L1 to L7. | Multiply the pure cost by the agents each level needs, under three multiplier rules. | **Depends on the rule.** Doubling (1 → 64): yes at L1–L6, from 17% of salary at L1 to 82% at L6; an L7 costs 104%. Failure-based (agents fail more on long tasks): yes at L1–L4 (8–15%), no at L5 (372%), impossible at L6–L7. |
| H3 | The hardware exists to replace the whole US market. | Racks, GPUs, capital and power needed vs. what NVIDIA builds and what the US grid connects per year. | **Over years, not at once.** Doubling rule: ~42,900 GB300 racks (3.1M GPUs, ~$245B, ~7.8 GW). That is ~19 months of 2025's global rack output, or ~7 months of 2026's forecast, and about nine months of the most power the US grid has ever connected for data centers. |
| H4 | LLM token supply can keep up. | Tokens the fleet would process per month vs. the largest provider today. | **Yes, because tokens are made by the hardware in H3.** ~0.87 quadrillion new tokens a month, about 27% of everything Google processes (3.2 quadrillion a month, May 2026). |
| H5 | LLM technical requirements (1M-token context, 80 tokens/s) don't block it. | Memory and bandwidth per agent on each machine. | **Supported on rack-scale systems only.** A 16× H100 machine fits zero agents at a 1M context; a GB300 NVL72 rack fits ~36 at 80 tokens/s. |
| H6 | Enough agents can do any level's work. | Agent success rate vs. task length (METR time-horizon data). | **The real limit.** Success compounds down with task length, so senior work (weeks- to months-long tasks) needs a number of attempts that grows without bound. Capability, not hardware, caps seniority today. |
| H7 | Charging clients their current salaries gives a large margin. | Gross margin = 1 − pure cost ÷ salary, by level. | **Supported: 66% across the whole market** (doubling rule), from 83% at L1 to 18% at L6; L7 loses money. But a client saves nothing at that price, so it is a ceiling, not a selling price. |
| H8 | Agents review each other; no human is needed. | Max's assumption, cross-checked with the independent memo. | **Untested and decisive.** If a human senior must review and answer for the work, it adds ~$23,600 per L1 replaced (independent memo), about a third more than the agent cost. |

> **How the hypotheses resolve:** The cost side is not the problem. At pure cost, an agent's year of work is $17,841, and under the doubling rule every level through L6 costs less than the salary; only an L7 (64 agents) costs slightly more, at 104%. The hardware for the whole market is buildable, but it takes years of global GPU output and grid power. What can't be bought is reliability on long tasks: agents finish short tasks and fail on long ones, so L1–L4 are replaceable now and L5–L7 are not, whatever the hardware.

---

## Section 00 — Executive summary

**The analytical question:** At pure cost, can agents replace US engineers from L1 to L7, is it physically possible at full-market scale, and what margin does a business earn if clients keep paying today's salaries?

| KPI | Value | Note |
|---|---|---|
| Pure cost per agent-hour | $8.58 | Rack $7.91 + sandbox $0.30 + platform support $0.36; no margin |
| Pure cost per engineer-year of agent work | $17,841 | 2,080 h; a 24/7 agent costs $75,140 a year and covers 4.2 of them |
| Pure cost vs. salary, L1 → L7 (doubling rule) | 17% → 104% | 1 agent for L1 up to 64 for L7 |
| Whole US market at pure cost | ~$116B vs. ~$346B payroll | 6.5M engineer-years of agent work |
| Hardware for the whole market | ~42,900 racks, ~$245B, ~7.8 GW | ~7 months of 2026's forecast global NVL72 output |
| Margin if clients pay current salaries | 66% (83% at L1, −4% at L7) | Clients save nothing at that price |
| What actually stops L5–L7 | Agent reliability on long tasks | Not hardware, tokens or cost |

> **Recommendation: Conditional. Agents are cheap enough to replace every level up to L6 at pure cost, and the hardware for the whole US market can be built over two to four years, but agents can't yet do senior work reliably. Build a business that replaces L1–L4 work, price it well below salaries, and treat L5–L7 as out of reach until agents can finish weeks-long tasks.**
>
> At pure cost, one GB300 NVL72 rack runs ~36 agents with 1M-token contexts at 80 tokens/s, and an agent-hour costs $8.58 including rack write-off, power, space, operations, sandbox and support staff. One engineer-year of agent work costs $17,841. Under the doubling rule, an L1 costs 17% of its salary in agents, an L6 costs 82% and an L7 costs 104%. Across the whole US market, replacing every developer would cost ~$116B a year against ~$346B of payroll.
>
> Physically, that needs ~42,900 racks (3.1M GPUs, ~$245B, ~7.8 GW). NVIDIA built ~27,300 of these racks in 2025, and 70,000–80,000 are forecast for 2026, all of them already sold to other buyers. The US grid has never connected more than ~10 GW of new data-center demand in a year. So the whole market takes years of supply, not one purchase. Token supply follows from the hardware; the fleet would process about a quarter of what Google processes today.
>
> The real limit is technical. Agents fail more often the longer the task, and the failures compound. On the independent memo's failure model, L1–L4 cost only 8–15% of salary in agents, but an L5 needs ~100 agent-years ($1.78M against a $480K salary) and L6–L7 can't be reached at any count. If clients paid their current salaries, the margin would be 66% across the market and 91% on L1–L4 alone. But a client saves nothing at that price, so the business has to share the saving to win the sale.

---

## Section 01 — Market definition and capacity: pure cost vs. salary, L1 to L7

**The analytical question:** What does each level cost at pure cost in agents, against its salary, and can the hardware and the models supply the whole market?

**Exhibit 1 — Pure cost of agents vs. salary, by level (doubling rule)**

| Level | Loaded cost / yr | Agents (engineer-years of agent work) | Pure cost of agents | Cost as % of salary | Saving at pure cost | Margin if client pays salary |
|---|---|---|---|---|---|---|
| L1 Junior | $105,000 | 1 | $17,841 | 17% | $87,159 | 83% |
| L2 Mid | $155,000 | 2 | $35,683 | 23% | $119,317 | 77% |
| L3 Senior | $215,000 | 4 | $71,366 | 33% | $143,634 | 67% |
| L4 Staff | $300,000 | 8 | $142,732 | 48% | $157,268 | 52% |
| L5 Principal | $480,000 | 16 | $285,463 | 59% | $194,537 | 41% |
| L6 Distinguished | $700,000 | 32 | $570,927 | 82% | $129,073 | 18% |
| L7 Fellow | $1,100,000 | 64 | $1,141,854 | 104% | ($41,854) | −4% |

*Pure cost = $8.58 per agent-hour × 2,080 h × agents. No margin, no sales or overhead. Loaded cost = pay × employer taxes and benefits; directional, set so the level totals reconcile to BLS payroll (Exhibit 3). The doubling rule is Max's assumption, and it includes agents doing their own review.*

**Exhibit 2 — Pure cost per engineer replaced under three rules for "how many agents"**

| Level | Loaded cost | Doubling (1 → 64) | Linear (1, 1, 2, 3, 4, 6, 10) | Failure-based (task length vs. agent success) |
|---|---|---|---|---|
| L1 Junior | $105,000 | $17,841 (17%) | $17,841 (17%) | $9,813 (9%) — 0.55 agent-years |
| L2 Mid | $155,000 | $35,683 (23%) | $17,841 (12%) | $11,954 (8%) — 0.67 |
| L3 Senior | $215,000 | $71,366 (33%) | $35,683 (17%) | $16,593 (8%) — 0.93 |
| L4 Staff | $300,000 | $142,732 (48%) | $53,524 (18%) | $46,388 (15%) — 2.6 |
| L5 Principal | $480,000 | $285,463 (59%) | $71,366 (15%) | $1,784,146 (372%) — ~100 |
| L6 Distinguished | $700,000 | $570,927 (82%) | $107,049 (15%) | not reachable |
| L7 Fellow | $1,100,000 | $1,141,854 (104%) | $178,415 (16%) | not reachable |

*The failure-based counts come from the independent memo: agent success = 0.8 ^ (task length ÷ 8 h), with typical tasks of 4 h (L1) up to 2,000 h (L7), based on METR's measured time horizons. Those counts are agent time only; the independent memo also adds a human reviewer, which this table leaves out. The rules agree that L1–L4 are cheap. They disagree completely on L5–L7.*

### Adding it up across the US

**Exhibit 3 — Whole-market replacement at pure cost (doubling rule)**

| Level | Share (assumed) | Headcount | Payroll | Engineer-years of agent work | Pure cost |
|---|---|---|---|---|---|
| L1 Junior | 27% | 514,458 | $54.0B | 514,458 | $9.2B |
| L2 Mid | 40% | 762,160 | $118.1B | 1,524,320 | $27.2B |
| L3 Senior | 21% | 400,134 | $86.0B | 1,600,536 | $28.6B |
| L4 Staff | 8% | 152,432 | $45.7B | 1,219,456 | $21.8B |
| L5 Principal | 3% | 57,162 | $27.4B | 914,592 | $16.3B |
| L6 Distinguished | 0.8% | 15,243 | $10.7B | 487,776 | $8.7B |
| L7 Fellow | 0.2% | 3,811 | $4.2B | 243,904 | $4.4B |
| **Total** | **100%** | **1,905,400** | **$346.2B** | **6.51M** | **$116.1B** |

*Headcount total is BLS 2025 (1,717,800 software developers + 187,600 QA analysts and testers). The split by level is an assumption. At pure cost, the whole market costs 34% of its payroll.*

**Exhibit 4 — Can the hardware, power and tokens supply it?**

| Requirement | Doubling rule, all levels | Failure-based, L1–L4 only | Supply today |
|---|---|---|---|
| Engineer-years of agent work | 6.51M | 1.56M | — |
| Agents running 24/7 | 1.54M | 0.37M | — |
| GB300 NVL72 racks (36 agents each) | ~42,900 | ~10,300 | ~27,300 built in 2025; 70,000–80,000 forecast for 2026, worldwide, all buyers |
| GPUs (72 per rack) | ~3.1M | ~0.7M | — |
| Capital at ~$5.7M per rack | ~$245B | ~$59B | NVL72 output worth ~$710B forecast for 2027 |
| Power (140 kW × 1.3 overhead) | ~7.8 GW | ~1.9 GW | Most the US grid has connected for data centers in one year: ~10 GW |
| New tokens processed per month | ~0.87 quadrillion | ~0.21 quadrillion | Google, all products: ~3.2 quadrillion a month (May 2026) |

*Racks, power and tokens are one constraint, not three: tokens come from racks, and racks need power. Replacing L1–L4 needs about two months of 2026 rack output; replacing every level under the doubling rule needs more than half a year's output and most of a year of record grid additions. Both are possible over 2–4 years and impossible at once.*

**Exhibit 5 — Market funnel, payroll ceiling to SOM**

| Layer | Definition | Value |
|---|---|---|
| Payroll pool (ceiling) | All US developers and QA testers, loaded | ~$346B / yr |
| Technically replaceable now | L1–L4, where agents finish the work (failure-based rule) | ~$304B / yr of payroll |
| Pure cost of replacing it | 1.56M engineer-years of agent work × $17,841 | ~$28B / yr |
| Realistic vendor pool (SAM) | 10–30% of L1–L4 work moved to agents within ~3 years, priced at ~50% of salary — **assumption** | ~$15–46B / yr |
| SAM — this segment | Operators that own racks and sell managed agents (~10%) — **assumption** | ~$1.5–4.6B / yr |
| **SOM — 3 yr** | **2 GB300 racks, 303 engineer-years of agent work, L1–L3 mix, priced at salary** | **~$21.5M / yr** |

*Cross-check: paid AI coding tools are already a multi-billion-dollar category; Cursor alone passed $2B in annualized revenue in March 2026 (Bloomberg, TechCrunch).*

The capacity math that actually governs this:

- **Cost is not the cap.** At pure cost, every level through L6 is cheaper than its salary under two of the three rules.
- **Hardware is the cap on speed, not on scale.** The whole market takes years of global GPU output and record grid additions.
- **Agent reliability is the cap on seniority.** Today it stops at roughly L4.

---

## Section 02 — Industry structure (Five Forces)

**The analytical question:** What return does a rack-owning agent operator earn, structurally, before any firm-specific advantage?

**Exhibit 6 — Force assessment**

| Force | Rating | Evidence |
|---|---|---|
| Supplier power (NVIDIA, memory makers, model weights) | Very high | NVIDIA sells the only rack-scale systems that fit this workload; non-priority buyers report 30–52 week lead times. DRAM rose ~90–95% in Q1 2026 and HBM3E ~20%. The top closed models cannot be licensed for self-hosting. |
| Buyer power (engineering managers, CTOs) | High | Buyers can measure output, cancel monthly, and compare with API agents and in-house tools. |
| Threat of new entry | High | $5.7M per rack is a barrier, but clouds rent the same racks by the hour. |
| Substitutes | Very high | Claude Code, Cursor, GitHub Copilot and the labs' own agents; offshore contractors; hiring. |
| Rivalry | High | Model labs sell agents at API prices that run ~8× the rack's pure cost at a 1M-token context, so rivalry is over model quality more than price. |

*Four forces strongly unfavorable, rivalry less so. Owning racks gives a cost edge but not pricing power on its own.*

---

## Section 03 — Value chain and margin pool

**The analytical question:** If a client pays a full L1 salary for one engineer-year of agent work, who takes what?

**Exhibit 7 — Value extracted per L1 replaced, priced at the $105,000 salary**

| Participant | Take | Risk carried |
|---|---|---|
| NVIDIA and system builder (rack write-off share) | $12,532 | None after sale. |
| Power, colocation, rack operations | $3,927 | None. Metered or contracted. |
| Sandbox, CI runners | $624 | None. Metered. |
| Platform and infrastructure support staff | $758 | Salaried. |
| Model weights (open-weights, ~1.2 TB) | $0 license — **assumption** | No open model is guaranteed to match the top closed models. |
| **The operator (before sales and overhead)** | **$87,159** | **Unused rack slots, obsolescence, model quality, uptime, liability for bad changes.** |
| Client | Saves $0 | Pays what it paid the engineer, carries the code-quality risk. |

> **Who should get the saving:** At salary-parity pricing the operator keeps 83% and the client keeps nothing, so the client has no reason to switch. Priced at half the salary ($52,500), the operator still keeps ~$35,000 per L1 and the client saves $52,500. The pure cost is small enough that the price can be set almost anywhere above it.

---

## Section 04 — Domain-specific structural factors

**The analytical question:** What do the hardware, power and AI-model landscapes do to this business that a generic plan would miss?

**Exhibit 8 — Structural factors and their transmission**

| Factor | Effect | Mechanism |
|---|---|---|
| Memory per agent at a 1M-token context | Decides the hardware | A 1M-token context takes ~100 GB (assumed ~10 GB per 100K tokens). A 16× H100 machine holding a 1.2 TB model has 80 GB left, less than one context. |
| Bandwidth sets agents per rack | ~36 agents per GB300 rack at 80 tok/s | 576 TB/s ÷ 80 tok/s ≈ 7.2 TB read per step: the model plus ~60 contexts in theory. 2X compute halves that to ~30 on GB200; GB300's faster compute (measured 9–29% more inference throughput at interactive speeds, 1.5× FP4 on paper) lifts it to ~36. Memory bandwidth is the same on both racks. |
| Fast-link domain size | Rack-scale systems only | H100 links 8 GPUs at full speed; GB200/GB300 NVL72 link 72 in one rack. Copper cable length and ~120–140 kW of liquid-cooled power cap the domain at one rack. |
| Agent reliability vs. task length | Caps seniority | METR measures the length of task agents finish 50% or 80% of the time; the 80% horizon was ~3 h in April 2026 and doubles every ~4 months. Success compounds down with longer tasks, so L5–L7 work (weeks to months) needs an unbounded number of attempts. |
| GPU supply | Years for the whole market | ~27,300 GB200/GB300 racks built in 2025, 70,000–80,000 forecast for 2026 (Morgan Stanley). |
| Grid power | Years for the whole market | The US has connected at most ~10 GW of new data-center demand in a year; BNEF expects 118 GW installed by 2030 (July 2026). |
| Memory shortage | Rental up, purchase flat | DRAM rose ~90–95% in Q1 2026 and HBM3E ~20%. H100 purchase prices held at $27K–40K through October 2026. |
| Closed model weights | Limits what an owner can run | Claude Opus and Fable are sold only as a service. An owner runs an open-weights model, which has generally trailed the top models on long agentic coding work. |
| Hardware economic life | 3 years used | NVIDIA ships a new architecture roughly yearly. |
| Accountability and law | Keeps humans near the work | Someone must approve merges and answer for outages; the WARN Act sets notice duties for mass layoffs; the US Copyright Office requires human authorship for protection. |

---

## Section 05 — Unit economics: the agent-hour at pure cost

**The analytical question:** What does one agent-hour cost with no margin, on each machine, and how does that compare with renting a model lab's API?

### The cost base, isolated

**Exhibit 9 — Pure cost of one agent-hour, GB300 NVL72 base case**

| Line | Per rack / yr | Per agent-hour | Note |
|---|---|---|---|
| Rack write-off ($5.7M deployed ÷ 3 yr) | $1,900,000 | $6.02 | Purchase orders ~$5.0M, ~$5.7M deployed (Data Gravity, Aug 2026) |
| Power (140 kW × 1.3 × $0.10/kWh) | $159,432 | $0.51 | 24/7 at full load |
| Colocation and space (140 kW × ~$200 per kW-month) | $336,000 | $1.07 | Liquid-cooled high-density colo rate, 2026 |
| Rack operations staff | $100,000 | $0.32 | Assumption |
| **Rack subtotal (÷ 36 agents)** | **$2,495,432** | **$7.91** | |
| Sandbox VM and CI minutes | — | $0.30 | Per agent |
| Platform and infrastructure support (1 engineer per 2 racks, $230K) | $115,000 | $0.36 | Assumption |
| **Pure cost per agent-hour** | | **$8.58** | **$17,841 per 2,080-h engineer-year; $75,140 per 24/7 agent** |

**Exhibit 10 — Pure cost by machine vs. API prices (which include the lab's margin)**

| Machine | Agents served | Pure cost per agent-hour | Per engineer-year | Note |
|---|---|---|---|---|
| 16× H100, 3 yr, fully costed, 2X | 1 (needs 2 machines) | $76.10 | $158,295 | 0 agents actually fit at a 1M context |
| **GB300 NVL72, 2X (base case)** | **~36** | **$8.58** | **$17,841** | Bandwidth-bound; ~20% more agents than GB200 from faster compute |
| GB300 NVL72, full 1.5× compute gain | 45 | $7.00 | $14,550 | If NVIDIA's 1.5× FP4 figure carried through to this workload |
| GB300 NVL72, ideal efficiency | 60 | $5.41 | $11,258 | Upper bound set by memory bandwidth |
| GB200 NVL72, 2X (previous base case) | ~30 | $7.84 | $16,309 | ~$3.9M rack at 132 kW |
| Reference: Fable 5.1 API, full 1M context | — | ~$72 (price) | $149,760 | $10 / $50 per M tokens; cached reads assumed $0.50 |
| Reference: Opus 5.5 API, 100K context | — | $9.46 (price) | $19,677 | Smaller model and context |

*The API prices include the labs' own margins, so they are not pure cost. Owning the right rack is the only way to reach pure cost.*

**Exhibit 11 — Per-level P&L for one engineer replaced, client pays the full salary (doubling rule)**

| Level | Price (= salary) | Pure cost | Gross profit | Gross margin |
|---|---|---|---|---|
| L1 Junior | $105,000 | $17,841 | $87,159 | 83% |
| L3 Senior | $215,000 | $71,366 | $143,634 | 67% |
| L5 Principal | $480,000 | $285,463 | $194,537 | 41% |
| L7 Fellow | $1,100,000 | $1,141,854 | ($41,854) | −4% |

*Under the doubling rule, revenue per engineer-year of agent work falls as level rises: $105,000 at L1, $53,750 at L3, $17,188 at L7. Junior work is the most profitable per rack.*

---

## Section 06 — Annual operating model

**The analytical question:** What does an operator with two racks earn if clients pay their current salaries for L1–L3 work?

**Exhibit 12 — Annual P&L at 2 racks, 303 engineer-years of agent work, L1–L3 mix, priced at salary (steady state)**

| Line | Annual | Per engineer-year of agent work |
|---|---|---|
| Revenue — replaces ~43 L1, ~64 L2, ~33 L3 at their salaries | $21,511,921 | $70,942 |
| Rack write-off (2 × $5.7M ÷ 3) | ($3,800,000) | ($12,532) |
| Power, colocation, rack operations | ($1,190,864) | ($3,927) |
| Sandbox and CI | ($189,216) | ($624) |
| Platform and infrastructure support | ($230,000) | ($758) |
| **Gross margin** | **$16,101,841 (75%)** | **$53,101** |
| Sales & customer success (3 × $200K) | ($600,000) | — |
| Marketing | ($500,000) | — |
| Product and orchestration engineering (4 × $230K) | ($920,000) | — |
| G&A, E&O and cyber insurance, legal | ($350,000) | — |
| **Profit before owner compensation** | **$13,731,841** | — |
| Owner compensation at market | ($300,000) | — |
| Capital charge (10% on $11.4M of racks) | ($1,140,000) | — |
| **Economic profit** | **$12,291,841** | — |

*The mix follows the national L1–L3 split in agent-years (14% L1, 42% L2, 44% L3). Replaced engineers: ~140 in total. On a single rack, breakeven is ~83 engineer-years of agent work, a bit over half the rack. At half the salary, two racks still earn ~$1.5M of economic profit; at 75%, ~$6.9M.*

---

## Section 07 — Sensitivity analysis

**The analytical question:** Which matters more: the price the client will pay, how many agents a rack holds, or how much compute a future model needs?

**Exhibit 13 — Gross profit per engineer replaced, by price as a share of salary (doubling rule)**

| Level | 100% of salary | 75% | 50% | 25% |
|---|---|---|---|---|
| L1 Junior | $87,159 | $60,909 | $34,659 | $8,409 |
| L2 Mid | $119,317 | $80,567 | $41,817 | $3,067 |
| L3 Senior | $143,634 | $89,884 | $36,134 | ($17,616) |
| L4 Staff | $157,268 | $82,268 | $7,268 | ($67,732) |
| L5 Principal | $194,537 | $74,537 | ($45,463) | ($165,463) |
| L6 Distinguished | $129,073 | ($45,927) | ($220,927) | ($395,927) |
| L7 Fellow | ($41,854) | ($316,854) | ($591,854) | ($866,854) |

*Under the doubling rule L7 loses money even at full salary, L6 does at 75% and L5 at 50%. L1–L2 stay profitable down to 25%, and L3 down to ~33%.*

**Exhibit 14 — Pure cost per engineer-year of agent work, by agents per rack and compute factor**

| Agents per rack (at 2X) | 1X compute | 2X compute (base) | 4X compute | 10X compute |
|---|---|---|---|---|
| 15 | $21,133 | $40,884 | $80,386 | $198,890 |
| 30 (no gain over GB200) | $11,258 | $21,133 | $40,884 | $100,136 |
| **36 (base)** | $11,258 | **$17,841** | $34,300 | $83,677 |
| 45 (full 1.5× compute) | $11,258 | $14,550 | $27,717 | $67,218 |
| 60 (bandwidth cap) | $11,258 | $11,258 | $21,133 | $50,759 |

*Agents scale with 2 ÷ compute factor and are capped at 60 by memory bandwidth. At 10X compute an L1's agent work costs $83,677 at the base 36 agents per rack, just under its $105,000 salary, and $198,890 at 15. If GB300's full 1.5× compute carried through (45 agents), the base cost would fall to $14,550; with no gain over GB200 (30 agents) it would rise to $21,133.*

### The scenario the grids do not show

**Exhibit 15 — Adverse case at the two-rack base case**

| Event | Impact | Comment |
|---|---|---|
| Base case economic profit (Exhibit 12) | $12,291,841 | |
| Price cut 25% to give clients a reason to switch | ($5,377,980) | Salary parity saves the client nothing |
| 20% of rack capacity unsold | ($3,188,945) | Rack costs are fixed |
| New GPU generation; racks written off over 2 years, not 3 | ($1,900,000) | |
| One agent-caused production incident | ($150,000) | |
| **Adverse case economic profit** | **$1,674,916** | |

*If a human reviewer is needed after all (H8), add ~$23,600 per L1 replaced (~$3.3M across the ~140 engineers replaced), and the adverse case becomes a loss of about $1.6M.*

---

## Section 08 — Comparative insight: 2 GB300 racks vs. the same money in 16× H100 machines

**The analytical question:** With the same capital (~$11.4M vs. ~$11.5M), how do two GB300 NVL72 racks compare with 16× H100 machines on unit economics?

**Exhibit 16 — Unit economics, ~$11.4–11.5M of hardware, priced at salary (L1–L3 mix)**

| Line | **2 GB300 NVL72 racks (main)** | 18× 16-H100 machines, 1M context | 18× 16-H100, ~600K context | 18× 16-H100, 100K context |
|---|---|---|---|---|
| Hardware cost | $11.4M | $11.5M | $11.5M | $11.5M |
| GPUs | 144 | 288 | 288 | 288 |
| Agents running 24/7 | **72** | 0 (one 1M context doesn't fit) | 9 (1 agent per 2 machines) | 72 (4 per machine) |
| Speed per agent | **~80 tok/s** | — | ~26 tok/s real (44 ideal) | ~25 tok/s real |
| Engineer-years of agent work | **303** | 0 | 38 | 303 |
| Annual pure cost (write-off, power, space, ops, sandbox, support) | $5.41M | $6.00M | $6.06M | $6.47M |
| **Pure cost per agent-hour** | **$8.58** | — | $76.84 | $10.25 |
| **Pure cost per engineer-year** | **$17,841** | — | $159,829 | $21,321 |
| Revenue at salary ($70,942 per engineer-year) | **$21.5M** | $0 | $2.7M | $21.5M |
| Gross margin | **$16.1M (75%)** | ($6.0M) | ($3.4M) | $15.0M (70%) |
| Economic profit (after $2.37M overhead, owner, 10% capital charge) | **$12.3M** | ($9.8M) | ($7.2M) | $11.2M |
| Power draw (with 1.3 overhead) | ~364 kW | ~477 kW | ~477 kW | ~477 kW |

*H100 machine: $640K (16 × $40K), 3-year write-off, $120K a year for power, space and operations. A 1.2 TB model fills 1.2 of a machine's 1.28 TB, leaving 80 GB for agent contexts at ~10 GB per 100K tokens. The 100K-context column breaks Max's 1M-context requirement and assumes 2X compute halves the 8 contexts that fit.*

What the comparison shows:

- **At the required 1M-token context, H100s can't run the business at all.** The memory left after the model is smaller than one context, so eighteen machines earn nothing and lose ~$9.8M a year.
- **Squeezing one agent onto two machines works but costs about 9× more per engineer-year** ($159,829 vs. $17,841), more than an L1's salary.
- **Cutting the context to 100K makes H100s viable**, at 20% higher pure cost than GB300, and eighteen machines then run as many agents as two GB300 racks. But each agent runs at ~25 tokens/s instead of 80, so it gets through about a third as much work per hour. Adjusted for speed (80 ÷ 25), the pure cost of an engineer-year of work is ~$68,000, about 4× GB300.
- **Why GB300 wins:** one fast link across 72 GPUs puts ~20.7 TB of memory and 576 TB/s of bandwidth behind one copy of the model. An H100 machine links only 8 GPUs at full speed and spends almost all its memory on the model.

---

## Section 09 — Risk register

**The analytical question:** What can stop a business that replaces engineers at pure cost plus a margin?

**Exhibit 17 — Ranked exposures**

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Agents can't do the work at the assumed counts (L4 and above) | High | High | Sell L1–L3 work first; measure agents per level in paid pilots before quoting L4+. |
| A human reviewer is needed after all (H8) | High | High | Price with room for ~$23,600 of review per L1; build automated verification (tests, checks) to shrink it. |
| No open-weights model does top-model work on the rack | Medium | High | Benchmark candidate models on the client's own tasks before buying a rack. |
| Rack supply and power delays (30–52 week lead times, grid queues) | High | Medium | Order through a cloud or system partner with allocation; start on rented racks. |
| Clients won't pay near salary | High | Medium | Price at 50–75% of salary; L1–L2 stay profitable down to ~25% and L3 to ~33%. |
| Unsold rack slots | Medium | High | Sign anchor clients for ~83 engineer-years before buying the first rack. |
| Hardware obsolescence | High | Medium | 3-year write-off at most; lease where possible. |

---

## Section 10 — Recommendation

**The analytical question:** Given all of it, what should be built?

Four findings converge:

1. **Pure cost is far below salaries** (Sections 01 and 05): $17,841 per engineer-year of agent work; 17% of an L1 and, under the doubling rule, 82% of an L6 and 104% of an L7.
2. **The whole market is physically possible but slow** (Section 01): ~42,900 racks, ~$245B, ~7.8 GW. That is years of global GPU output and grid additions, shared with every other AI buyer.
3. **Agent reliability, not hardware, caps seniority** (Sections 01 and 04): L1–L4 are replaceable now; L5–L7 are not, at any agent count, on today's failure rates.
4. **Pricing at salary gives a 66% margin but no reason to buy** (Sections 03 and 07): the business has to share the saving.

> **Recommended structure and sequence**
>
> **Replace L1–L4 work, not the whole ladder.** Start on rented rack capacity, run paid pilots on L1–L3 work, and measure two numbers: engineer-years of agent work per level, and whether a human reviewer is still needed. Buy the first GB300 rack once ~83 engineer-years of work are signed. Price at 50–75% of the salary replaced: at half the salary, an L1 still earns ~$35,000 of gross profit and the client saves $52,500.
>
> Treat L5–L7 as a later market that opens as the agent time horizon grows. At the current ~4-month doubling, each doubling moves the reliable task length up about one level's worth.

> **What would change this recommendation**
>
> If agents need human review, the cost per L1 more than doubles and only L1–L2 stay attractive. If agents start finishing weeks-long tasks reliably, L5–L7 open, and the doubling rule's 18–41% margins on L5–L6 at salary price become the market. If grid power or rack supply tightens further, the timeline to scale stretches but the unit economics don't change.

### Metrics to run it on

- **Engineer-years of agent work per level, measured** — against the doubling rule and the failure-based rule.
- **Human review hours per agent-year** — the H8 test.
- **Pure cost per agent-hour** — against the $8.58 base case.
- **Price as a share of salary** — what clients actually pay.
- **Rack fill** — against the ~83 engineer-year single-rack breakeven.

---

**ANALYTICAL BASIS** — Figures are directional estimates for running AI coding agents at pure cost and selling them to US employers, built for structural analysis rather than as an audited forecast. Pure cost means infrastructure and its support only: rack write-off over 3 years, power at $0.10/kWh with 1.3 overhead, colocation at ~$200 per kW-month, rack operations staff, sandbox/CI at $0.30 per agent-hour, and one platform support engineer ($230K loaded) per two racks; it excludes sales, overhead, owner pay and any margin. Developer counts are from the US Bureau of Labor Statistics (May 2025); loaded cost and the share at each level are assumptions set to reconcile to BLS-based payroll (~$346B). Max's review set the inputs: a 1.2 TB model, a 1M-token context, 80 tokens/s per agent, 2X compute for a future model, 24/7 use, agents doing their own review, and agents per level doubling from 1 to 64. The failure-based agent counts come from the independent memo in this repo, built on METR time-horizon data. GPU and rack specs are NVIDIA's published figures; rack prices are third-party estimates, because NVIDIA publishes none: GB300 NVL72 purchase orders just under $5.0M and ~$5.7M deployed (Data Gravity, August 2026), used here at the deployed figure; other estimates run from $3.7M–4.0M (Loop Capital) to $6.0M–6.5M (Tom's Hardware). The GB200 NVL72 comparison row uses ~$3.9M all-in (SemiAnalysis) at 132 kW. GB300 rack power is ~135–140 kW typical with peaks near 155 kW, used here at 140 kW. GB300 has 288 GB of HBM3e per GPU (~20.7 TB per rack) against GB200's 13.4 TB, the same 576 TB/s of memory bandwidth, and 1.5× the dense FP4 compute; measured inference throughput is 5–45% higher than GB200 (MLPerf v5.1 and v6.0, InferenceX), and 9–29% at interactive speeds, so this memo assumes ~20% more agents per rack (36 vs. 30). Colocation uses ~$196–204 per kW-month for liquid-cooled high-density space (Encor Advisors, Metro Colo Advisory). The base case moved from GB200 NVL72 to GB300 NVL72 on 18 November 2026. Rack supply: Morgan Stanley via Wallstreetcn (27,300 GB200/300 racks in 2025; 70,000–80,000 forecast for 2026) and TrendForce (August 2026: NVL72 output above $710B in 2027). Grid: BNEF (July 2026: ~10 GW the most connected in one year; 118 GW by 2030). Tokens: Google I/O (May 2026: 3.2 quadrillion tokens a month), with this memo counting ~120 turns an hour, ~1.5K output and ~5K new input tokens per turn. API references use Claude Fable 5.1 ($10 / $50 per million tokens; cached reads assumed $0.50) and Opus 5.5 ($4 / $20 / $0.20).

**FRAMEWORKS APPLIED** — Hypothesis-first framing with explicit tests · Pure-cost build-up per agent-hour · Per-level substitution table under three multiplier rules · Supply-side feasibility (racks, power, tokens) · Market sizing from payroll by level (ceiling → technically replaceable → vendor pool → SOM) · Porter's Five Forces · Value chain and margin pool · Two-variable sensitivities (price share × level; agents per rack × compute factor) · Adverse-case scenario · Hardware comparison (GB300 NVL72 vs. 16× H100, with GB200 NVL72 as a reference row) · Risk register · Economic profit adjustment for owner labor and capital.
