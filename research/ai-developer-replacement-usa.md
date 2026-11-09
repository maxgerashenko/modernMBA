# How Many Agents Make an Engineer

**Artifact:** https://claude.ai/artifact/W1kcyA5nYTzimgDhrULt36
**Notion:** https://app.notion.com/p/413ba21e32d4815980fdd79459e1d203?pvs=204

An MBA-style teardown of one pricing idea. Work out what one machine running a top coding model costs per hour, add a true 75% company margin, assume a number of agents will one day equal one software engineer (more agents for each higher level), and compare that bundle with each engineer level's salary. The memo states the hypotheses first, then rebuilds the machine-hour from the hardware: which machine can actually serve coding agents with a 1M-token context at 80 tokens a second, how many agents it holds, and what each one costs.

**SUBJECT:** an operator that owns GPU racks, runs a frontier-size coding model on them, and sells agent capacity to US employers at cost × 4 (a true 75% margin), with N agents sold per engineer replaced
**MARKET:** US software developers and QA testers, ~1.9M people (BLS, 2025), split into seven engineer levels (L1–L7)
**BASE CASE:** one NVIDIA GB200 NVL72 rack (~$3.4M, 3-year life) serving ~30 agents 24/7 at a 1M-token context and 80 tokens/s, with 2X compute for a future model. Price $22.58 per agent-hour, which is $46,961 per engineer-year of agent work (2,080 h). Agents per level double from 1 (L1) to 64 (L7).
**SOURCE:** a chat with another AI assistant that built the formula `((1.28 TB / 80 GB × $40K) / (4Y × 8,760H)) × 2,080H × 2X + 75%M`, then a hypothesis review with Max that changed its inputs. The chat's numbers are treated as claims to test, not as facts.

---

## Preface — Hypotheses, stated before the verdict

**The analytical question:** What has to be true for "N agents, priced at machine cost with a 75% margin, replace one engineer at each level" to work, and is each of those things true?

**Exhibit A — Hypotheses, tests, and results**

| # | Hypothesis | How it is tested | Result |
|---|---|---|---|
| H1 | One machine-hour is the right cost base: hardware written off over its life, plus running costs. | Rebuild the machine-hour with a 3-year life and power, rack space and staff. | **Supported, with corrections.** 16× H100: $640K ÷ 3 yr + $120K/yr = $333K/yr, or $38.05 per machine-hour (the formula had $18.26, hardware only over 4 years). GB200 NVL72 rack: ~$1.48M/yr, or $169 per rack-hour. |
| H2 | One machine runs one agent. | Model memory and bandwidth: a 1.2 TB model, a 1M-token context (~100 GB each), 80 tokens/s per agent. | **Rejected both ways.** On 16× H100, zero agents fit: 80 GB is left after the model, less than one context, and top speed is 44 tokens/s. On a GB200 NVL72 rack, ~60 agents fit in theory and ~30 in practice. Weights are loaded once and shared, so the cost per agent falls with scale. |
| H3 | H100s are the right hardware. | Compare 2× 8 H100, GB200 NVL72 and GB300 NVL72 on memory, bandwidth and how GPUs connect. | **Rejected for this workload.** H100 links only 8 GPUs at full speed; a 1.2 TB model must cross the slower network. GB200 NVL72 links 72 GPUs (13.4 TB, 576 TB/s) and serves ~30 agents at $5.64 per agent-hour. GB300 has more memory (20.7 TB) but the same bandwidth, so at 80 tokens/s it holds the same ~30. |
| H4 | Future models must be 2× smarter, so each agent needs 2X compute. | Treated as Max's assumption, since current benchmarks overstate real-world ability. Compare with how compute has scaled with capability. | **Kept as the base case; likely low.** Gains from more compute grow roughly with its log, so 2× better often takes 4–10× compute. Cheaper hardware each year pulls the other way. Sensitivity runs 1X–10X (Exhibit 11). |
| H5 | A true 75% margin: the company keeps 75% of the price. | Arithmetic. | **Applied.** Price = cost ÷ (1 − 0.75) = cost × 4. The source chat's "+75%" (cost × 1.75) was a 42.9% margin. |
| H6 | Agents per engineer grow exponentially with level: 1, 2, 4, 8, 16, 32, 64 (L1–L7). | No data can confirm a future multiplier, so the memo shows how many agents each salary can pay for. | **The deciding assumption, untested.** Senior pay grows ~1.5× per level while agents double, so seniors are the hardest to replace. At $46,961, agents save money at L1–L3 and cost more from L4 up. |
| H7 | Agents run 24/7, which makes the hour cheaper. | Check what the machine-hour already covers. | **Partly.** The machine-hour already includes power, space, staff and write-off for all 8,760 hours. Running 24/7 doesn't lower the price per hour of work. It means one agent supplies 4.2 engineer-years of hours, so a buyer needs 4.2× fewer agents. |
| H8 | Agents do everything (architecture, coding, review, testing). | Treated as Max's assumption. | **Applied.** No human review cost in the buyer's saving. This is optimistic; Section 09 lists it as a risk. |
| H9 | Owning the rack beats renting a frontier model's API. | Price the same agent-hour on Claude Fable 5.1 ($10 in / $50 out per million tokens) at a full 1M-token context. | **Supported.** The API re-bills the cached context on every turn: ~$72 per agent-hour, $149,760 per engineer-year, already including the lab's margin. The rack's price with a 75% margin is $22.58, about 31% of that. |

> **How the hypotheses resolve:** The cost side holds up once the hardware is right. One GB200 NVL72 rack runs ~30 frontier-size agents with 1M-token contexts at 80 tokens/s, and the true agent-hour costs $5.64, not the $76 that one-agent-per-machine H100 math gives. At a true 75% margin that is $46,961 per engineer-year of agent work. That is about 31% of what the same 1M-context agent-hour costs on Claude Fable 5.1's API (~$72), so price is not the problem. Two things then decide the case: how many agents really equal each level (H6), and whether an open-weights model on your own rack does Fable-class work.

---

## Section 00 — Executive summary

**The analytical question:** If one engineer at each level equals N agents priced at machine cost × 4, does the bundle beat the salary, and is there a business in owning the racks?

| KPI | Value | Note |
|---|---|---|
| Agent-hour cost, GB200 NVL72 rack | $5.64 | ~30 agents, 1M context, 80 tok/s, 2X compute, 3-yr life |
| Price at a true 75% margin | $22.58 / agent-hour | $46,961 per 2,080-h engineer-year; $197,778 per 24/7 agent |
| Same formula, 16× H100, 1 agent per machine | $633,181 / engineer-year | and 0 agents fit at a 1M-token context |
| Levels where agents save money | L1–L3 | exponential agents, 1 → 64 |
| Operator economic profit, 2 racks | $5.09M | 60 agents 24/7; breakeven ~25 agents on the first rack |
| Price ceiling set by the API | ~$72 / agent-hour | Fable 5.1 API at a full 1M-token context ($149,760 per engineer-year); the rack price is 31% of it |

> **Recommendation: Conditional. Owning the right racks makes agents cheap enough to replace L1–L3 engineers, even with a true 75% margin, but not L4 and above. The rack's price is about a third of a frontier API at the same 1M-token context, so build if an open-weights model on the rack does Fable-class work.**
>
> The idea's structure is sound: machine-hour cost, a margin, agents per level, compared with salary. What changed is the machine. A 16× H100 server can't hold even one agent with a 1M-token context, and it tops out at 44 tokens a second. A GB200 NVL72 rack links 72 GPUs at full speed, holds the model once, and leaves ~12 TB for agent contexts. Bandwidth limits it to ~60 agents at 80 tokens/s, and real efficiency plus 2X compute brings that to ~30. Each agent-hour then costs $5.64, and the true-75%-margin price is $22.58.
>
> At that price, an engineer-year of agent work costs $46,961. With agents doubling at each level, the bundle saves $58K at L1, $61K at L2 and $27K at L3, then costs more from L4 up: 64 agents for an L7 costs $3.0M against a $1.1M salary (Exhibit 1). Junior and mid-level work is the market. Senior replacement isn't, unless the multiplier stays far below doubling.
>
> As a business, two racks ($6.8M) earn about $5.1M of economic profit at full use. Price has room. On Claude Fable 5.1's API ($10 / $50 per million tokens), a full 1M-token context is re-billed every turn, so the same agent-hour costs about $72, already including the lab's margin. The rack's $22.58 is about 31% of that, and owning gets cheaper the longer the context. The weak point is the model: the operator has to run an open-weights model that does Fable-class work, since Fable itself can't be self-hosted.

---

## Section 01 — Market definition and capacity: agents per engineer level

**The analytical question:** For each engineer level, what does the agent bundle cost against the salary, and how large is the US opportunity once that is added up?

**Exhibit 1 — Agents per engineer vs. salary, by level**

| Level | Loaded cost / yr | Agents per engineer (assumed) | Bundle, 16× H100 (1 agent / machine) | Saving | Bundle, GB200 rack (30 agents) | Saving |
|---|---|---|---|---|---|---|
| L1 Junior | $105,000 | 1 | $633,181 | ($528,181) | $46,961 | $58,039 |
| L2 Mid | $155,000 | 2 | $1,266,362 | ($1,111,362) | $93,922 | $61,078 |
| L3 Senior | $215,000 | 4 | $2,532,724 | ($2,317,724) | $187,844 | $27,156 |
| L4 Staff | $300,000 | 8 | $5,065,448 | ($4,765,448) | $375,687 | ($75,687) |
| L5 Principal | $480,000 | 16 | $10,130,896 | ($9,650,896) | $751,375 | ($271,375) |
| L6 Distinguished | $700,000 | 32 | $20,261,792 | ($19,561,792) | $1,502,750 | ($802,750) |
| L7 Fellow | $1,100,000 | 64 | $40,523,584 | ($39,423,584) | $3,005,500 | ($1,905,500) |

*An "agent" here is one engineer-year of agent work (2,080 hours). A 24/7 agent supplies 4.2 of them. Loaded cost = total pay × employer taxes and benefits; directional, set so the level totals reconcile to BLS payroll (Exhibit 3). The agents-per-level column is Max's exponential assumption, not a measurement. The H100 column uses Max's revised formula ($38.05 per machine-hour × 2X × 4 × 2,080 h) and assumes one agent fits, which at a 1M-token context it doesn't.*

**Exhibit 2 — How many agents each salary can pay for (break-even multiplier)**

| Level | Loaded cost | Max agents, H100 1 / machine | Max agents, GB200 30 / rack | Max agents, GB200 60 / rack (ideal) | Assumed agents |
|---|---|---|---|---|---|
| L1 Junior | $105,000 | 0.17 | 2.2 | 4.5 | 1 |
| L2 Mid | $155,000 | 0.24 | 3.3 | 6.6 | 2 |
| L3 Senior | $215,000 | 0.34 | 4.6 | 9.2 | 4 |
| L4 Staff | $300,000 | 0.47 | 6.4 | 12.8 | 8 |
| L5 Principal | $480,000 | 0.76 | 10.2 | 20.4 | 16 |
| L6 Distinguished | $700,000 | 1.1 | 14.9 | 29.8 | 32 |
| L7 Fellow | $1,100,000 | 1.7 | 23.4 | 46.9 | 64 |

*Read across a row: the assumed number must be below the break-even for replacement to pay. At the base case it is below at L1–L3 only. Even at the ideal 60 agents per rack, L6 and L7 stay out of reach under doubling.*

### Adding it up across the US

**Exhibit 3 — US developers by level: payroll vs. agent bundle (GB200 base case)**

| Level | Share (assumed) | Headcount | Payroll | Agents needed | Bundle cost |
|---|---|---|---|---|---|
| L1 Junior | 27% | 514,458 | $54.0B | 514,458 | $24.2B |
| L2 Mid | 40% | 762,160 | $118.1B | 1,524,320 | $71.6B |
| L3 Senior | 21% | 400,134 | $86.0B | 1,600,536 | $75.2B |
| L4 Staff | 8% | 152,432 | $45.7B | 1,219,456 | $57.3B |
| L5 Principal | 3% | 57,162 | $27.4B | 914,592 | $43.0B |
| L6 Distinguished | 0.8% | 15,243 | $10.7B | 487,776 | $22.9B |
| L7 Fellow | 0.2% | 3,811 | $4.2B | 243,904 | $11.5B |
| **Total** | **100%** | **1,905,400** | **$346.2B** | **6.51M** | **$305.5B** |

*Headcount total is BLS 2025 (1,717,800 software developers + 187,600 QA analysts and testers). The split by level is an assumption; BLS does not report levels. Replacing L1–L3 only (where it saves) needs 3.64M engineer-years of agent work, a $171B bundle against $258B of payroll. That would take ~28,800 GB200 racks (~$98B of hardware).*

**Exhibit 4 — Market funnel, payroll ceiling to SOM**

| Layer | Definition | Value |
|---|---|---|
| Payroll pool (ceiling) | All US developers and QA testers, loaded (Exhibit 3) | ~$346B / yr |
| Theoretical agent revenue | L1–L3 replaced at the assumed multipliers, base price | ~$171B / yr (~$128B margin) |
| Realistic vendor pool (SAM) | 10–30% of that work automated within ~3 years — **assumption** | ~$17–51B / yr |
| SAM — this segment | Operators that own racks and sell managed agents, vs. API-based tools (~10%) — **assumption** | ~$1.7–5.1B / yr |
| **SOM — 3 yr** | **2 GB200 racks, 60 agents 24/7 (253 engineer-years of work) × $46,961** | **$11.9M / yr** |

*Cross-check: paid AI coding tools are already a multi-billion-dollar category; Cursor alone passed $2B in annualized revenue in March 2026 (Bloomberg, TechCrunch).*

The capacity math that actually governs this business:

- **Memory bandwidth is the cap per rack.** Every token, the rack reads the model plus every agent's context. At 576 TB/s and 80 tokens/s that is ~7.2 TB per step, so ~60 agents in theory and ~30 in practice.
- **The multiplier is the cap on the market.** Every revenue figure above assumes doubling agents per level. Until that is measured on real codebases, the market is a forecast.
- **The API price is a ceiling well above cost.** A 1M-context agent-hour on Fable 5.1's API costs ~$72, so the rack's $22.58 has headroom. Cheaper API models (Opus 5.5, ~$9.46 at a 100K context) set a lower bar only if they do the same work.

---

## Section 02 — Industry structure (Five Forces)

**The analytical question:** What return does a rack-owning agent operator earn, structurally, before any firm-specific advantage?

**Exhibit 5 — Force assessment**

| Force | Rating | Evidence |
|---|---|---|
| Supplier power (NVIDIA, memory makers, model weights) | Very high | NVIDIA sells the only rack-scale systems that fit this workload; non-priority buyers report 30–52 week lead times and deposits 9–12 months ahead. DRAM prices rose ~90–95% in Q1 2026 and HBM3E ~20% for 2026 contracts. The top closed models (Claude Opus) cannot be licensed for self-hosting. |
| Buyer power (engineering managers, CTOs) | High | Buyers can measure output (merged pull requests, tickets closed), cancel monthly, and compare with API agents: ~$72 per agent-hour on Fable 5.1 at a 1M-token context, less on smaller models or shorter contexts. |
| Threat of new entry | High | Capital is the barrier ($3.4M per rack) but cloud providers rent the same racks by the hour. |
| Substitutes | Very high | Claude Code, Cursor, GitHub Copilot and the labs' own agents; offshore contractors; hiring. |
| Rivalry | High | Model labs sell agents directly at API prices. At long contexts those prices run ~3× the rack's price, so the rivalry is over model quality more than price. |

*Four forces strongly unfavorable, rivalry less so. Owning racks gives a real cost edge at long contexts, but not pricing power on its own.*

---

## Section 03 — Value chain and margin pool

**The analytical question:** Of what a buyer pays for one 24/7 agent, who takes what, and who carries the risk?

**Exhibit 6 — Value extracted per 24/7 agent-year, $197,778 price**

| Participant | Take | Risk carried |
|---|---|---|
| NVIDIA and system builder (rack write-off, 1/30 of $3.4M over 3 yr) | $37,778 | None after sale. |
| Power, colocation, rack operations | $11,667 | None. Metered or contracted. |
| Model weights (open-weights model, ~1.2 TB) | $0 license — **assumption** | None; but no open model is guaranteed to match the top closed models. |
| **The operator (true 75% margin)** | **$148,333** | **Unused rack slots, hardware obsolescence, model quality, uptime, liability when an agent ships a bad change.** |
| Buyer replacing one L2 with 2 engineer-years of agent work | Saves $61,078 vs. a $155,000 engineer | Pays $93,922; carries code-quality and security risk. Saving holds only if 2 agent-years really do an L2's work. |

> **Where the 75% margin comes from:** A true 75% margin means price = cost × 4. Cost × 1.75 (the source chat's "+75%") is only a 42.9% margin. The higher margin is only possible because the rack-hour is cheap. On H100s with one agent per machine, the same margin would put an L1 replacement at $633K.

---

## Section 04 — Domain-specific structural factors

**The analytical question:** What do the hardware and AI-model landscapes do to this model that a generic plan would miss?

**Exhibit 7 — Structural factors and their transmission**

| Factor | Effect | Mechanism |
|---|---|---|
| Memory per agent at a 1M-token context | Decides the hardware | A 1M-token context takes ~100 GB (assumed ~10 GB per 100K tokens). A 16× H100 machine has 1.28 TB; a 1.2 TB model leaves 80 GB, less than one context. |
| Fast-link domain size | H100 is the wrong machine | H100 servers link 8 GPUs at ~900 GB/s through NVSwitch; across servers, InfiniBand gives ~50 GB/s per GPU. A 1.2 TB model must span that slower link. GB200/GB300 NVL72 link 72 GPUs in one rack. Copper cable length and ~120 kW of liquid-cooled power cap the domain at one rack. |
| Batching | Cost per agent falls with scale | The model is loaded once and shared. Each extra agent needs only its context and a share of bandwidth and compute. Adding agents on a fixed machine slows each one, because every context is read for every token. |
| Bandwidth sets the speed | ~30 agents per rack at 80 tok/s | 576 TB/s ÷ 80 tok/s ≈ 7.2 TB read per step: the 1.2 TB model plus ~60 contexts in theory, ~30 after real-world efficiency and 2X compute. GB300's extra memory doesn't help at this speed. |
| Memory shortage | Rental up, purchase flat | DRAM rose ~90–95% in Q1 2026 and HBM3E ~20%. H100 purchase prices held at $27K–40K through October 2026; H100 rental rose ~13% in a year to a ~$3.50 median, H200 ~26%. |
| Closed model weights | Limits what an owner can run | Claude Opus is sold only as a service. An owner runs an open-weights model of similar size, which has generally trailed the top models on long agentic coding work. |
| Hardware economic life | 3 years used | NVIDIA ships a new architecture roughly yearly. A 2-year write-off adds ~$567K per rack per year. |
| Layoffs and the WARN Act | Slows "replacement" sales | Replacing staff at scale triggers 60-day notice duties for employers with 100+ workers. Buyers more often redirect hiring budgets than cut people. |
| Copyright of AI-generated code | Contract issue for buyers | The US Copyright Office's position is that protection requires human authorship. Buyers will want IP warranties. |

---

## Section 05 — Unit economics: the agent-hour

**The analytical question:** What does one agent-hour really cost on each machine, and what does it sell for at a true 75% margin?

### The cost base, isolated

**Exhibit 8 — One engineer-year of agent work (2,080 h) by machine, 1M-token context, 80 tok/s target**

| Machine | Agents served | Cost per agent-hour | Price per engineer-year (× 4) | Note |
|---|---|---|---|---|
| Source formula: 16× H100, hardware only, 4 yr, "+75%" | 1 (×2) | $18.26 | $132,968 | No power, space or staff; markup, not margin |
| 16× H100, 3 yr, fully costed, 2X | 1 (needs 2 machines) | $76.10 | $633,181 | 0 agents actually fit at 1M context; 44 tok/s top speed |
| **GB200 NVL72, 3 yr, fully costed, 2X (base case)** | **~30** | **$5.64** | **$46,961** | ~$3.4M + $350K/yr; bandwidth-bound |
| GB200 NVL72, ideal efficiency | 60 | $2.82 | $23,480 | Upper bound |
| GB300 NVL72, 3 yr, fully costed, 2X | ~30 | $6.35 | $52,871 | ~$3.9M + $370K/yr; extra memory unused at 80 tok/s |
| **Reference: Fable 5.1 API, full 1M context (rented)** | — | **~$72 (price)** | **$149,760** | $10 / $50 per M tokens, cached reads assumed $0.50; already includes the lab's margin; cannot be self-hosted |
| Reference: Opus 5.5 API, 100K context (rented) | — | $9.46 (price) | $19,677 | Smaller model and context; not comparable at 1M |

*Rack prices are press-reported estimates; NVIDIA publishes no list prices. Specs: H100 80 GB, 3.35 TB/s; GB200 NVL72 13.4 TB, 576 TB/s; GB300 NVL72 20.7 TB, 576 TB/s. Fable's API price implies a lab cost of ~$18 per 1M-context agent-hour if the lab also keeps 75%, against the rack's $5.64. At a 100K context, Fable's API costs ~$22.20, which matches the rack price almost exactly.*

**Exhibit 9 — Per-agent P&L, annual (one 24/7 agent on a GB200 rack)**

| Line | Amount | Note |
|---|---|---|
| Price | $197,778 | $22.58 × 8,760 h = 4.2 engineer-years of work |
| Rack write-off | ($37,778) | $3.4M ÷ 3 yr ÷ 30 agents |
| Power, colocation, rack operations | ($11,667) | $350K ÷ 30 |
| **Gross margin / agent** | **$148,333** | **75.0%** |

*The agent count per rack is the line most likely to be wrong: it depends on model size, context length, speed target and the compute factor (Exhibit 11).*

---

## Section 06 — Annual operating model

**The analytical question:** What does an operator with two racks earn after paying a team, the founder, and the cost of its capital?

**Exhibit 10 — Annual P&L at 2 racks, 60 agents 24/7 (steady state)**

| Line | Annual | Per agent |
|---|---|---|
| Revenue — 60 agents × $197,778 | $11,866,667 | $197,778 |
| Rack write-off (2 × $3.4M ÷ 3) | ($2,266,667) | ($37,778) |
| Power, colocation, rack operations | ($700,000) | ($11,667) |
| **Gross margin** | **$8,900,000** | **$148,333** |
| Engineering & on-call (6 × $230K loaded) | ($1,380,000) | — |
| Sales & customer success (3 × $200K loaded) | ($600,000) | — |
| Marketing / paid acquisition | ($500,000) | — |
| G&A, E&O and cyber insurance, legal | ($350,000) | — |
| **Profit before owner compensation** | **$6,070,000** | — |
| Owner compensation at market | ($300,000) | — |
| Capital charge (10% on $6.8M of racks) | ($680,000) | — |
| **Economic profit** | **$5,090,000** | — |

*60 agents 24/7 supply 253 engineer-years of work, for example 63 L3 seniors at 4 agent-years each. On a single rack, breakeven is ~25 of 30 agent slots (83% filled). The rack is bought whole, so the first rack is the risky one.*

---

## Section 07 — Sensitivity analysis

**The analytical question:** Which matters more: how many agents a rack holds, how much compute a future model needs, or how many agents equal an engineer?

**Exhibit 11 — Price per engineer-year of agent work, by agents per rack and compute factor**

| Agents per rack (at 2X) | 1X compute | 2X compute (base) | 4X compute | 10X compute |
|---|---|---|---|---|
| 8 | $88,052 | $176,104 | $352,207 | $880,518 |
| 15 | $46,961 | $93,922 | $187,844 | $469,609 |
| **30 (base)** | $23,480 | **$46,961** | $93,922 | $234,805 |
| 60 (ideal) | $11,740 | $23,480 | $46,961 | $117,402 |

*GB200 NVL72, true 75% margin. Each doubling of the compute factor halves the agents a rack holds. At 4X, the base price doubles and only L1–L2 still save money.*

**Exhibit 12 — Buyer's saving per engineer replaced, by agent-years needed and level (base price $46,961)**

| Agent-years needed per engineer | L2 Mid ($155K) | L3 Senior ($215K) | L5 Principal ($480K) | L7 Fellow ($1.1M) |
|---|---|---|---|---|
| 1 | $108,039 | $168,039 | $433,039 | $1,053,039 |
| 2 | $61,078 | $121,078 | $386,078 | $1,006,078 |
| 4 | ($32,844) | $27,156 | $292,156 | $912,156 |
| 8 | ($220,687) | ($160,687) | $104,313 | $724,313 |
| 16 | ($596,375) | ($536,375) | ($271,375) | $348,625 |
| 32 | ($1,347,750) | ($1,287,750) | ($1,022,750) | ($402,750) |
| 64 | ($2,850,500) | ($2,790,500) | ($2,525,500) | ($1,905,500) |

*Saving = loaded cost − agent-years × $46,961 (no review cost, per H8). The diagonal is the assumed doubling (L2 = 2, L3 = 4, L5 = 16, L7 = 64). If the real multiplier grows more slowly than doubling, senior replacement opens up.*

### The scenario the grids do not show

An ordinary bad year at the two-rack base case:

**Exhibit 13 — Adverse case, nothing exotic**

| Event | Impact | Comment |
|---|---|---|
| Base case economic profit (Exhibit 10) | $5,090,000 | |
| A model lab or funded rival cuts prices; 15% price cut | ($1,780,000) | Cheaper models at short contexts undercut |
| 12 of 60 agent slots unsold (80% full) | ($2,017,333) | Lost gross margin; rack costs are fixed |
| New GPU generation; racks written off over 2 years, not 3 | ($1,133,333) | Faster write-off |
| One agent-caused production incident: credits, legal | ($150,000) | |
| **Adverse case economic profit** | **$9,333** | |

*Upside the base case leaves on the table: priced at half of Fable's 1M-context API ($36 per agent-hour), two full racks would earn ~$18.9M and ~$12.1M of economic profit. The downside test is a buyer comparing with a cheaper model at short context (Opus 5.5, ~$9.46): at that price two racks lose ~$1.8M a year.*

---

## Section 08 — What the source conversation got wrong

**The analytical question:** Which claims in the source chat survive checking, and which should be dropped from any pitch built on it?

**Exhibit 14 — Error log**

| # | Claim in the source chat | What is actually true | Effect on the case |
|---|---|---|---|
| 1 | Opus 5.5 needs ~600 GB unquantized, 350–400 GB at 4-bit, 1.2 TB with full context | Anthropic does not publish model size. This memo keeps 1.2 TB as Max's assumption for a frontier-size model. Opus cannot be self-hosted at any precision. | An owner runs an open-weights model of that size. |
| 2 | Anthropic serves Claude on "over 1 million Trainium2 chips" and Inferentia2 handles API traffic | Anthropic says it runs Claude on AWS Trainium, Google TPUs and NVIDIA GPUs. Which chip serves which request is not public. | Irrelevant to the business; do not cite. |
| 3 | Opus 5.5 is "40% cheaper and 30% faster" and included in a $20 plan | Not verifiable. Published API list price is $4 / $20 per million tokens. | Use list prices only. |
| 4 | One machine serves one agent | On 16× H100 with a 1M-token context, zero agents fit. On a GB200 NVL72 rack, ~30 do. | Cost per agent-hour falls from $76 to $5.64 (Exhibit 8). |
| 5 | Hardware is the whole cost, written off over 4 years | Power, rack space and staff add ~$120K a year per H100 machine; a 3-year life is safer. | Machine-hour rises from $18.26 to $38.05. |
| 6 | `2X` means redundant hardware | Redefined in review as 2× compute for a model twice as capable. Likely low (Exhibit 11). | Halves agents per rack. |
| 7 | "+75% margin" | A 75% markup is a 42.9% margin. This memo applies a true 75% margin (cost × 4). | Price per hour is 2.3× the chat's. |
| 8 | "Top 15% earn $196K+, 262,500 people" | A $196K salary is near the top ~10–15% (BLS 90th percentile wage: $214,670); $196K loaded is a ~$145K wage. | The $51.45B figure is undefined. |
| 9 | Level split with L6 at $1.15M and L7 at $2.4M; total $387B | Invented. This memo uses a split that reconciles to BLS (~$346B), still an assumption. | Payroll overstated ~12%. |
| 10 | Agents per level = salary ÷ price | Circular: it restates payroll. This memo uses an assumed multiplier per level and shows the break-even (Exhibit 2). | Remove from any pitch. |
| 11 | Top 10 / top 20 industries, agent counts, $1.67T and $2.33T | No sources given; not traceable. | Remove. |
| 12 | 9.34M jobs lost; robotics 3.7M, later 8.72M | Unsourced and inconsistent within the chat. | Out of scope; remove. |
| 13 | Healthcare is 7.5% of GDP, later 23.7%; shadow economy 10–12% of GDP | The chat contradicts itself. | A thought experiment, not a forecast. |
| 14 | `($300K × 10,000 ÷ 43,800) × 90`, then "if $6.1M is 20%" | The 10,000 and 90 were never defined. | Ignore. |

*What survives checking: H100 purchase prices ($27K–40K) and rental ranges match October 2026 market data; BLS developer counts (1,717,800) and median wage ($135,980) are correct; Opus 5.5 API prices are correct.*

---

## Section 09 — Risk register

**The analytical question:** What can stall or break the rack-owning business, and what specifically prevents it?

**Exhibit 15 — Ranked exposures**

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| The open-weights model on the rack doesn't do Fable-class work, so buyers compare with cheaper models (~$9.46/agent-hour) | High | High | Benchmark candidate models on the buyer's own tasks before buying a rack; sell long-context work, where the rack's cost edge over the API is largest. |
| The real multiplier grows faster than doubling, or agents can't do senior work at all | High | High | Sell L1–L3 work only until the multiplier is measured per level in paid pilots. |
| Unsold rack slots | Medium | High | Sign anchor customers for ~25 agents before buying the first rack; rent cloud racks for overflow. |
| Hardware obsolescence (new GPU generation yearly) | High | Medium | 3-year write-off at most; lease rather than buy where possible. |
| Agents doing their own review ship a harmful change | Medium | High | Agents open pull requests only; CI gates; E&O and cyber cover; liability caps. |
| Rack supply (30–52 week lead times, deposits) | Medium | Medium | Order through a cloud or system partner with allocation. |

---

## Section 10 — Recommendation

**The analytical question:** Given all of it, what should this operator actually do?

Four findings converge:

1. **The per-level structure is right** (Section 01): machine-hour cost × 4, times agents per level, compared with each level's salary.
2. **The machine decides the cost** (Section 05): H100s can't serve a 1M-token agent at all; a GB200 NVL72 rack serves ~30 at $5.64 per agent-hour, so $46,961 per engineer-year of work at a true 75% margin.
3. **The multiplier decides the market** (Sections 01 and 07): with agents doubling per level, replacement pays at L1–L3 and loses from L4 up.
4. **The rack beats the API at long contexts** (Sections 05 and 07): a 1M-context agent-hour costs ~$72 on Fable 5.1's API and $22.58 from the rack with a 75% margin. The open question is whether the rack's model is as good.

> **Recommended structure and sequence**
>
> **Sell junior-to-senior (L1–L3) work, not senior replacement.** Use Exhibit 1 as the sales tool, with the GB200 column. Don't buy a rack first. Run 20–30 agents on rented rack capacity or the API as paid pilots on one narrow kind of work, and count accepted changes per agent against the engineers doing the same work. That measures the multiplier per level.
>
> Buy the first rack only when two things are true: signed demand for ~25 agents (the single-rack breakeven), and an open-weights model that does the work as well as the API models on the buyer's tasks. Then the rack's $5.64 agent-hour, against ~$72 on Fable's API at the same context, is a real cost edge, and there is room to price above $22.58.

> **What would change this recommendation**
>
> If the real multiplier grows more slowly than doubling (for example the linear 1, 1, 2, 3, 4, 6, 10), every level saves money and senior replacement becomes the bigger market. If the compute factor is 4X or more, the price doubles and only L1–L2 pay. If a top closed model becomes licensable for private racks, owning racks gets a stronger case.

### Metrics to run it on

- **Agent-years per engineer, measured per level** — accepted changes per agent-week vs. per engineer-week on the same work.
- **Agents per rack at 80 tok/s and 1M context** — measured, against the ~30 base case.
- **Rack fill rate** — against the ~83% single-rack breakeven.
- **Price per agent-hour vs. Fable's API** — the share of ~$72 buyers will pay, and the model quality gap.
- **Buyer saving per engineer replaced** (Exhibit 12 inputs, measured).

---

**ANALYTICAL BASIS** — Figures are directional estimates for an operator selling AI coding-agent capacity to US employers, built for structural analysis rather than as an audited forecast. Developer counts and the median wage are from the US Bureau of Labor Statistics (May 2025). Loaded cost per level and the share of developers at each level are assumptions, set so the level totals reconcile to BLS-based payroll (~$346B); BLS does not report engineer levels. Max's review set these inputs: 3-year write-off, $120K/yr running costs per 16× H100 machine, 2X compute for a future model twice as capable, a true 75% margin, a 1.2 TB model, a 1M-token context, 80 tokens/s per agent, 24/7 use, agents doing their own review, and agents per level doubling from 1 to 64. GPU and rack specs are NVIDIA's published figures (H100 80 GB, 3.35 TB/s; GB200 NVL72 13.4 TB, 576 TB/s; GB300 NVL72 20.7 TB, 576 TB/s). Rack prices (~$3.4M GB200, ~$3.9M GB300) and running costs are press-reported or engineering estimates. Agents per rack (~30) is an estimate from memory bandwidth, real-world efficiency (~60%) and the compute factor, assuming ~10 GB of context memory per 100K tokens. H100 purchase ($27K–40K) and rental (~$3.50 median) prices and memory price changes are from October 2026 market surveys and TrendForce. The API benchmark uses Claude Fable 5.1 at $10 input / $50 output per million tokens (cached reads assumed at $0.50) with ~120 turns an hour, a full 1M-token context 95% cached and ~1.5K output tokens per turn, giving ~$72 per agent-hour; the Opus 5.5 reference ($4 / $20 / $0.20) uses a 100K context, giving ~$9.46. Claims from the source conversation are treated as hypotheses; Section 08 lists which were corrected.

**FRAMEWORKS APPLIED** — Hypothesis-first framing with explicit tests · Per-level substitution table with break-even multipliers · Hardware capacity model (memory, bandwidth, compute) · Market sizing from payroll by level (ceiling → theoretical agent revenue → vendor pool → SOM) · Porter's Five Forces · Value chain and margin pool · Cost-plus formula audit and build-vs-rent comparison · Two-variable sensitivities (price by agents per rack and compute factor; buyer saving by multiplier and level) · Adverse-case scenario · Source-claim error log · Risk register · Economic profit adjustment for owner labor and capital.
