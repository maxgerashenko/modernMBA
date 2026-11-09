# How Many Agents Make an Engineer

**Artifact:** https://claude.ai/artifact/W1kcyA5nYTzimgDhrULt36
**Notion:** https://app.notion.com/p/413ba21e32d4815980fdd79459e1d203?pvs=204

An MBA-style teardown of one pricing idea: work out what one machine running a top coding model costs per hour, add a 75% company margin, assume that some number of agents will one day equal one software engineer (more agents for more senior levels), and compare that bundle with each engineer level's salary. The memo states the hypotheses first, builds the per-level table, then corrects the inputs where the source conversation got them wrong.

**SUBJECT:** an operator selling AI coding-agent capacity to US employers, priced as (cost per agent-hour × 2,080 h × 2X redundancy) + 75% margin, with N agents sold per engineer replaced
**MARKET:** US software developers and QA testers, ~1.9M people (BLS, 2025), split into seven engineer levels (L1–L7)
**BASE CASE:** source formula = $132,968 per agent-year; corrected (Claude Opus 5.5 on the API, same 75% margin) = $34,400 per agent-year; 1 agent for an L1 up to 10 for an L7
**SOURCE:** a long chat with another AI assistant that built the formula `((1.28 TB / 80 GB × $40K) / (4Y × 8,760H)) × 2,080H × 2X + 75%M`. Its numbers are treated as claims to test, not as facts.

---

## Preface — Hypotheses, stated before the verdict

**The analytical question:** What has to be true for "N agents, priced at machine cost plus 75%, replace one engineer at every level" to be a good business — and is each of those things true?

The idea has one pricing rule and one capability assumption. The table names each piece, how it is tested, and the result. Everything after it is the evidence.

**Exhibit A — Hypotheses, tests, and results**

| # | Hypothesis | How it is tested | Result |
|---|---|---|---|
| H1 | One agent's year of work costs far less than one engineer. | Price an agent-year on Claude Opus 5.5 list prices ($4 in / $20 out / $0.20 cached per million tokens), and on a batched self-hosted cluster. | **Supported, strongly.** ~$19,700 of cost per agent-year on the API (~$34,400 with the 75% margin), ~$4,400 self-hosted at full batching, vs. $105,000–1.1M per engineer. |
| H2 | One machine (16× H100, $640K) runs one agent, so the agent-hour costs the machine-hour: $640K ÷ (4 yr × 8,760 h) = $18.26. | Rebuild the machine's real hourly cost and how many agents it serves. | **Rejected.** All-in (power, space, staff) the machine costs ~$32/hour, not $18.26. But it serves ~30 agents at once, so one agent-hour costs ~$1.07. The formula overcharges each agent by ~17× and undercounts the machine by ~43%. |
| H3 | Self-hosting the top model is possible and cheapest. | Check model availability; compare owned vs. rented GPU-hours. | **Rejected.** The top coding model (Claude Opus) is sold only as a service; it cannot run on owned hardware. Owned H100s cost ~$2.00/GPU-hour at full use vs. a $3.49 rental median. |
| H4 | A fixed number of agents equals one engineer, rising with level (1 for L1 … 10 for L7). | No data can confirm a future multiplier, so the memo inverts it: how many agents can each level's salary pay for before agents cost more? | **The deciding assumption, and untested.** At the source price, an L1 salary pays for 0.8 agents and an L7 for 8.3, so the bundle costs *more* than the engineer at most levels. At the corrected price, an L1 pays for 2.4 agents and an L7 for 31. Cost stops being the question; capability is. |
| H5 | Replacing all US developers moves ~$300B+. | Rebuild payroll by level from BLS totals. | **Supported as a ceiling.** ~$346B loaded payroll across 1.9M people. At the corrected price, the full agent bundle would cost ~$99B, of which ~$43B is the 75% margin. That is a theoretical maximum; a realistic vendor pool is ~$10–30B. |
| H6 | "+75% margin" means the company keeps 75%. | Check the arithmetic. | **Rejected as stated.** Cost × 1.75 is a 75% markup, which is a 42.9% gross margin (0.75 ÷ 1.75). The source chat used both definitions on the same totals. |

> **How the hypotheses resolve:** H1 is true and is why the idea is attractive. H2 and H3 mean the hardware-hour is the wrong cost base: the agent-hour is ~17× cheaper than the formula says, and the top model is rented, not owned. With the corrected cost, every level's salary covers several agents, so the whole case rests on H4, the number of agents it really takes to equal one engineer at each level. That number is a forecast, not a fact, and it sets both the buyer's savings and the operator's revenue.

---

## Section 00 — Executive summary

**The analytical question:** If one engineer at each level equals N agents priced at cost plus 75%, does the bundle beat the salary — and is there a business in selling it?

| KPI | Value | Note |
|---|---|---|
| Agent-year, source formula | $132,968 | one 16× H100 machine per agent, 4-yr life, 2,080 h, 2X, +75% |
| Agent-year, corrected (Opus 5.5 API +75%) | $34,400 | ~$19,700 of tokens and sandbox, ×1.75 |
| Agents an L5 ($480K) salary pays for | 3.6 vs. 13.3 | source price vs. corrected price |
| US dev payroll by level (ceiling) | ~$346B | 1.905M people, BLS 2025, level split assumed |
| Full agent bundle, all levels, corrected | ~$99B | ~$43B of it is the 75% margin |
| Operator economic profit | $1.01M | at 250 agents; breakeven ~181 agents at $34,400 |

> **Recommendation: Keep the per-level model, but price agents off the agent-hour on the API, not off a machine-hour you own. At that price every engineer level can afford several agents, so the business depends entirely on how many agents it really takes to replace each level, and that has to be measured before it is sold.**
>
> The model in the source chat has the right shape. Cost per agent-hour, plus a margin, times the agents needed to match one engineer, compared level by level with salary: that is the right way to price labor substitution. The problem is the input. The formula charges each agent for a whole 16-GPU machine, about $18 an hour. An inference machine runs about 30 agents at once, so the real hardware cost per agent-hour is about a dollar, and the top coding model can't run on owned hardware anyway. On the Opus 5.5 API, one agent working a 2,080-hour year costs about $19,700, or $34,400 with the 75% margin.
>
> At the source price ($132,968), the bundle costs more than the engineer at six of seven levels; it saves money only at L2 (Exhibit 1). At the corrected price, it costs 22–34% of the engineer at every level, and an L7 salary would cover 31 agents, not 10. So the per-level table now turns on one number: how many agents really equal one engineer at each level. That is a capability forecast, not a cost fact. The buyer and the operator both win only if it holds.
>
> As a business, selling agents at cost plus 75% clears a market return at ~181 agents and makes about $1M at 250. Margin is thin in dollars ($14,730 per agent-year) because a cost-plus price shrinks as model prices fall. An ordinary bad year — a rival's price cut plus token overruns — wipes out the profit (Exhibit 13).

---

## Section 01 — Market definition and capacity: agents per engineer level

**The analytical question:** For each engineer level, what does the agent bundle cost against the salary — and how large is the US opportunity once that is added up?

**Exhibit 1 — Agents per engineer vs. salary, by level**

| Level | Loaded cost / yr | Agents per engineer (assumed) | Bundle, source price | Saving | Bundle, corrected price | Saving |
|---|---|---|---|---|---|---|
| L1 Junior | $105,000 | 1 | $132,968 | ($27,968) | $34,400 | $70,600 |
| L2 Mid | $155,000 | 1 | $132,968 | $22,032 | $34,400 | $120,600 |
| L3 Senior | $215,000 | 2 | $265,936 | ($50,936) | $68,800 | $146,200 |
| L4 Staff | $300,000 | 3 | $398,904 | ($98,904) | $103,200 | $196,800 |
| L5 Principal | $480,000 | 4 | $531,872 | ($51,872) | $137,600 | $342,400 |
| L6 Distinguished | $700,000 | 6 | $797,808 | ($97,808) | $206,400 | $493,600 |
| L7 Fellow | $1,100,000 | 10 | $1,329,680 | ($229,680) | $344,000 | $756,000 |

*Loaded cost = total pay × employer taxes and benefits; directional, set so the level totals reconcile to BLS payroll (Exhibit 3). L5 uses the source chat's own $480K / 4-agent example. L6–L7 exist mostly at large tech firms. The agents-per-level column is the source idea's assumption, not a measurement. At the source price the bundle saves money only at L2.*

**Exhibit 2 — How many agents each salary can pay for (break-even multiplier)**

| Level | Loaded cost | Max agents, source price | Max agents, corrected price | Assumed agents |
|---|---|---|---|---|
| L1 Junior | $105,000 | 0.8 | 2.4 | 1 |
| L2 Mid | $155,000 | 1.2 | 3.9 | 1 |
| L3 Senior | $215,000 | 1.6 | 5.6 | 2 |
| L4 Staff | $300,000 | 2.3 | 8.1 | 3 |
| L5 Principal | $480,000 | 3.6 | 13.3 | 4 |
| L6 Distinguished | $700,000 | 5.3 | 19.7 | 6 |
| L7 Fellow | $1,100,000 | 8.3 | 31.4 | 10 |

*This is the more useful way to read the model: the multiplier is unknown, so ask how high it can go before replacement stops paying. At the corrected price there is room for 2.4–3.9× the assumed agents at every level. The corrected column first deducts ~$21,000 of review time (~4 h/week of a senior engineer per engineer replaced) is an assumption.*

### Adding it up across the US

**Exhibit 3 — US developers by level: payroll vs. agent bundle**

| Level | Share (assumed) | Headcount | Payroll | Agents needed | Bundle cost, source price | Bundle cost, corrected price |
|---|---|---|---|---|---|---|
| L1 Junior | 27% | 514,458 | $54.0B | 514,458 | $68.4B | $17.7B |
| L2 Mid | 40% | 762,160 | $118.1B | 762,160 | $101.3B | $26.2B |
| L3 Senior | 21% | 400,134 | $86.0B | 800,268 | $106.4B | $27.5B |
| L4 Staff | 8% | 152,432 | $45.7B | 457,296 | $60.8B | $15.7B |
| L5 Principal | 3% | 57,162 | $27.4B | 228,648 | $30.4B | $7.9B |
| L6 Distinguished | 0.8% | 15,243 | $10.7B | 91,459 | $12.2B | $3.1B |
| L7 Fellow | 0.2% | 3,811 | $4.2B | 38,108 | $5.1B | $1.3B |
| **Total** | **100%** | **1,905,400** | **$346.2B** | **2.89M** | **$384.6B** | **$99.5B** |

*Headcount total is BLS 2025 (1,717,800 software developers + 187,600 QA analysts and testers). The split by level is an assumption; BLS does not report levels. At the source price, replacing everyone costs more than the payroll it replaces. At the corrected price it costs 29% of it.*

**Exhibit 4 — Market funnel, payroll ceiling to SOM**

| Layer | Definition | Value |
|---|---|---|
| Payroll pool (ceiling) | All US developers and QA testers, loaded (Exhibit 3) | ~$346B / yr |
| Theoretical agent revenue | Every engineer replaced at the assumed multipliers, corrected price | ~$99B / yr (~$43B margin) |
| Realistic vendor pool (SAM) | 10–30% of that work automated within ~3 years — **assumption** | ~$10–30B / yr |
| SAM — this segment | Mid-market employers buying managed agents rather than self-serve tools (~20%) — **assumption** | ~$2–6B / yr |
| **SOM — 3 yr** | **250 agents × $34,400 — capped by distribution and trust, not compute or demand** | **$8.6M / yr** |

*Cross-check: paid AI coding tools are already a multi-billion-dollar category; Cursor alone passed $2B in annualized revenue in March 2026 (Bloomberg, TechCrunch).*

The capacity math that actually governs this business:

- **Compute is not the cap.** A year of one agent's tokens costs about 12% of an L2 engineer. Any operator can buy as many as it can sell.
- **The multiplier is the cap.** Every revenue figure above assumes the agents-per-level column in Exhibit 1. Until that is measured on real codebases, the market is a forecast.
- **Distribution is the second cap.** Each sale goes to an engineering manager who has to trust agents with a codebase and set up review, against tools the team already has (Claude Code, Cursor, GitHub Copilot).

---

## Section 02 — Industry structure (Five Forces)

**The analytical question:** What return does an agent-capacity operator earn, structurally, before any firm-specific advantage?

**Exhibit 5 — Force assessment**

| Force | Rating | Evidence |
|---|---|---|
| Supplier power (model labs, GPU vendors, clouds) | Very high | The top coding models come from a few labs, and Claude Opus is sold only as a service (Anthropic API, AWS, Google Cloud, Microsoft Foundry). The lab sets the input price; Opus 5.5 lists at $4 / $20 per million tokens, 20% below Opus 5. |
| Buyer power (engineering managers, CTOs) | High | Buyers can measure output directly (merged pull requests, tickets closed), can cancel monthly, and already pay $20–200 per developer per month for agent tools. |
| Threat of new entry | Very high | The same API is open to everyone. A competing service needs no capital, only an orchestration layer. |
| Substitutes | Very high | Claude Code, Cursor, GitHub Copilot and similar tools used by the buyer's own staff; offshore contractors; hiring. |
| Rivalry | Very high | Model labs sell agents directly, so the supplier is also a competitor. |

*Five of five forces unfavorable. Falling compute prices help every competitor equally, and they push a cost-plus price down every model generation.*

---

## Section 03 — Value chain and margin pool

**The analytical question:** Of what a buyer pays for one agent-year, who takes what — and who carries the risk?

**Exhibit 6 — Value extracted per agent-year, $34,400 price**

| Participant | Take | Risk carried |
|---|---|---|
| Model lab (Opus 5.5 tokens, 2,080 h × ~$8.88) | $18,470 | None. Billed per token whether or not the code is accepted. |
| Cloud sandbox, CI runners, tooling | $1,200 | None. Metered. |
| **The operator (75% markup)** | **$14,730** | **Token overruns on a fixed price, uptime, onboarding each codebase, liability when an agent ships a bad change.** |
| Buyer replacing one L3 with 2 agents | Saves $146,200 vs. a $215,000 engineer | Pays $68,800 plus ~$21,000 of review time; carries code-quality and security risk. Saving holds only if 2 agents really do an L3's work. |

> **Where the 75% margin went:** Cost × 1.75 is a 75% markup, which is a 42.9% gross margin. The source chat applied both meanings to the same $51.45B (once $22.05B of margin with $29.40B of compute, once $38.59B with $12.86B), and labeled a $300B pool as 43% compute and 57% margin, which reverses the split. At a 75% markup, any price is 57% cost and 43% margin.

---

## Section 04 — Domain-specific structural factors

**The analytical question:** What does the AI-model and US-employment landscape do to this model that a generic plan would miss?

**Exhibit 7 — Structural factors and their transmission**

| Factor | Effect | Mechanism |
|---|---|---|
| Closed model weights | Decisive against owning the machine | Claude Opus is sold only as a service. Running "Opus 5.5 at 4-bit on Mac Studios or DGX Sparks," as the source chat suggested, is not possible. Owned hardware can only run open-weights models, which have generally trailed the top models on long agentic coding work. |
| Model size and memory are not public | The 1.28 TB sizing is a guess | Anthropic does not publish parameter counts or memory footprints. The chat's "~600 GB," "350–400 GB at 4-bit" and "1.2 TB with context" are estimates for open models, stated as fact. |
| Batching | One machine serves many agents | Inference servers run many conversations at once. A 16× H100 machine with ~280 GB left after model weights holds roughly 30–40 long-context agent sessions. Charging one agent for the whole machine is the formula's largest error. |
| Token prices fall each model generation | Cost-plus prices ratchet down | Opus 5.5 lists 20% below Opus 5. A price set as cost × 1.75 falls with it; a price set on the buyer's saving does not. |
| Hardware economic life is 2–4 years | Faster write-downs if hardware is owned | Hyperscalers depreciate GPUs over 5–6 years, but NVIDIA now ships a new architecture roughly yearly. The chat's own 2-year case doubles the source price to $265,936. |
| Layoffs and the WARN Act | Slows "replacement" sales | Replacing staff at scale triggers 60-day notice duties for employers with 100+ workers. Buyers more often redirect hiring budgets than cut people, which lengthens the sale. |
| Copyright of AI-generated code | Contract issue for buyers | The US Copyright Office's position is that protection requires human authorship. Buyers will want IP warranties an operator must stand behind. |

---

## Section 05 — Unit economics: the agent-hour

**The analytical question:** What does one agent-hour really cost, and what does the choice of machine change?

### The cost base, isolated

**Exhibit 8 — One agent-year (2,080 h, ×2 redundancy where hardware is owned, +75%)**

| Cost base | Cost per agent-hour | Agent-year price | Note |
|---|---|---|---|
| Source formula: 1 machine per agent, hardware only | $18.26 | $132,968 | $640K ÷ (4 yr × 8,760 h); no power, space or staff |
| 1 machine per agent, fully costed | $31.96 | $232,654 | + ~$23K power, ~$37K colocation, ~$60K operations per year |
| Owned machine shared by ~30 agents, fully costed | $1.07 | $7,755 | Same hardware, batched; runs an open-weights model, not Opus |
| **Claude Opus 5.5 API (base case)** | **$8.88 + sandbox** | **$34,400** | ~120 turns/h, ~100K-token context 95% cached, ~1.5K output tokens per turn; no 2X needed |

*Per GPU-hour, the owned machine costs ~$2.00 at 100% use and ~$4.00 at 50%, against an October 2026 rental median of $3.49 and a floor of $1.70. The cheapest line runs a weaker model; the base case uses the top model at about 4× the cost. Either is a small fraction of any engineer level.*

**Exhibit 9 — Per-agent P&L, annual (API base case)**

| Line | Amount | Note |
|---|---|---|
| Agent-year price | $34,400 | (tokens + sandbox) × 1.75 |
| Opus 5.5 tokens | ($18,470) | $8.88/agent-hour × 2,080 h |
| Sandbox, CI, tooling | ($1,200) | |
| **Gross margin / agent** | **$14,730** | **42.8%** |

*The token estimate is the line most likely to be wrong. Light agentic use runs ~$3–4/hour; heavy use with large uncached contexts or fast mode ($8 / $40 per million tokens) runs $15–25/hour (Exhibit 11).*

---

## Section 06 — Annual operating model

**The analytical question:** How many agents does the operator have to sell to pay a team and the founder at market?

**Exhibit 10 — Annual P&L at 250 agents (steady state, year 3)**

| Line | Annual | Per agent |
|---|---|---|
| Revenue — 250 agents × $34,400 | $8,600,000 | $34,400 |
| Model tokens | ($4,617,500) | ($18,470) |
| Sandbox, CI, tooling | ($300,000) | ($1,200) |
| **Gross margin** | **$3,682,500** | **$14,730** |
| Engineering & on-call (4 × $230K loaded) | ($920,000) | — |
| Sales & customer success (3 × $200K loaded) | ($600,000) | — |
| Marketing / paid acquisition | ($500,000) | — |
| G&A, E&O and cyber insurance, legal | ($350,000) | — |
| **Profit before owner compensation** | **$1,312,500** | — |
| Owner compensation at market | ($300,000) | — |
| **Economic profit** | **$1,012,500** | — |

*Breakeven after paying the founder at market is ~181 agents — for example, 45 L5 principals at 4 agents each. 250 agents is about 125 L3 seniors replaced at 2 agents each.*

For comparison, running the same 250 agents on owned hardware with the source formula's one-machine-per-agent rule would need 500 machines (with 2X) and ~$320M of GPUs. Batched at 30 agents per machine, it needs ~18 machines (~$11.5M), runs a weaker model, and saves little against the API.

---

## Section 07 — Sensitivity analysis

**The analytical question:** Which matters more — what an agent-hour costs, what the agent sells for, or how many agents it takes to equal an engineer?

**Exhibit 11 — Operator gross margin per agent, by token cost and agent-year price**

| Token cost per agent-hour | $24,000 | $34,400 (base) | $48,000 | $60,000 |
|---|---|---|---|---|
| $4 (light use) | $14,480 | $24,880 | $38,480 | $50,480 |
| **$8.88 (base)** | $4,330 | **$14,730** | $28,330 | $40,330 |
| $15 (heavy) | ($8,400) | $2,000 | $15,600 | $27,600 |
| $25 (very heavy / fast mode) | ($29,200) | ($18,800) | ($5,200) | $6,800 |

*2,080 agent-hours per year; $1,200 sandbox cost per agent. A fixed agent price leaves the operator holding the token risk.*

**Exhibit 12 — Buyer's saving per engineer replaced, by agents needed and engineer level (corrected price)**

| Agents needed per engineer | L2 Mid ($155K) | L3 Senior ($215K) | L5 Principal ($480K) | L7 Fellow ($1.1M) |
|---|---|---|---|---|
| 1 | $99,600 | $159,600 | $424,600 | $1,044,600 |
| 2 | $65,200 | $125,200 | $390,200 | $1,010,200 |
| 4 | ($3,600) | $56,400 | $321,400 | $941,400 |
| 8 | ($141,200) | ($81,200) | $183,800 | $803,800 |
| 16 | ($416,400) | ($356,400) | ($91,400) | $528,600 |

*Saving = loaded cost − agents × $34,400 − ~$21,000 review time. The multiplier swings the outcome far more than price or token cost: it moves an L3 from +$160K to −$356K. That is why it has to be measured per level before any of this is sold.*

### The scenario the grids do not show

An ordinary bad year at the 250-agent base case:

**Exhibit 13 — Adverse case, nothing exotic**

| Event | Impact | Comment |
|---|---|---|
| Base case economic profit (Exhibit 10) | $1,012,500 | |
| A model lab or funded rival bundles agents; price cut 15% to $29,240 | ($1,290,000) | The supplier is also a competitor |
| Token use runs 30% over plan (longer contexts, retries, harder repos) | ($1,385,250) | Fixed price; operator absorbs it |
| 15% of agents cancelled mid-year after weak acceptance | ($276,188) | Lost half-year gross margin |
| One agent-caused production incident: credits, legal | ($150,000) | |
| **Adverse case economic profit** | **($2,088,938)** | |

*Any two of these together wipe out the year. There are no fixed assets to lose, which is good, and no pricing power, which is the problem with cost-plus pricing on someone else's model.*

---

## Section 08 — What the source conversation got wrong

**The analytical question:** Which claims in the source chat survive checking, and which should be dropped from any pitch built on it?

**Exhibit 14 — Error log**

| # | Claim in the source chat | What is actually true | Effect on the case |
|---|---|---|---|
| 1 | Opus 5.5 needs ~600 GB unquantized, 350–400 GB at 4-bit, 1.2 TB with full context | Anthropic does not publish model size. These are estimates for open models, stated as fact. Opus cannot be self-hosted at any precision. | The machine sizing (16× H100) is a guess for an open model. |
| 2 | Anthropic serves Claude on "over 1 million Trainium2 chips" and Inferentia2 handles API traffic | Anthropic says it runs Claude on AWS Trainium, Google TPUs and NVIDIA GPUs; Amazon announced a ~1M Trainium2 plan. Which chip serves which request is not public. | Irrelevant to the business; do not cite. |
| 3 | Opus 5.5 is "40% cheaper and 30% faster" and included in a $20 plan | Not verifiable. Published API list price is $4 / $20 per million tokens, 20% below Opus 5. | Use list prices only. |
| 4 | Machine cost ÷ 8,760 h is the agent-hour cost | One inference machine serves ~30–40 long-context agents at once. | Agent-hour overstated ~17× (Exhibit 8). |
| 5 | Hardware is the whole cost | Power, colocation and operations add ~75% to depreciation for this machine. | Machine-hour understated ~43%. |
| 6 | `2X` redundancy doubles all hardware | Standard practice is N+1 spare capacity, not a full mirror; on the API it does not apply. | Doubles the source price. |
| 7 | "+75% margin" | A 75% markup is a 42.9% margin; the chat mixed the two and reversed the split on $300B. | Margin overstated up to 1.75×. |
| 8 | "Top 15% earn $196K+, 262,500 people" | A $196K loaded cost is a ~$145K wage, roughly the top ~45%. A $196K salary is near the top ~10–15% (BLS 90th percentile wage: $214,670). | The $51.45B figure is undefined. |
| 9 | Level split 25/40/20/10/4/0.8/0.2% with L6 at $1.15M and L7 at $2.4M; total $387B | Invented. L6–L7 pay at that level exists at a few large tech firms. This memo uses a split that reconciles to BLS (~$346B), still an assumption. | Payroll overstated ~12%. |
| 10 | Agents per level = salary ÷ $132,968 (2.9M agents, $387B) | Circular: it restates payroll and says nothing about capability. This memo keeps an assumed multiplier per level and shows the break-even multiplier instead (Exhibit 2). | Remove from any pitch. |
| 11 | Top 10 / top 20 industries, agent counts, $1.67T and $2.33T | No sources given; numbers not traceable. | Remove. |
| 12 | 9.34M jobs lost; robotics 3.7M, later 8.72M | Unsourced and inconsistent within the chat. | Out of scope; remove. |
| 13 | Healthcare is 7.5% of GDP, later 23.7%; shadow economy 10–12% of GDP | The chat contradicts itself on healthcare. Shadow-economy estimates vary by method and are usually lower for the US. | Macro section is a thought experiment, not a forecast. |
| 14 | `($300K × 10,000 ÷ 43,800) × 90`, then "if $6.1M is 20%" | The 10,000 and 90 were never defined; the arithmetic is right but measures nothing. | Ignore. |

*What survives checking: H100 purchase and rental ranges match October 2026 market data; BLS developer counts (1,717,800) and median wage ($135,980) are correct; Opus 5.5 API prices are correct; each individual formula evaluation is arithmetically right. The errors are in what the formulas assume.*

---

## Section 09 — Risk register

**The analytical question:** What can stall or break the corrected business, and what specifically prevents it?

**Exhibit 15 — Ranked exposures**

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| The real agents-per-engineer multiplier is higher than assumed | High | High | Measure it per level in paid pilots (accepted changes per agent vs. per engineer) before quoting a replacement price; price per accepted change until it is known. |
| Model labs or funded coding-agent companies sell equivalent agents directly | High | High | Specialize where general tools are weakest (legacy migrations, test backfill, dependency upgrades) with your own evaluation and review workflow. |
| Token use above plan on a fixed price | High | High | Price with a token allowance and overage, or per accepted change; track cost per merged change weekly. |
| Agent ships a harmful change to production | Medium | High | Agents open pull requests only; human review and CI gates are mandatory; E&O and cyber cover; liability caps. |
| Model price cuts shrink a cost-plus price | High | Medium | Move from cost-plus to value pricing (share of the saving in Exhibit 12) once the multiplier is measured. |
| Buyer IP and data requirements (SOC 2, on-premises) | Medium | Medium | SOC 2 early; offer private-cloud deployment through AWS, Google Cloud or Microsoft rather than owned hardware. |

---

## Section 10 — Recommendation

**The analytical question:** Given all of it, what should this operator actually do?

Four findings converge:

1. **The per-level structure is right** (Section 01): agent cost × agents per level, compared with each level's salary, is the correct way to price labor substitution.
2. **The cost input was ~4× too high** (Section 05): price the agent-hour on the API ($34,400 per agent-year with the 75% margin), not as a whole machine per agent ($132,968). At the source price the bundle loses to the engineer at six of seven levels; at the corrected price it wins at all seven.
3. **The multiplier decides everything** (Sections 01 and 07): each salary covers 2.4–3.9× the assumed agents, but if the real multiplier is higher than that, the saving disappears.
4. **Cost-plus pricing leaves the operator thin and exposed** (Sections 02 and 06): $14,730 per agent-year, breakeven ~181 agents, and an ordinary bad year erases the profit.

> **Recommended structure and sequence**
>
> **Keep the per-level table as the sales tool; change its inputs.** Price agents on the API agent-hour plus 75% ($34,400 per agent-year), drop the owned machine and the 2X mirror, and show buyers Exhibit 2 (how many agents each level's salary can pay for) next to the assumed multiplier.
>
> Then measure the multiplier before selling replacement. Run 20–30 agents as paid pilots on one narrow kind of work and count accepted changes per agent against the engineers doing the same work. Once the real multiplier per level is known, move from cost-plus to a price that shares the buyer's saving: that is where the operator's margin can grow instead of shrinking with every model price cut. Target ~181 agents as the floor for paying a team and the founder, and 250+ for a real outcome.

> **What would change this recommendation**
>
> If open-weights models match the top models on long agentic coding and a buyer group requires fully on-premises deployment, owned hardware gets a real niche, priced at the batched agent-hour (~$1.07), not the machine-hour. If measured multipliers come in at or below the assumed column, value pricing could support 2–3× the cost-plus price. If measured multipliers come in above the break-even column (Exhibit 2), replacement doesn't pay at that level, and the product becomes extra capacity rather than replacement.

### Metrics to run it on

- **Agents per engineer, measured per level** — accepted changes per agent-week vs. per engineer-week on the same work.
- **Token cost per accepted change** — weekly, against the $8.88/agent-hour base case.
- **Buyer saving per engineer replaced** (Exhibit 12 inputs, measured) — if negative for a customer, that account will churn.
- **Gross margin per agent** — target ≥40% after tokens and sandbox.
- **Agents under contract vs. the 181-agent floor.**

---

**ANALYTICAL BASIS** — Figures are directional estimates for an operator selling AI coding-agent capacity to US employers, built for structural analysis rather than as an audited forecast. Developer counts and the median wage are from the US Bureau of Labor Statistics (May 2025). Loaded cost per level and the share of developers at each level are assumptions, set so the level totals reconcile to BLS-based payroll (~$346B); BLS does not report engineer levels. The agents-per-level multipliers (1, 1, 2, 3, 4, 6, 10) are the source idea's assumption about future capability, not a measurement. Model prices are Anthropic's published API list prices for Claude Opus 5.5 ($4 input / $20 output / $0.20 cached input per million tokens; fast mode $8 / $40). The per-hour token profile (~120 turns, ~100K-token context 95% cached, ~1.5K output tokens per turn) is an assumption and the most uncertain cost input. H100 rental prices are from an October 2026 survey of 45 providers ($1.70 floor, $3.49 median); purchase price uses the source chat's $40K/GPU. Machine opex (power at $0.10/kWh, colocation at $150/kW-month, ~$60K/yr operations) and batching capacity (~30 long-context agents per 16× H100 machine) are engineering estimates. Claims from the source conversation are treated as hypotheses; Section 08 lists which were corrected.

**FRAMEWORKS APPLIED** — Hypothesis-first framing with explicit tests · Per-level substitution table with break-even multipliers · Market sizing from payroll by level (ceiling → theoretical agent revenue → vendor pool → SOM) · Porter's Five Forces · Value chain and margin pool · Cost-plus formula audit and build-vs-rent decomposition · Two-variable sensitivities (operator margin; buyer saving by multiplier and level) · Adverse-case scenario · Source-claim error log · Risk register · Economic profit adjustment for owner labor.
