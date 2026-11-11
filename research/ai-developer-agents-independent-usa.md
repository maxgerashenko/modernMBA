# The Agent Costs $4 an Hour. The Reviewer Is the Bill.

**Artifact:** https://claude.ai/artifact/4KQNgXTwrTvG2ZugrBYvtD
**Notion:** https://app.notion.com/p/414ba21e32d4811a93a6ddbfa855e5be?pvs=204

An independent MBA-style teardown of a business that replaces US software engineers with AI coding agents, priced as compute plus margin and compared level by level (L1 junior to L7 fellow) with fully loaded salaries. The finding: the compute to do an L1's work costs about $4,500 a year, the human who must check that work costs five times as much, and above L3 no number of agents closes the gap.

**SUBJECT:** a new, venture-funded operator selling "agent engineers" to US employers, renting model capacity by the token
**MARKET:** US software developers (BLS SOC 15-1252), 1.69M jobs, about $397B of loaded payroll
**BASE CASE:** 300 L1–L2 bundles in year 3, $22.8M revenue, 50% gross margin, API tokens rather than owned GPUs

*Every number below is a directional estimate dated 10 November 2026. Inputs marked (A) are this memo's own assumptions, not sourced facts.*

---

## Preface — Hypotheses

**Exhibit 0 — What the idea assumes, and what the numbers say**

| # | Hypothesis | How it is tested | Result |
|---|---|---|---|
| H1 | The compute to replace one L1 costs a small fraction of the L1's loaded salary. | Token-level cost of one agent-hour × agent-hours needed for an L1's yearly output (Section 05). | **Confirmed.** About $4,450 a year, 3.5% of a $128K loaded L1. |
| H2 | Senior levels just need more agents; the count rises steadily with level. | Success-rate model built on measured agent time horizons (METR), applied to typical task length per level (Section 01, 04). | **Rejected.** The count is flat for L1–L3 (under 1 agent-year), 2.6 at L4, about 100 at L5, and has no finite value at L6–L7. It is a cliff, not a slope. |
| H3 | Compute cost plus a margin is a sellable product. | Compare with what the model labs and Cognition already charge direct (Section 02, 05). | **Rejected.** Agent time already sells direct at roughly $8–9 an hour. A margin on $4,450 is too small to fund a company and too easy to undercut. |
| H4 | The real cost of replacement is compute. | Full bundle cost including the human who specifies and reviews the work (Section 03, 05). | **Rejected.** Supervision is 79% of the L1 bundle's cost; compute is 15%. |
| H5 | Replacement pays at every level if enough agents are used. | Bundle price vs. loaded cost at each level (Section 01). | **Rejected.** It pays at L1 and L2, is marginal at L3, and loses money from L4 up. |
| H6 | Owning GPUs beats renting GPUs or buying tokens. | Three-way cost comparison at year-3 volume (Section 05). | **Rejected at this scale.** Owning saves about 2% of revenue and risks more than that in lost output quality. |
| H7 | The US market is large enough for a new operator. | Payroll ceiling → revenue pool → managed-service share → supervisor-bound capacity (Section 01). | **Partly confirmed.** $397B payroll, about $3.1B SAM, about $23M SOM. Demand is not the limit; reviewers are. |
| H8 | The operator earns an economic profit by year 3. | Year-3 P&L with founders paid at market and a charge for capital (Section 06). | **Not at base case.** +$1.2M operating profit, −$1.8M economic profit. |

---

## Section 00 — Executive summary

**The analytical question:** Can a new company make money replacing US software engineers with AI agents priced as compute plus margin, and at which levels does the swap actually save the customer money?

| KPI | Value | Note |
|---|---|---|
| Cost of one agent-hour | ~$4.05 | Mid-tier frontier model via API with 20% escalation to a stronger model, plus sandbox. (A) on token profile |
| Compute to replace one L1 | ~$4,450/yr | 0.55 agent-years (1,100 active hours). 3.5% of loaded cost |
| Full cost to replace one L1 | ~$30,000/yr | Compute + 1/12 of a supervising senior engineer + platform |
| Price of the L1 bundle | ~$60,100/yr | At a 50% gross margin; customer saves ~$68K (53%) |
| Levels where replacement pays | L1, L2 (L3 marginal) | 64% of headcount, 49% of payroll |
| US payroll ceiling (TAM) | ~$397B | 1.69M developers × ~$235K average loaded cost |
| SAM / 3-year SOM | ~$3.1B / ~$23M | SOM = 300 bundles, capped by ~33 supervising engineers |
| Year-3 revenue / economic profit | $22.8M / −$1.8M | After market pay for founders and a 25% charge on $12M capital |
| Five Forces | 5 of 5 unfavorable | Suppliers sell the same product direct |

> **Recommendation: Do not build the seven-level "replace your engineers" business; if you build anything, build a narrow supervised service that does L1–L2 work for companies without their own senior reviewers, and accept that it is a staffing business, not a compute business.**
>
> The pricing idea in the brief works on paper for the bottom of the ladder. One agent-hour costs about $4. Doing a junior developer's yearly output takes about 1,100 agent-hours, so about $4,450 of compute against $128,000 of loaded salary. If compute were the whole story the saving would be 96%.
>
> It is not the whole story, for two reasons. First, somebody has to write the task, read the result, and answer for it when it breaks. That person is a senior engineer, and one of them can cover about twelve L1-equivalents of agent output. That adds $23,600 per L1 replaced, five times the compute. Second, the model labs and Cognition already sell agent time direct at about twice compute cost. A customer with its own senior engineers can do the swap itself for about $33,000 and has no reason to pay an operator $60,000.
>
> The idea that senior levels simply need more agents does not hold. Agents fail more often as tasks get longer, and the failure rate compounds. On this memo's model an L4 takes 2.6 agent-years and so much checking that the bundle costs the same as the L4. An L5 would take about 100 agent-years. L6 and L7 have no finite answer. Above L3, agents make the engineer more productive; they do not remove the engineer.
>
> What is left is a real but modest business: about $23M of revenue in year 3 at a 50% gross margin, limited by how many senior engineers the operator can hire to review agent output all day. It makes an accounting profit and misses its cost of capital. The agent horizon is doubling about every four months, which moves the cliff up a level roughly every 18 months, but it moves for every competitor at the same time, including the suppliers.

---

## Section 01 — Market definition and capacity

**The analytical question:** What does it cost in agents to replace each level, how big is the US market at those prices, and what actually limits one operator?

### Definitions used throughout

- **One agent (A):** one autonomous coding session with its own sandbox VM, running a frontier model through an API with a 1M-token context window, of which about 120K tokens are in active use on average. It makes about 60 model calls an hour and writes about 90K output tokens an hour (model speed about 70–100 tokens a second; the rest of the hour is tool calls, builds and tests).
- **One agent-year (A):** 2,000 active agent-hours. An agent can run around the clock, but API billing only charges active hours, so capacity is counted in active hours, not seats.
- **Loaded cost (A):** base salary × 1.4 (benefits, payroll tax, equipment, space, recruiting; BLS puts benefits at 30% of private-sector compensation) plus bonus and equity. Base salaries are anchored on BLS May 2025 percentiles for software developers (10th $82K, median $136K, 90th $215K, mean $148K).
- **Agent-hours needed (A):** hands-on hours of the human ÷ agent speed-up × expected attempts × 2.5 overhead (tests, a reviewing agent, rebuilding context each task) + 400 hours of duties (triage, CI, questions).
- **Expected attempts:** 1 ÷ success rate, where success rate = 0.8 ^ (task length ÷ 8 hours). The 8-hour figure is this memo's estimate (A) of the task length today's best agents finish 80% of the time, extrapolated from METR's measured ~3 hours in April 2026 at a ~129-day doubling time.

**Exhibit 1 — Replacement cost by level**

| Level | Share of jobs (A) | Loaded cost | Typical task length (A) | Agent success rate | Agents needed (agent-years) | Supervision (A) | Bundle cost to operator | Bundle price (50% margin) | Saving to customer |
|---|---|---|---|---|---|---|---|---|---|
| L1 Junior | 12% | $128K | 4 h | 89% | 0.55 | 1/12 of an L4 | $30.0K | $60.1K | **+$68K (53%)** |
| L2 Developer | 22% | $164K | 8 h | 80% | 0.67 | 1/8 of an L4 | $43.3K | $86.6K | **+$77K (47%)** |
| L3 Experienced | 30% | $210K | 20 h | 57% | 0.93 | 1/4 of an L4 | $83.5K | $167.0K | +$43K (21%), marginal |
| L4 Senior | 24% | $283K | 60 h | 19% | 2.6 | 0.6 of an L5 | $283K | $566K | **−$283K** |
| L5 Staff | 9% | $389K | 200 h | 0.4% | ~100 | a full L6 | >$2.8M compute alone | n/a | Does not pay |
| L6 Principal | 2.5% | $536K | 600 h | ~0% | no finite number | n/a | n/a | n/a | Does not pay |
| L7 Fellow | 0.5% | $920K | 2,000 h | ~0% | no finite number | n/a | n/a | n/a | Does not pay |

*Replacement pays at L1 and L2. L3 pays the customer 21%, which is thin against the risk of handing over a codebase. At L4 the bundle costs the operator exactly what the engineer costs, before any margin. The step from L3 to L4 is where a typical task (about a week and a half of work) becomes several times longer than what an agent finishes reliably, so most attempts fail and a senior human has to find out which ones.*

**The answer to question 1:** one L1 takes about **0.55 agent-years** (1,100 active hours). In practice that is one agent seat running a little over half the working year. It costs the operator about **$4,450 in compute and $30,000 all-in**, and sells for about **$60,000**.

**Exhibit 2 — Market funnel, payroll to SOM**

| Layer | Definition | Seats | Dollars |
|---|---|---|---|
| TAM — payroll ceiling | All US software developers at loaded cost (BLS: 1,687,890 jobs) | 1.69M | ~$397B |
| Payroll where replacement pays | L1–L3 only | 1.08M | ~$193B |
| Same seats at bundle prices | What those seats would generate as agent revenue if all converted | 1.08M | ~$129B |
| Displaced within 3 years (A) | 25% of L1 and L2 seats, 5% of L3 seats, at bundle prices | ~169K | ~$15.3B |
| **SAM — managed service** (A) | The 20% of that displacement bought as an outside supervised service rather than done in-house with tools | ~34K | **~$3.1B** |
| **SOM — year 3** | **Capacity-bound: what ~33 supervising engineers can cover** | **300** | **~$22.8M (0.7% of SAM)** |

*The worldwide AI coding tools market is reported at about $12.8B for 2026, with Cursor above $2B of annualized revenue, Claude Code around $2.5B early in the year, and Cognition at $492M in May. A $3.1B US pool for outsourced, supervised agent labor is consistent with those figures. The 80% that is not in the SAM is customers buying the tools and supervising agents with their own staff.*

What actually caps this operator:

- **Supervising engineers.** Each L1-equivalent produces roughly 150–200 pull requests a year. Twelve of them is about ten a day, each needing a written task and a real review. That is a full day for one senior engineer. 300 bundles need about 33 such people, and the job (reviewing machine output all day) is hard to hire and keep for.
- **Customer access.** Each customer must grant agents access to its code, build systems and credentials. That means a security review and a sales cycle of months, not a self-serve signup.
- **Not compute.** The whole year-3 business uses about 373,000 agent-hours, an average of 43 agents running at once. Rate limits are a nuisance, not a ceiling.
- **Not demand.** Junior hiring was already falling before this business exists: the Stanford/ADP study found employment of 22–25 year olds in the most AI-exposed jobs down about 20% from peak.

---

## Section 02 — Industry structure (Five Forces)

**The analytical question:** What return does a company in this position earn before any advantage of its own?

**Exhibit 3 — Force assessment**

| Force | Rating | Evidence |
|---|---|---|
| Supplier power (model labs) | Very high | The best coding models come from two or three labs, and each sells its own agent product direct (Claude Code, Codex). The supplier sets the operator's input price and is also its largest competitor. |
| Buyer power | High | Buyers are engineering leaders who can test the tools themselves in an afternoon and who know the compute cost. Contracts are short and switching back to in-house tools costs nothing. |
| Threat of new entry | Very high | No capital barrier: the product is an API key, a sandbox and an orchestration layer. Every IT services firm and staffing agency can add an "agent pod" offering. |
| Substitutes | Very high | Do it in-house with Cursor, Claude Code or Devin; send the work offshore at roughly $45–60K a seat (A); or simply stop hiring juniors and give seniors agents. |
| Rivalry | Very high | Cognition raised over $1B at a $26B valuation and prices agent work at $2.00–2.25 per unit, an implied $8–9 an hour. Cursor is reported in funding talks at $50–60B. |

*Five of five forces are unfavorable. The single favorable fact, that compute is cheap and getting cheaper, helps every competitor equally.*

---

## Section 03 — Value chain and margin pool

**The analytical question:** When a customer swaps one $128K L1 for an agent bundle, who gets the money and who carries the risk?

**Exhibit 4 — Where the $128,200 goes after replacing one L1**

| Participant | Take | Share | Risk carried |
|---|---|---|---|
| Customer (saving kept) | $68,100 | 53% | Keeps production risk: outages, security holes and bad code still land on its systems and its name. |
| Supervising engineer (operator's employee) | $23,600 | 18% | None financially. Paid a salary whatever the agents produce. |
| Operator — sales, R&D and overhead | ~$26,800 | 21% | Fixed costs that must be paid whether or not customers renew. |
| Model lab (tokens) | ~$4,100 | 3% | None. Billed per token whether the agent's attempt succeeded or failed. |
| Sandbox and cloud | ~$350 | <1% | None. Metered. |
| Platform, security tooling, insurance | $2,000 | 2% | Insurer carries a capped slice of liability. |
| **Operator — net margin** | **~$3,200** | **~2.5%** | **Carries delivery, the customer relationship, data-security liability and the contract promise that the work is correct.** |

*The customer takes more than half the value. Of what the customer pays ($60,100), the operator keeps about 5% after its own costs. The largest cost in the chain is not the AI. It is the human who checks the AI. The lab collects 3% and carries no risk, which is why it can afford to sell direct.*

---

## Section 04 — Domain-specific structural factors

**The analytical question:** What is particular to AI agents and to US software work that a generic outsourcing analysis would miss?

**Exhibit 5 — Structural factors and how they act on the model**

| Factor | Effect | Mechanism |
|---|---|---|
| Failure compounds with task length | Sets the level cliff | METR measures agents by the length of task they finish 50% or 80% of the time. In April 2026 the best measured model finished ~17-hour tasks half the time but only ~3-hour tasks 80% of the time. Reliability, not peak ability, decides whether work can be handed over without checking. |
| Horizon doubling every ~129 days | The cliff moves, for everyone | Each doubling roughly halves the failure exponent. On this memo's model L4 becomes replaceable at about a 32-hour horizon, two doublings away (see Section 08). The operator does not own that improvement. |
| API billing charges only active time | Favors renting | An owned GPU costs money while idle. Tokens do not. Agents that wait on human review most of the day are cheap on an API and expensive on owned hardware. |
| Prompt caching | Makes long context affordable | An agent re-reads its whole context on every call. At Sonnet 5.5 rates a cached token costs $0.10 per million against $2.00 uncached. Without caching the agent-hour would cost about $15, not $3. |
| No memory between tasks | Hidden overhead | Each task starts by re-reading the codebase. This is why the model adds a 2.5× overhead and why agent-hours do not fall as far as raw speed suggests. |
| Accountability cannot be delegated to software | Keeps a human in every bundle | Someone must approve a merge and answer for an outage. Regulated buyers (banks, health, government) require a named person. This is the structural reason supervision never goes to zero. |
| Ownership of AI-written code | Contract friction | US copyright protection for purely machine-written work is uncertain. Enterprise buyers ask for indemnities, which the operator must insure or decline. Not legal advice. |
| Where developers work | Defines the reachable customer | Most US developers work outside the large technology firms, in banks, insurers, manufacturers, agencies and government contractors. Those employers are the ones short of senior reviewers and are the only natural buyers of a managed service. |

---

## Section 05 — Unit economics

**The analytical question:** What does one agent-hour and one L1 bundle cost, and does this operator have any cost advantage of its own?

### The advantage, isolated

**Exhibit 6 — Cost of one agent-hour by model tier (November 2026 list prices)**

| Line | Sonnet 5.5 ($2 / $10 per M tokens) | Opus 5.5 ($4 / $20) | Fable 5.1 ($10 / $50) |
|---|---|---|---|
| Cached context re-read, 7.2M tokens (A) | $0.72 | $1.44 | $1.80 |
| New context written to cache, 0.6M tokens (A) | $1.50 | $3.00 | $7.50 |
| Output, 90K tokens (A) | $0.90 | $1.80 | $4.50 |
| **Model cost per agent-hour** | **$3.12** | **$6.24** | **$13.80** |
| Sandbox VM and CI minutes (A) | $0.30 | $0.30 | $0.30 |
| **Total per agent-hour** | **$3.42** | **$6.54** | **$14.10** |

*Base case for L1–L2 work: 80% of hours on the mid tier and 20% on the stronger tier, which blends to **$4.05 an hour**. Cross-check: Cognition's Devin retails at an implied $8–9 an hour, about twice this cost, and Anthropic reports an average Claude Code spend of $13 per active developer day for interactive (part-time) use.*

**Exhibit 7 — Four ways a customer can get one L1's worth of work**

| Option | Annual cost | Note |
|---|---|---|
| Hire a US L1 | ~$128K | Plus about 10% of a senior's time for mentoring, not counted here. |
| Offshore contractor through a vendor (A) | ~$45–60K | The real price ceiling for any L1 replacement service. |
| **This operator's managed bundle** | **~$60K** | Operator supplies agents and the reviewing engineer. |
| Do it in-house: agent tool at retail + own senior's review time | ~$33K | ~$9.4K of agent time at $8.50 an hour plus 1/12 of an in-house L4. |

*The operator has no cost advantage. Its bundle costs $27,000 more than the customer doing the same thing itself. That premium buys one thing: the reviewing engineer on someone else's payroll, and someone else's name on the contract. It is worth paying only for a customer that has no senior engineers to spare.*

**Exhibit 8 — Build, rent or buy tokens, at year-3 volume (373,000 agent-hours)**

| Route | Annual cost | What it takes | Verdict |
|---|---|---|---|
| Buy API tokens (base case) | ~$1.51M | Nothing owned. Pay per active token. Frontier model quality. | **Chosen.** |
| Rent GPUs and self-host an open-weight model | ~$1.1M for three 8×H200 nodes at ~$5.30 per GPU-hour, plus ~$0.7M for two engineers to run them | Open-weight models of the Kimi K3 or DeepSeek V4 class need an 8×H200 node each. Idle hours are billed. | More expensive than tokens once staff is counted. |
| Own the GPUs | ~$1.07M: three nodes at ~$350K each (A) over 4 years, ~$110K power and hosting, ~$0.7M staff | $1.05M up front. Hardware two generations old by year 4. | Saves ~$0.4M, about 2% of revenue. |

*Owning looks $0.4M cheaper, but compute is only 7% of revenue while supervision is 40%. Open-weight models trail the frontier. If a weaker model drops first-pass acceptance by even five points, the extra reviewer time costs more than the whole saving. Rule of thumb for this business: do not own hardware until compute is above a quarter of cost of sales and ten or more nodes can be kept over 60% busy. Neither is in sight.*

### The P&L of one L1 bundle

**Exhibit 9 — One L1 replaced, one year**

| Line | Amount | Note |
|---|---|---|
| Customer's current cost | $128,200 | $88K base × 1.4 + $5K bonus (A) |
| **Bundle price** | **$60,100** | 47% of the salary it replaces |
| Agent compute, 1,100 hours × $4.05 | ($4,450) | 0.55 agent-years |
| Supervising engineer, 1/12 of $283K | ($23,600) | Writes tasks, reviews every change, owns incidents |
| Platform, security tooling, insurance | ($2,000) | (A) |
| **Cost of sales** | **($30,050)** | |
| **Gross margin** | **$30,050** | **50%** |

*Why 50%: software companies run at 70–80%, staffing firms at 20–30%. This is a blend of the two, and it matches what Devin's retail price implies over compute cost. A higher margin pushes the L1 price above the offshore alternative; a lower one cannot fund enterprise sales.*

---

## Section 06 — Annual operating model

**The analytical question:** What does the business look like in year 3, with the founders paid a market wage and the investors' capital charged for?

**Exhibit 10 — Year-3 P&L, 300 bundles (120 L1, 180 L2)**

| Line | Annual | Per bundle |
|---|---|---|
| Revenue — 120 × $60.1K + 180 × $86.6K | $22.80M | $76.0K |
| Agent compute (373,000 hours) | ($1.51M) | ($5.0K) |
| Supervising engineers (32.5 × $283K) | ($9.20M) | ($30.7K) |
| Platform, security, insurance | ($0.69M) | ($2.3K) |
| **Gross margin** | **$11.40M (50%)** | **$38.0K** |
| Sales and marketing | ($3.50M) | — |
| Product and platform engineering (10 people) | ($3.30M) | — |
| General, legal, compliance, liability cover | ($1.60M) | — |
| Customer onboarding and solutions | ($1.00M) | — |
| **Operating profit before founder pay** | **$2.00M** | — |
| Founders at market rate (2 × $400K) | ($0.80M) | — |
| **Operating profit after founder pay** | **$1.20M** | — |
| Charge for capital (25% on $12M) | ($3.00M) | — |
| **Economic profit** | **−$1.80M** | — |

*Capital of $12M (A) is the cumulative loss of about $10M over the first two years plus $2M of working capital. None of it is hardware. The 25% charge is what venture investors need from a company at this stage.*

**Breakeven.** Each bundle contributes about $38,000 of gross margin. Covering operating costs and founder pay takes **268 bundles (~$20.4M of revenue)**. Covering the capital charge as well takes **347 bundles (~$26.4M)**, which needs about 38 supervising engineers. The base case sits between the two: profitable on paper, short of what the capital costs.

---

## Section 07 — Sensitivity analysis

**The analytical question:** Which matters more, the price the operator can hold or the number of bundles one supervisor can cover?

**Exhibit 11 — Year-3 operating profit after founder pay ($M), 300 bundles**

| L1 bundles per supervisor (L2 in proportion) | Price −30% | Price −15% | Base price | Price +15% |
|---|---|---|---|---|
| 8 | −10.2 | −6.8 | −3.4 | 0.0 |
| 10 | −7.5 | −4.1 | −0.6 | +2.8 |
| **12 (base)** | −5.6 | −2.2 | **+1.2** | +4.6 |
| 16 | −3.3 | +0.1 | +3.5 | +6.9 |
| 24 | −1.0 | +2.4 | +5.8 | +9.2 |

*Both levers are steep. A 15% price cut and a slip from 12 to 10 bundles per supervisor each cost about $3M, more than twice the base profit. The business only clears its $3.0M capital charge in the bottom-right cells: supervisors covering 16 or more bundles at full price. Compute does not appear in the grid because it barely matters; a 30% rise in token cost moves the result by $0.45M.*

**Exhibit 12 — Volume at base price and base supervision**

| Bundles | 100 | 200 | 300 (base) | 450 | 600 |
|---|---|---|---|---|---|
| Operating profit after founder pay ($M) | −6.4 | −2.6 | +1.2 | +6.9 | +12.6 |
| Supervising engineers needed | 11 | 22 | 33 | 49 | 65 |

### The scenario the grid does not show

**Exhibit 13 — Adverse case, nothing exotic**

| Event | Impact | Comment |
|---|---|---|
| Base operating profit after founder pay | +$1.20M | Exhibit 10 |
| Renewals close 10% lower | ($2.28M) | Buyers know that agent time retails at $8–9 an hour and falls every year |
| Supervision slips from 12 to 10 bundles each | ($1.84M) | Turnover among reviewers, or harder codebases than planned |
| One customer worth 12% of revenue moves in-house at mid-year | ($0.96M) | Its supervisors stay on payroll for a quarter |
| Work shifts to the stronger model, compute +30% | ($0.45M) | |
| One security incident: credits and insurance excess | ($0.25M) | |
| **Adverse-case operating profit** | **−$4.58M** | Before any charge for capital |

*None of these events is unusual for a services company in its third year. Together they turn a $1.2M profit into a $4.6M loss, because most of the cost base is salaried people who cannot be switched off the way tokens can.*

---

## Section 08 — The cliff moves: what each doubling of the horizon does

**The analytical question:** If agents keep improving at the measured rate, when do the senior levels become replaceable, and who benefits?

**Exhibit 14 — Agent-years needed per level as the 80% horizon lengthens**

| 80% horizon | Roughly when (A) | L1 | L2 | L3 | L4 | L5 | L6 | L7 |
|---|---|---|---|---|---|---|---|---|
| 4 h | mid-2026 | 0.59 | 0.79 | 1.5 | 13 | no | no | no |
| **8 h (base)** | **now** | **0.55** | **0.67** | **0.93** | **2.6** | **~100** | **no** | **no** |
| 16 h | spring 2027 | 0.53 | 0.62 | 0.75 | 1.2 | 6.3 | ~1,100 | no |
| 32 h | late 2027 | 0.52 | 0.60 | 0.68 | 0.88 | 1.7 | 17 | no |
| 64 h | early 2028 | 0.52 | 0.59 | 0.65 | 0.75 | 0.95 | 2.2 | ~200 |

*"no" means more than 10,000 agent-years. Dates assume the ~129-day doubling continues, which is an extrapolation, not a forecast. The model also assumes failure is the only obstacle; it leaves out the parts of senior work that are not tasks at all, such as deciding what to build, aligning teams and being answerable.*

Three things follow:

- **The answer to "how many agents per level" has a short shelf life.** At a 4-hour horizon an L4 took 13 agent-years; at 8 hours, 2.6; at 16 hours, 1.2. Any fixed table of agents per level is out of date within two quarters.
- **For L1–L3 better models add almost nothing.** The count barely moves from 0.55 to 0.52. The cost that remains is review, and review falls only when customers trust the output enough to check less.
- **The gain goes to the customer and the lab, not to the operator.** When L4 becomes replaceable, the same model is on sale to every buyer the same day. The operator's 50% margin on supervision does not grow because the model improved; its supervision ratio does, and its price falls with it.

---

## Section 09 — Risk register

**The analytical question:** What can break this, and what specifically limits the damage?

**Exhibit 15 — Ranked exposures**

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Customers do it in-house with the same tools at about half the price | High | High | Sell only to buyers without spare senior engineers. Price on delivered work, not on agent-hours, so the comparison is not line by line. |
| Model labs or Cognition offer a supervised service themselves | High | High | Stay out of general-purpose work. Pick one or two verticals where review needs domain knowledge (for example regulated legacy systems). |
| Cannot hire or keep enough supervising engineers | High | High | Pay above market, rotate reviewers into platform work, and invest R&D in tools that raise bundles per reviewer. This ratio is the business. |
| Price erosion as token prices and retail agent rates fall | High | Medium | Multi-year contracts with outcome pricing. Pass token savings through slowly. |
| Agent introduces a security flaw or outage at a customer | Medium | High | Mandatory human approval on every merge, restricted credentials, liability cover, capped indemnities. |
| Revenue concentrated in a few customers | Medium | High | No customer above 10% of revenue by year 3. |
| Model supplier changes prices, rate limits or terms | Medium | Low–Medium | Keep the orchestration layer model-neutral. Compute is 7% of revenue, so even a 50% rise is survivable. |
| Reputational and political reaction to "replacing engineers" | Medium | Medium | Sell as capacity for backlog and maintenance, not as layoffs. |
| Horizon growth stalls | Low–Medium | Low for this plan | The plan only needs today's models. A stall protects the supervision margin. |
| Horizon growth continues and customers stop wanting review | Medium | High | This removes the product. The only hedge is owning the customer relationship and moving up to L3–L4 work as it opens. |

---

## Section 10 — Recommendation

**The analytical question:** Given all of it, what should a founder do with this idea?

Five findings converge:

1. **Compute is not the cost** (Section 05). Replacing an L1 takes about $4,450 of compute a year. The supervising human costs $23,600. Pricing the business as compute plus margin prices the wrong thing.
2. **The level ladder is a cliff, not a slope** (Section 01, 08). Under one agent-year covers L1 through L3. L4 costs as much as the engineer. L5 and above cannot be bought at any count today.
3. **The operator has no cost advantage** (Section 05). The customer can do the same swap for about $33,000 using tools sold direct by the operator's own suppliers.
4. **The margin pool goes elsewhere** (Section 03). The customer keeps 53% of the value, the reviewing engineer 18%, the operator about 2.5%.
5. **The constraint is reviewers, not demand or GPUs** (Section 01, 06). Year 3 tops out near 300 bundles and $23M, makes $1.2M, and misses its cost of capital by $1.8M.

> **Recommended structure**
>
> **Do not launch the seven-level replacement business.** If the founders want to operate in this space, the only version that holds up is narrow: a supervised service that does L1–L2 work (maintenance, migrations, test coverage, backlog tickets) for mid-size companies outside the technology sector that have codebases but few senior engineers. Buy tokens; own no hardware. Hire reviewers before customers. Price per unit of delivered work at roughly 45–50% of the loaded salary replaced. Spend the R&D budget on one number: bundles per supervising engineer. At 12 the business breaks even; at 16 or more it earns its capital.
>
> A founder whose real asset is engineering talent rather than enterprise sales should consider the simpler alternative: build the review tooling and sell it to the companies doing the swap in-house, which is where 80% of the displacement will happen.

> **What would change this recommendation**
>
> **For the better:** a proprietary way to verify agent output (tests, formal checks, domain-specific validators) that lifts one reviewer from 12 bundles to 30 or more. That would be a real advantage and would also open L3. A signed anchor customer in a regulated vertical willing to pay for accountability would also change the picture.
>
> **For the worse:** a model lab or Cognition launching a supervised, indemnified service of its own; retail agent prices falling below $5 an hour; or customers deciding that agent output for junior work no longer needs line-by-line review, which removes what this operator sells.

### Metrics to run it on

- **Bundles per supervising engineer** — target 12 rising to 16+. Every other number follows from this one.
- **First-pass acceptance rate** — share of agent changes merged without rework. It drives both agent-hours and reviewer time.
- **Gross margin per bundle** — against the $38,000 base, tracked by level, since L3 work sold at L2 prices loses money.
- **Price as a share of replaced loaded cost** — hold near 47%; a drift below 40% means buyers are benchmarking against in-house tools.
- **Customer concentration and renewal rate** — no customer above 10% of revenue; renewals are the test of whether accountability is worth a premium.

---

**ANALYTICAL BASIS** — Figures are directional estimates as of 10 November 2026 for a venture-funded operator selling supervised AI coding-agent capacity to US employers, built for structural analysis and not as a forecast. Sourced inputs: BLS OEWS May 2025 for software developers (1,687,890 jobs; median $135,980; mean $148,100; 10th/90th percentiles $82,460/$214,670); BLS Employer Costs for Employee Compensation, June 2026 (benefits 30% of private compensation); Anthropic API list prices as reported in October 2026 (Sonnet 5.5 $2/$10, Opus 5.5 $4/$20, Fable 5.1 $10/$50 per million tokens, cache reads $0.10–0.25); GPU rental prices as reported in early November 2026 (H100 ~$2–4, H200 ~$5.30, B200 ~$6.70–8.50 per GPU-hour at specialist clouds); METR time-horizon measurements through spring 2026 and its ~129-day doubling estimate; Cognition's reported $492M run-rate, $26B valuation and $2.00–2.25 unit pricing; the reported $12.8B 2026 AI coding tools market; and the Stanford/ADP study of early-career employment. Everything marked (A) is this memo's assumption: the seven-level salary ladder and headcount split, the 1.4× load factor, the token profile of an agent-hour, the 8-hour 80% horizon for November 2026, typical task lengths per level, agent speed-ups, the 2.5× overhead, supervision ratios, the 50% gross margin, adoption and managed-service shares, operating costs and the $12M capital figure. The success model (constant failure rate per hour of task) is deliberately simple; real tasks can be broken up by a human, which is exactly the supervision this memo prices. The conclusions are most sensitive to the supervision ratio, the 80% horizon, the price the operator can hold against in-house tools, and the assumed share of buyers who want an outside service. Legal points are for planning only and are not legal advice.

**FRAMEWORKS APPLIED** — Hypothesis-driven problem structuring · Market funnel (TAM/SAM/SOM) with a supervisor-capacity cap · Porter's Five Forces · Value chain and margin-pool analysis · Domain-specific structural analysis (agent time horizons, token billing) · Bottom-up unit economics with build-vs-rent-vs-buy comparison · Annual operating model with economic profit (market pay for founders, charge for capital) · Two-variable sensitivity · Adverse-case scenario · Capability-trajectory comparison · Risk register.
