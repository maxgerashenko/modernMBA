# The Flipper's Underwriting Memo

*Underwriting Memo · Independent Used-Vehicle Retail · Florida*

A full MBA-style teardown of an owner-mechanic car-flipping operation — industry structure, value chain, unit economics, sensitivity, risk, and the recommendation the numbers actually support.

**SUBJECT:** licensed independent dealer, 1 lot + 2 bays, ~180 retail units/yr
**OWNER:** master technician, sole operator
**BASE CASE:** $10k acquisition band

**Artifact (full styled version):** https://claude.ai/code/artifact/2b433464-31cd-41c0-971a-280c970ba88a

> **How a document like this is built:** define the market before valuing anything (TAM, then the addressable slice) → test industry structure (Five Forces) for the *average* return available → map the value chain to find where the margin pool actually sits → build unit economics bottom-up, then scale to a full P&L with the owner charged a market wage → stress the model on the two variables that move the answer → register the risks with likelihood, impact, and a named mitigation → recommend, and state what would change your mind.

---

## Section 00 — Executive summary

*The analytical question: Should a master technician deploy capital and labor into retailing used vehicles in Florida, and if so, how should the business be structured?*

| Metric | Value | Note |
|---|---|---|
| Revenue | $2.65M | 180 units at $14,699 all-in |
| EBITDA | $306K | 11.6% of revenue, after owner salary |
| Invested capital | $170K | floor-planned inventory |
| Return on capital | 180% | 99% unlevered |
| Economic profit | $128K | after charging owner labor at market |

> **Recommendation: Proceed — but structure it as a service business that retails cars, not a car business with a shop attached.**
>
> The headline 180% return on invested capital is real but misleading. Decomposing it shows that essentially all of the abnormal return is the owner's own mechanical labor, contributed to the business below its market price. Charge that labor at a Florida shop door rate and economic profit falls to **4.8% of revenue** — squarely inside the 3–5% band that independent dealers earn nationally. The operator is not beating the industry. He is buying into an industry-normal return by donating $178K of skilled labor a year.
>
> That reframes the decision. The scarce asset is the technician's 1,620 annual hours, not the capital. The value-chain analysis (Section 03) shows fixed operations — service and parts — is the highest-margin layer in the entire chain at 45–55% gross, with no inventory, no depreciation exposure, and no working capital. The right structure puts the bays first and uses retail as a channel for absorbing units the shop can improve, capped at a volume the owner can personally recondition.

---

## Section 01 — Market definition and sizing

*The analytical question: How big is the pool, and what share of it is genuinely addressable by a single-lot operator?*

Sizing is done top-down and then bounded by physical capacity, because in this business the binding constraint is lot space and technician hours, not demand.

**Exhibit 1 — Market funnel, TAM to SOM**

| Layer | Definition | Units / yr | Value |
|---|---|--:|--:|
| TAM | US used-vehicle transactions, all channels | ~40M | ~$1.3T |
| SAM — state | Florida share (~8% of national volume) | ~3.2M | ~$104B |
| SAM — segment | Independent-dealer retail, $8K–18K price band | ~410K | ~$5.4B |
| SAM — local | Within a 45-minute drive radius of the lot | ~26K | ~$340M |
| **SOM** | **Capacity-bound: 17.5 stalls at a 35-day turn** | **180** | **$2.6M** |

*Share of the local addressable segment: 0.7%. The operator is a price taker in every direction — too small to influence acquisition cost or retail pricing, which is the defining structural fact of this business.*

The SOM line is the one that matters. It is not derived from demand or ambition; it is **17.5 inventory slots divided by turn velocity**. Every strategic lever in this business ultimately shows up as a change to one of those two numbers.

---

## Section 02 — Industry structure: Five Forces

*The analytical question: What return does the average participant earn, and why?*

**Exhibit 2 — Force assessment**

| Force | Rating | Evidence |
|---|---|---|
| Supplier power | High | Wholesale supply is concentrated. Cox Automotive (Manheim) and OPENLANE dominate physical and digital lanes; fees are posted, non-negotiable at small volume, and charged to both sides. The operator has no leverage over the price of his single largest input. |
| Buyer power | High | Total price transparency. CarGurus, KBB and Autotrader let a buyer rank every comparable unit within 100 miles by price-to-market before they leave the house. Switching cost is zero. |
| Threat of entry | High at low end | Entry below the licensing threshold costs nothing but a bank balance. Above it — surety bond, garage liability, physical location, pre-licensing course — the barrier is real but low by any commercial standard. |
| Substitutes | Moderate | New-car incentives, leasing, Carvana/CarMax convenience, and simply keeping the current vehicle longer. Substitution intensity moves with interest rates. |
| Rivalry | Intense | Fragmented, undifferentiated, high fixed cost of inventory carry, and a perishable product — every day of age destroys value. Classic conditions for competing away margin. |

*Four of five forces are unfavorable. This is a structurally unattractive industry.*

**The conclusion drives everything downstream.** When industry structure is this poor, average returns are poor by construction, and no amount of operational enthusiasm changes that. Any return above the average must therefore come from a *firm-specific* advantage — something this operator has that the marginal competitor does not.

There is exactly one candidate: the owner is a master technician. That converts into a genuine cost advantage in reconditioning, and it is the only thing in this analysis that produces excess return. Section 05 quantifies it; Section 08 asks whether it is durable.

---

## Section 03 — Value chain and margin pool

*The analytical question: Of every dollar of margin created between wholesale and the driveway, who captures it?*

The instinct is to assume the retailer captures the retail spread. In this chain, the retailer captures the least attractive economics of any participant, and the parties who never take title do best.

**Exhibit 3 — Margin capture by layer**

| Layer | What it earns on | Gross margin | Capital & risk | Quality |
|---|---|--:|---|---|
| Auctions (Manheim, OPENLANE, ACV) | Buy fee + sell fee + transport, inspection, floor plan | 30–40% EBITDA | None — never takes title. Volume rises in booms *and* busts. | Best |
| Floor plan lenders | Interest on someone else's inventory | Spread | Collateralized, self-liquidating | Excellent |
| F&I / lenders | Finance reserve, warranty, GAP | ~100% incremental | Near-zero marginal cost per contract | Excellent |
| Fixed operations (service & parts) | Labor hours and parts markup | 45–55% | No inventory risk, no depreciation, no working capital | Excellent |
| **Retail — the flipper** | **Spread between wholesale and retail** | **3–5% net** | **Full title risk, mechanical risk, 35 days of market risk** | Worst |

*The retailer is the only participant absorbing all three risks — title, mechanical, and market — and it earns the thinnest net margin in the chain.*

Note the fourth row. **Fixed operations is the second-best business in this value chain, and it is the one the owner is already qualified to run.** Hold that finding — it is the pivot of the recommendation.

---

## Section 04 — Macro drivers

*The analytical question: Which external variables move the business, in which direction, and over what horizon?*

**Exhibit 4 — Driver sensitivity, Florida**

| Driver | Direction | Transmission mechanism |
|---|---|---|
| Interest rates | Dominant | The market is *payment-elastic, not price-elastic* — buyers shop dollars per month. A 200bp move changes what the same buyer can bid on the same car by roughly $1,500. It simultaneously moves the cost of floor plan. This is the single most important variable in the model. |
| Off-lease supply | Supportive | The 2021–22 production and leasing collapse structurally thinned the supply of clean 3-to-5-year-old units. Fewer good cars sourced at auction supports pricing but also raises acquisition cost. |
| Tax refund season | Seasonal | February–April is the strongest retail window in the sub-$15K band nationally. Inventory must be bought in December to sell into it. |
| Hurricane cycle | Both ways | A landfall totals thousands of units at once; insurance settlements produce a 60–90 day local demand spike. It also produces flood-titled inventory that will be washed through permissive states and resold — and it puts the operator's own uninsured lot inventory at risk. |
| Rental defleeting | Adverse | Fleet dispositions arrive in large synchronized blocks, and Florida absorbs a disproportionate share. |
| EV residuals | Adverse | Battery health is unpriceable at the retail level and OEM price cuts reset residuals without warning. There is no stable floor to underwrite against. |
| Insurance cost | Adverse | Florida premiums are among the highest in the country, which reduces the vehicle price a given household can carry. |

*Leading indicator: the Manheim Used Vehicle Value Index moves retail by roughly 6–8 weeks. It is the operator's early-warning system on inventory that is already bought.*

---

## Section 05 — Unit economics

*The analytical question: What does one transaction actually earn, built from the bottom up with nothing hidden?*

**Exhibit 5 — Per-unit P&L, base case**

| Line | Amount | Note |
|---|--:|---|
| Retail sale price | $13,900 | Priced to sell inside 35 days at ~96% of market |
| Dealer fee | $799 | Uncapped in Florida; conservative vs. market practice |
| **Total revenue** | **$14,699** | |
| Acquisition — hammer price | $9,200 | Bought with a known, correctable defect |
| Auction buy fee | $450 | Non-negotiable at this volume |
| Transport | $200 | |
| Recon parts | $700 | **Owner labor not charged here** — this is the edge |
| Sublet — alignment, glass, paint | $250 | Work that cannot be done in-house |
| Floor plan interest | $80 | 35 days on $9,200 |
| Recon variance reserve | $250 | Probability-weighted surprises |
| **Total cost of sale** | **$11,130** | Cost-to-market 80% |
| Front-end gross | $3,569 | 24.3% of revenue |
| F&I income | $300 | Third-party warranty attach and modest finance reserve |
| **Total gross per unit** | **$3,869** | |
| *Memo: imputed owner labor* | *($990)* | 9 hours at a $110 Florida door rate — value contributed, not paid |
| *Memo: economic gross* | *$2,879* | What the unit earns once labor is priced honestly |

*A conventional independent dealer earns roughly $2,400–2,800 total gross on a unit in this band. The base case beats that by about $1,100, and the memo lines show precisely where it comes from: unpaid skilled labor and the ability to buy defective cars others won't touch.*

### Cash conversion cycle

Days inventory outstanding: 35. Days sales outstanding: 2 — funds arrive at delivery. Days payable outstanding: 0 — the auction requires payment within two business days and will lock you out otherwise.

**Cash conversion cycle: ~37 days, entirely self-funded.** There is no supplier float anywhere in this business. That single fact is why floor plan financing exists as an industry, and why an operator's growth ceiling is set by working capital rather than by demand.

---

## Section 06 — Operating model at scale

*The analytical question: What does the whole enterprise earn once fixed costs and a market wage for the owner are charged against it?*

**Exhibit 6 — Annual P&L, 180 retail units**

| Line | Annual | Per unit | % rev |
|---|--:|--:|--:|
| Revenue | $2,645,820 | $14,699 | 100.0% |
| Cost of vehicles sold | $2,003,400 | $11,130 | 75.7% |
| **Gross profit** | **$642,420** | **$3,569** | **24.3%** |
| F&I income | $54,000 | $300 | 2.0% |
| Wholesale losses & policy expense | ($63,000) | ($350) | (2.4%) |
| **Total gross profit** | **$633,420** | **$3,519** | **23.9%** |
| Lot rent — lot + 2 bays | $54,000 | $300 | 2.0% |
| Garage liability & property insurance | $18,000 | $100 | 0.7% |
| Advertising & listing fees | $30,000 | $167 | 1.1% |
| Wages — technician, detailer, part-time sales | $95,000 | $528 | 3.6% |
| Shop supplies, tooling, scan subscriptions | $14,000 | $78 | 0.5% |
| Licensing, bond, DMV/EFS, compliance | $6,000 | $33 | 0.2% |
| DMS/CRM, utilities, telecom | $16,000 | $89 | 0.6% |
| Professional — CPA, legal | $9,000 | $50 | 0.3% |
| Owner salary at market | $85,000 | $472 | 3.2% |
| **Total operating expense** | **$327,000** | **$1,817** | **12.4%** |
| **EBITDA** | **$306,420** | **$1,702** | **11.6%** |

*Charging the owner a market salary is deliberate. Owner-operator businesses routinely flatter themselves by treating the owner's wage as profit; doing so makes the return incomparable to any alternative use of the same person's time.*

### The decomposition that matters

An 11.6% EBITDA margin is roughly three times the 3–5% independent dealers earn nationally. Before celebrating, the analysis has to explain the gap — because an unexplained outperformance in a structurally unattractive industry is almost always a modelling error or a hidden cost.

Here it is neither. It is 1,620 hours of the owner's skilled labor going into the cars at zero recorded cost. Priced at a $110 Florida door rate, that is **$178,200 of value** the P&L never sees.

> **Adjusted economic profit:** EBITDA $306,420 − owner shop labor at market $178,200 = **$128,220**
>
> That is **4.8% of revenue** — precisely the industry benchmark. The apparent outperformance disappears entirely under honest labor accounting. The operator is earning a normal return, and paying for the privilege with his own trade.

### Capital and returns

Average inventory runs about 17.5 units at $10,000 cost, or $175,000, of which floor plan funds roughly 80%. Add an operating cash reserve of $75,000 and leasehold plus equipment of $60,000, and invested equity is approximately $170,000.

Return on invested capital is therefore **180% levered, 99% unlevered**. Both figures are genuinely high — and they are high for a specific, unglamorous reason: the capital base is tiny relative to the labor input. This is a labor-intensive business wearing a capital-intensive costume. High ROIC in this setting is a statement about how little capital is at work, not about how good the business is.

---

## Section 07 — Sensitivity analysis

*The analytical question: Which two variables determine the outcome, and where is the cliff?*

Every other input can be wrong by a wide margin without changing the conclusion. Two cannot: **gross per unit** and **days to turn**. Turn matters more than most operators believe, because at a fixed 17.5-stall capacity it sets annual volume outright — and the fixed cost base does not shrink when the cars stop moving.

**Exhibit 7 — EBITDA by turn velocity and gross per unit**

| Days to turn | Units/yr | $3,200 gross | $3,600 gross | $3,900 gross | $4,300 gross |
|---|--:|--:|--:|--:|--:|
| 28 days | 228 | $314,724 | $405,924 | $474,324 | $565,524 |
| 35 days (base) | 182 | $191,306 | $264,106 | $318,706 | $391,506 |
| 45 days | 142 | $83,986 | $140,786 | $183,386 | $240,186 |
| 60 days | 106 | ($12,602) | $29,798 | $61,598 | $103,998 |

*Contribution per unit is gross less $350 of policy and wholesale loss and $167 of advertising; fixed operating cost of $297,000 is held constant. Owner salary is inside the fixed base.*

**Read the rows, not the columns.** Moving gross from $3,200 to $4,300 — an aggressive, hard-won $1,100 improvement — adds about $200K at base velocity. Moving turn from 60 days to 28 days at unchanged gross adds roughly *$285K*. Velocity is the more powerful lever and the cheaper one to pull, because it costs nothing but discipline: price to market on day one and wholesale anything that ages out.

The bottom-left cell is the failure mode, and it is the one that actually kills operators. At 60-day turn and compressed gross the business loses money while appearing busy, because the fixed base keeps running whether or not the cars move. It is reached not by a market crash but by ordinary optimism — holding out for another $500 on a unit that has already told you it is priced wrong.

### Rate shock

A 200bp increase in consumer rates hits from both sides: it reduces the price a payment-constrained buyer can support by roughly $1,500, which compresses gross, *and* it raises floor plan cost per unit. The correct response is not to hold for price. It is to shorten the turn and step down a price band, where buyers are less finance-dependent.

---

## Section 08 — Competitive positioning

*The analytical question: Where does this operator sit against the field, and is the position defensible?*

**Exhibit 8 — Strategic group map: gross per unit vs. scale** *(scatter chart in the artifact; positions below)*

| Player | Annual volume | Gross / unit | Note |
|---|--:|--:|---|
| Private flipper | ~10s/yr | $2.0K | Unlicensed |
| **Owner-mechanic lot** | **180/yr** | **$3.9K** | **Subject of this memo** |
| Independent lot | ~500/yr | $2.6K | |
| Franchise used dept. | ~2,000/yr | $4.3K | Mostly F&I + service |
| CarMax | ~1,000,000/yr | $2.3K | Net margin 2–3% |
| Carvana | ~500,000/yr | $6.8K | Heavily gain-on-sale |

The map's useful feature is that it is **non-monotonic**. Scale does not buy gross per unit — CarMax, the most operationally sophisticated retailer in the field, earns *less* gross per car than a two-bay lot. What scale buys is lower cost of capital, lower cost per acquired customer, and the ability to originate and securitize the loan. Carvana's $6,800 is not a car margin at all; a large share of it is gain on sale from securitizing receivables.

The owner-mechanic occupies a genuinely good spot for its size — top-quartile gross at the smallest viable scale. But the position is defensible only within a hard capacity ceiling. **The advantage is one person's hands, and it does not scale.** Hiring a second technician at market rate transfers the entire advantage to that technician's wage; the 46th unit per quarter earns independent-lot economics, not owner-mechanic economics.

That is the central strategic fact of the business: *this is a high-return operation that cannot be made larger without becoming an average one.*

---

## Section 09 — Risk register

*The analytical question: What can destroy a year of profit, how likely is it, and what specifically prevents it?*

**Exhibit 9 — Ranked exposures**

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Key-man dependency | Certain | Severe | **Structural, not mitigable.** The entire excess return is one person's labor. Injury or illness takes the business to zero margin, not to reduced margin. This is the strongest single argument for the recommendation in Section 10. |
| Aged inventory | High | High | A hard 45-day wholesale rule with no discretionary exceptions. Exhibit 7 shows this is where the money is won or lost. |
| Flood or washed title | Medium | Severe | NMVTIS and NICB check on every VIN without exception; buy only in lanes with arbitration rights. Florida's storm cycle makes this a permanent, not episodic, exposure. One missed unit is an $8–12K write-off — roughly three units of profit. |
| Named-storm loss to lot inventory | Medium | Severe | Inventory coverage with explicit named-storm inclusion, plus a written evacuation plan. $175K sitting on open asphalt is the largest concentrated exposure on the balance sheet. |
| Rate shock | Medium | High | Shorten turn, step down a price band toward less finance-dependent buyers. |
| Recon variance | High | Moderate | $250/unit reserve is already in the model; pre-purchase scan and a hard per-unit repair cap. |
| Consumer litigation | Medium | Moderate | FTC Buyers Guide compliance, documented recon file per unit, third-party warranty attach to move post-sale disputes off the balance sheet. |
| Licensing & compliance | Low | Severe | Licensed and bonded from day one. Unlicensed selling above Florida's three-vehicle threshold is an enforcement priority and carries criminal exposure; odometer and title-transfer errors carry federal exposure. |

---

## Section 10 — Recommendation

*The analytical question: Given all of the above, what should this operator actually do?*

Three findings converge, and they point somewhere other than where the operator's instinct does.

1. **The industry is structurally unattractive** (Section 02) — so the only source of excess return is firm-specific.
2. **The firm-specific advantage is mechanical labor** (Sections 05–06) — and once that labor is priced at market, the excess return is gone entirely.
3. **Service is the second-best business in the value chain** (Section 03) — 45–55% gross, no inventory, no depreciation, no working capital, no market risk.

Put those together and the conclusion is uncomfortable but hard to argue with. The technician's 1,620 annual hours are the scarce asset. Deployed into retail cars, those hours return $128K of economic profit while carrying title risk, mechanical risk, market risk, named-storm risk, and consumer-litigation risk. Deployed into a service bay at a $110 door rate with 55% gross margin, comparable hours generate broadly similar profit **with none of those risks and essentially no working capital**.

> **Recommended structure: Lead with fixed operations. Retail vehicles as a secondary channel, capped at owner recon capacity.**
>
> Run the shop as the primary business and the lot as a complement — roughly 8–10 units a month, strictly units the shop's own capability makes cheap to improve. That volume sits comfortably inside the owner's hours, keeps the per-unit advantage intact rather than diluting it across hired labor, and holds inventory exposure near $100K instead of $175K.
>
> The retail side then does something more valuable than its own margin: it feeds the bays. Every car sold is a future service customer, and service customers are the acquisition channel for trade-ins — which are the only source of inventory that arrives below auction cost. That closes the loop the auction houses otherwise collect a fee on, and it is the one advantage in this business that compounds rather than capping out.

### What would change this recommendation

- **A sourcing channel that isn't the auction.** If the operator can build repeatable private-party or fleet acquisition at $800–1,000 below auction cost, the retail advantage stops depending on his hands and becomes genuinely scalable. That would justify pushing volume.
- **Access to F&I economics.** A credit-union relationship producing real finance reserve and warranty attach moves gross per unit toward the franchise column of Exhibit 8 without adding a single labor hour.
- **Sustained sub-30-day turn.** Exhibit 7's top row is a materially different business. If turn discipline proves durable over two full seasons, the volume case reopens on evidence rather than optimism.

### Metrics to run the business on

The model above is only as good as the operator's willingness to be told he is wrong by his own numbers. Six measures do that work:

- **Average days in stock** and **percentage of inventory over 45 days** — targets under 35 and under 10%. These are the early-warning pair.
- **Cost-to-market** — all-in cost as a percentage of market retail; target 80–85%. Diagnoses overpaying at the auction before the unit ages.
- **Recon variance** — actual repair cost against the pre-purchase estimate. Diagnoses bad buying decisions and bad diagnosis separately.
- **Retail-to-wholesale ratio** — target above 82% retailed. Falling ratio means acquisition standards have slipped.
- **Inventory turn, annualized** — the single number that reconciles to Exhibit 7.

---

**ANALYTICAL BASIS** — Figures are directional industry estimates for an owner-operated Florida independent dealer in the $8–18K retail band, built for structural analysis rather than as an audited forecast. Acquisition cost, gross per unit and turn velocity vary materially by segment, season and rate environment; the sensitivity grid in Exhibit 7 exists because those inputs should be re-derived from live auction and listing data before capital is committed.

**FRAMEWORKS APPLIED** — Market funnel (TAM/SAM/SOM) · Porter's Five Forces · Value chain and margin-pool analysis · PESTEL drivers · Bottom-up unit economics · Cash conversion cycle · Two-variable sensitivity · Strategic group mapping · Risk register · Economic profit adjustment for owner labor.
