# Four Cents to Make, a Quarter to Sell

**Artifact:** https://claude.ai/artifact/XKA3VkxJBtT5apQNGS51sa
**Notion:** https://app.notion.com/p/41bba21e32d4818f91cbd2a19a50368b?pvs=204

An MBA-style teardown of a startup that answers business phone calls with an LLM voice agent, trained on each client's documents and website, sold by the minute on a Twilio number — and why the cost model works while the horizontal business does not.

**SUBJECT:** bootstrapped technical founder, self-built stack on direct APIs
**MARKET:** US small businesses, inbound calls first
**BASE CASE:** $0.25/min, 500 min/client/mo, 100 clients in year two

---

## Section 00 — Executive summary

**The analytical question:** Can a startup that rents out an AI phone agent by the minute make money, and is the idea already dead?

| KPI | Value | Note |
|---|---|---|
| All-in cost / min | $0.042 | self-built, inbound, current list prices |
| Suggested price / min | $0.25 | inside the $0.15–0.50 SMB market band |
| Markup / gross margin | 495% / 78% | margin after card fees and per-client costs |
| Clients for owner market pay | ~171 | at 500 min/mo each, 4% monthly churn |
| Economic profit @ 100 clients | ($60,690) | after a $150K market wage for the founder |
| Named competitors | 51+ | on one investor map; hundreds with resellers |

> **Recommendation**
>
> **The idea is not dead, but the version described is the most crowded seat in the room: do not launch a general-purpose per-minute voice agent; pick one vertical, sell it on rented infrastructure first, and move to the self-built stack once volume passes roughly 30,000 minutes a month.**
>
> The per-minute arithmetic is excellent. At November 2026 list prices one inbound minute costs about **$0.042** to produce on a self-built stack: Twilio carriage and audio streaming ($0.013), Deepgram streaming speech-to-text ($0.0065), Deepgram Aura-2 text-to-speech ($0.011), a budget LLM with retrieval context ($0.004), recording and analytics ($0.003), and a 10% allowance for unbillable minutes. Small-business buyers pay **$0.15 to $0.50** per minute for the same thing from Rosie, Dialzara, Reception.ai and others, so $0.25 is a defensible price with a 495% markup.
>
> The problem is that everyone can do this arithmetic. A single investor market map published in September 2026 names 51 voice-AI companies; Vapi and Bland alone are reported to have raised over $170M between them, and Retell is reported at about $60M of annualised revenue. Every one of the seven cost lines the founder asked about is a metered commodity with several interchangeable suppliers. The margin is real and undefended.
>
> **So the binding constraint is distribution, not cost.** At $0.25 a minute a 500-minute client is worth about $98 a month of contribution. Replacing a market salary of $150,000 takes about **171 paying clients** once churn replacement is paid for. A horizontal product has no cheap way to find those clients against funded rivals. A vertical product with a real integration (a dental practice system, a towing dispatch board, a property-management ledger) does.

---

## Section 01 — Market definition and capacity

**The analytical question:** How big is the pool of businesses that would pay for an answered phone, and what actually caps a new entrant?

**Exhibit 1 — Market funnel, TAM to SOM**

| Layer | Definition | Businesses |
|---|---|---|
| TAM | US small businesses, all types (SBA count) | ~34.8M |
| SAM — employer firms | Small businesses with employees and a published phone line | ~6.3M |
| SAM — phone-dependent | Local services where a missed call is a lost job: home services, dental and medical offices, legal, auto, salons, property management (directional estimate) | ~3M |
| SAM — reachable | Not yet on an AI answering product and reachable by one founder's channel (directional estimate) | ~1–2M |
| **SOM — 2 to 3 years** | **Bound by founder sales and onboarding throughput at 5–10 new clients a month, net of 4% monthly churn** | **150–300** |

*Counts are directional. Demand is four orders of magnitude larger than what one team can sign; the last row is set by acquisition speed and churn, not by the size of the market.*

The capacity math that governs the business:

- **System capacity is not the limit.** One $40 server carries dozens of concurrent calls because the heavy work (speech, language model) runs at the vendors. Twilio numbers are provisioned by API in seconds.
- **Onboarding is light but not zero.** Crawling a client's website and loading documents into a vector index takes minutes. Getting the agent to book into the client's actual calendar or job system is the part that takes days.
- **Churn sets the treadmill.** At 4% monthly churn, a 200-client book loses 96 clients a year. A founder signing 8 a month is standing still at 200.
- **Usage per client is small.** A typical local business generates 300 to 900 call minutes a month. Revenue per client at $0.25 is $75 to $225. This is a volume business from the first day.

---

## Section 02 — Industry structure — Five Forces

**The analytical question:** What return does the average participant earn before any firm-specific edge?

**Exhibit 2 — Force assessment**

| Force | Rating | Evidence |
|---|---|---|
| Supplier power (Twilio, speech, LLM vendors) | Low | Every layer has several interchangeable vendors and falling prices. Deepgram alone lists streaming transcription at $0.0048–0.0078 a minute; twelve text-to-speech vendors sit between $0.009 and $0.067 per audio minute. |
| Buyer power (small-business owners) | High | Month-to-month usage billing, no switching cost beyond porting a number, and public price lists from a dozen rivals to anchor on. |
| Threat of entry | Very high | Vapi, Retell, ElevenLabs Agents and Deepgram's Voice Agent API let anyone ship a working phone agent in a weekend. The founder's own stack is the same seven APIs. |
| Substitutes | High | Human answering services (Smith.ai, about $2.40 a call), voicemail-to-text, online booking widgets, and phone-system vendors bundling an AI attendant at no extra charge. |
| Rivalry | Intense | 51 named companies on one September 2026 market map, two platform vendors closing $50M rounds in mid-2026, and weekly "best AI receptionist" comparison articles ranking ten at a time. |

*Four of five forces unfavorable. The one favorable force, cheap interchangeable inputs, is the same fact that makes entry trivial.*

**Implication.** In a structure like this the average seller earns a thin return, and price drifts toward cost. Any excess return has to come from something a rival cannot rent: a distribution channel, a system-of-record integration, or a regulated niche.

---

## Section 03 — Value chain and margin pool

**The analytical question:** Of the $0.25 a client pays for a minute, who takes what, and who carries risk for it?

**Exhibit 3 — Value extracted from one inbound minute at $0.25**

| Participant | Take | Share | Risk carried |
|---|---|---|---|
| Twilio — inbound local carriage + Media Streams | $0.0129 | 5.2% | None. Metered. |
| Speech-to-text — Deepgram Flux streaming | $0.0065 | 2.6% | None. Metered on connection time. |
| Text-to-speech — Deepgram Aura-2 | $0.0113 | 4.5% | None. Metered on characters spoken. |
| LLM — budget tier, ~12K input / 250 output tokens per minute | $0.0042 | 1.7% | None. Billed per token whatever the call outcome. |
| RAG — embeddings and vector queries in Postgres | $0.0002 | 0.1% | None. |
| Recording, storage, post-call summary | $0.0030 | 1.2% | None. |
| Unbillable minutes — spam, tests, hang-ups (10%) | $0.0038 | 1.5% | Borne by the startup. |
| Card processing — 2.9% + $0.30 per invoice | $0.0079 | 3.1% | None. |
| Per-client fixed — number $1.15 + database ~$1.00, spread over 500 min | $0.0043 | 1.7% | Borne by the startup. |
| **The startup** | **$0.1959** | **78.3%** | **Client acquisition, churn, onboarding, uptime, and liability when the agent says something wrong.** |

*Suppliers take about 22 cents of each dollar and carry none of the risk. The startup keeps 78 cents because it is the only party holding the client relationship, which is also the only part a rival has to work to replicate.*

---

## Section 04 — Domain-specific structural factors

**The analytical question:** What do telephony rules and voice-agent engineering do to this model that a generic SaaS plan would miss?

**Exhibit 4 — Structural factors and their transmission**

| Factor | Effect | Mechanism |
|---|---|---|
| TCPA and outbound AI calls | Outbound is a legal product | The FCC ruled in February 2024 that AI-generated voices are "artificial or prerecorded" under the TCPA. Outbound calls need prior consent, and statutory damages run $500 to $1,500 per call. A platform that lets clients upload a lead list inherits that exposure. |
| Inbound calls | Mostly outside TCPA | The caller initiated the call. An inbound-only product avoids the heaviest compliance burden, which is why inbound reception is the safe wedge. |
| AI disclosure | Build it in now | California's BOT Act already requires disclosure when a bot sells to the public; Utah requires it in high-risk interactions; an FCC rule mandating in-call AI disclosure has been pending since July 2024. One opening sentence solves all three. |
| Call recording consent | Per-state | About a dozen states, including California and Florida, require all-party consent to record. Analytics depend on recordings, so the greeting must announce recording by default. |
| Latency budget | Limits vendor choice | Callers tolerate roughly 800 ms between turns. That rules out slow premium models for the live turn and pushes the stack toward fast budget LLMs and streaming speech vendors, which is also why the LLM line is so cheap. |
| Number reputation | Outbound cost | New numbers placing outbound calls get labelled spam quickly. Branded calling and number rotation add cost per call; Retell lists branded calls at $0.10 each. |
| Database per client | Design choice, not a cost | A dedicated Postgres database per client is clean for isolation but multiplies operations work. A shared instance with one schema per client and pgvector costs about the same in total at 100 clients and far less effort. |

*Regulatory lines are summarised for planning, not legal advice.*

---

## Section 05 — Unit economics

**The analytical question:** What does one minute cost on each possible stack, and what does one client earn?

### The advantage, isolated

**Exhibit 5 — The same inbound minute on six stacks, list prices November 2026**

| Stack | Cost / min | What is included |
|---|---|---|
| **Self-built on direct APIs** | **$0.042** | **Twilio + Deepgram STT/TTS + budget LLM + own orchestration server** |
| Vapi | ~$0.09 | $0.05 orchestration fee plus the same speech, LLM and carriage passed through at cost |
| Deepgram Voice Agent API + Twilio | ~$0.09 | $0.075 bundled STT, LLM and TTS, plus $0.013 carriage |
| Retell AI | ~$0.10 | $0.055 infrastructure + $0.015 voice + ~$0.008 small LLM + $0.015 telephony + $0.005 knowledge base |
| ElevenLabs Agents + Twilio | ~$0.10 | $0.08 per call minute, LLM at cost, carriage separate |
| Bland AI | $0.11–0.14 | Bundled rate, plus a $299–499 monthly plan to reach the lower rates; telephony separate |

*The founder's edge from building is about five cents a minute, exactly the orchestration fee the platforms charge. It is worth $500 a month at 10,000 minutes and $2,500 a month at 50,000. It is an engineering saving, not a moat: any competitor can make the same choice.*

**Exhibit 6 — LLM line by model choice, per call minute**

| Model tier | Input / output per 1M tokens | Cost / min | Note |
|---|---|---|---|
| Claude Haiku 5.5 | $0.10 / $0.50 | $0.0013 | Cheapest of the four at these list prices |
| Gemini 3.5 Flash-Lite | $0.30 / $2.50 | $0.0042 | Base case in this memo |
| GPT-5.6 Luna | $1.00 / $6.00 | $0.0135 | Before prompt-cache discounts |
| Claude Sonnet 5.5 | $2.00 / $10.00 | $0.0265 | Premium reasoning; adds 2.3 cents a minute |

*Assumes four agent turns a minute, each resending a ~3,000-token prompt (instructions, retrieved passages, call history) and producing ~60 tokens. Prompt caching cuts the input side by up to 90% on most vendors and is not counted here.*

### One client, one month

**Exhibit 7 — Per-client monthly P&L at $0.25 per minute**

| Line | Amount | Note |
|---|---|---|
| Billable minutes | 500 | ~165 calls at 3 minutes |
| **Revenue** | **$125.00** |  |
| Variable cost of minutes | ($21.00) | 500 × $0.042 |
| Card processing | ($3.93) | 2.9% + $0.30 |
| Phone number + database | ($2.15) | Twilio local number $1.15, Postgres allowance ~$1.00 |
| **Contribution per client** | **$97.92** | **78.3% of revenue** |
| Acquisition cost to recover | $400 | Assumed blended cost per signed client; payback ~4 months |
| Expected lifetime at 4% monthly churn | 25 months | Lifetime contribution ~$2,450, about 6× acquisition cost |

*The $400 acquisition cost and 4% churn are assumptions, not measured figures. They are the two inputs this model is most sensitive to and the first two the founder should measure.*

**Exhibit 8 — Price, markup and margin at four monthly volumes**

| Line | 10,000 min | 50,000 min | 250,000 min | 1,000,000 min |
|---|---|---|---|---|
| Clients at 500 min each | 20 | 100 | 500 | 2,000 |
| Revenue / month at $0.25 | $2,500 | $12,500 | $62,500 | $250,000 |
| Variable cost at $0.042 | ($420) | ($2,100) | ($10,500) | ($42,000) |
| Card fees + per-client fixed | ($122) | ($608) | ($3,038) | ($12,150) |
| **Gross profit / month** | **$1,958** | **$9,792** | **$48,962** | **$195,850** |
| Gross margin | 78.3% | 78.3% | 78.3% | 78.3% |
| Platform fixed costs | ($500) | ($750) | ($6,000) | ($18,000) |
| Churn replacement (4% × $400) | ($320) | ($1,600) | ($8,000) | ($32,000) |
| **Operating profit / month, before founder pay** | **$1,138** | **$7,442** | **$34,962** | **$145,850** |
| Operating margin | 46% | 60% | 56% | 58% |

*Fixed costs step from $500 a month (two small servers, monitoring, insurance) to $18,000 a month at a million minutes, where support staff are included. Vendor volume discounts of 10–20% above 250,000 minutes are not counted.*

**Exhibit 9 — Markup and margin by price point, at $0.042 cost**

| Price / min | Markup on cost | Margin on minutes | Where it sits in the market |
|---|---|---|---|
| $0.10 | 138% | 58% | At the platforms' own all-in rates; no room for acquisition cost |
| $0.15 | 257% | 72% | Matches Rosie's 1,000-minute plan ($149) |
| $0.20 | 376% | 79% | Matches Rosie's 250-minute plan and Reception.ai's top plan |
| **$0.25 — suggested** | **495%** | **83%** | **Below Dialzara ($0.35–0.48) and My AI Front Desk (~$0.50)** |
| $0.35 | 733% | 88% | Only holds with a vertical integration the client cannot get elsewhere |

*Margin on minutes excludes card fees and per-client fixed costs, which take a further 5 points at 500 minutes per client. A $29 monthly minimum protects the low-usage client, whose number and database cost the same as anyone's.*

---

## Section 06 — Annual operating model

**The analytical question:** What does a year earn at a realistic second-year scale once overhead and a market wage are charged?

**Exhibit 10 — Annual P&L at 100 clients, 50,000 minutes a month**

| Line | Annual | Per client |
|---|---|---|
| Revenue — 600,000 minutes at $0.25 | $150,000 | $1,500 |
| Variable cost of minutes | ($25,200) | ($252) |
| Card processing | ($4,710) | ($47) |
| Phone numbers and client databases | ($2,580) | ($26) |
| **Gross profit** | **$117,510** | **$1,175** |
| Servers, shared Postgres, monitoring | ($4,800) | ($48) |
| Insurance (E&O, cyber), tools, admin | ($4,200) | ($42) |
| Client acquisition — 48 replacements at $400 | ($19,200) | ($192) |
| **Profit before owner compensation** | **$89,310** | **$893** |
| Owner compensation at market — senior full-stack / AI engineer, US | ($150,000) | ($1,500) |
| **Economic profit** | **($60,690)** | **($607)** |

*At 100 clients the business pays the founder about $89,000, some $61,000 less than the same person earns employed. Economic breakeven arrives at about 171 clients (roughly 85,500 minutes a month). Growth beyond the base book, not just replacement, would add further acquisition spend not shown here.*

The cost structure is light enough that the outcome is a pure function of client count. That is the good news and the bad news: nothing in the model improves by itself, and every one of the 171 clients has to be won against a funded competitor's advertising.

---

## Section 07 — Sensitivity analysis

**The analytical question:** Which matters more: the number of clients or the price per minute?

**Exhibit 11 — Annual profit before owner compensation, by client count and price**

| Clients | $0.10 / min | $0.15 / min | $0.20 / min | $0.25 / min | $0.35 / min |
|---|---|---|---|---|---|
| 20 clients | ($3,816) | $2,010 | $7,836 | $13,662 | $25,314 |
| 50 clients | ($3,540) | $11,025 | $25,590 | $40,155 | $69,285 |
| 100 clients (base) | $1,920 | $31,050 | $60,180 | $89,310 | $147,570 |
| 200 clients | $3,840 | $62,100 | $120,360 | $178,620 | $295,140 |
| 500 clients | ($17,400) | $128,250 | $273,900 | $419,550 | $710,850 |

*500 minutes per client, $0.042 cost, 4% monthly churn at $400 per replacement, stepped fixed costs. Green cells clear the $150,000 market wage. At $0.10 no client count works, because churn replacement eats the whole contribution; at $0.25 it takes about 170 clients; at $0.35 about 100.*

### The scenario the grid does not show

**Exhibit 12 — Adverse case at 100 clients, nothing exotic**

| Event | Impact | Comment |
|---|---|---|
| Base case profit before owner compensation | $89,310 | Exhibit 10 |
| Churn runs 6% a month instead of 4% | ($9,600) | 24 extra replacements at $400; usage billing makes leaving free |
| A fifth of the book negotiates down to $0.18 | ($8,400) | Rosie and others publish $0.15–0.20 effective rates |
| Clients ask for a premium voice | ($12,000) | ElevenLabs-class voices add about 2 cents a minute across 600,000 minutes |
| One multi-hour carrier or vendor outage | ($1,500) | Service credits to keep affected clients |
| **Adverse case profit before owner compensation** | **$57,810** | **About 39% of a market wage** |

*Four ordinary frictions take a third off an already below-market result. None is a catastrophe; together they describe a normal year in a crowded category.*

---

## Section 08 — Is it a dead idea? Counting the competition

**The analytical question:** How many companies already do this, what do they charge, and where is there still room?

**Exhibit 13 — Who already sells an AI phone agent, by layer**

| Layer | Named players | Pricing | What it means for the founder |
|---|---|---|---|
| Developer platforms | Vapi, Retell AI, Bland AI, Synthflow, ElevenLabs Agents, Deepgram Voice Agent, Voiceflow, Telnyx | $0.05–0.14 per minute platform rate; $0.07–0.31 all-in | This is the exact business described: number, agent, per-minute bill, analytics. Vapi reports $72M raised and over a billion calls; Retell about $60M annualised revenue; Bland over $100M raised. **Closed to a new entrant.** |
| Small-business receptionists | Rosie, Goodcall, Dialzara, Upfirst, Reception.ai, My AI Front Desk, Smith.ai, plus dozens more | $25–350 a month; $0.15–0.50 per effective minute | Many are thin layers on the platforms above. Crowded but fragmented, and none owns a vertical. **Open only with a channel.** |
| Enterprise agents | PolyAI, Sierra, Parloa, Decagon, Cresta, Replicant, Regal, Kore.ai | Custom contracts, typically six figures a year | Sold by enterprise sales teams with long cycles. **Not reachable by a bootstrapped founder.** |
| Vertical applications | EliseAI (housing), Hippocratic AI and Infinitus (health), HappyRobot (freight), Avoca (home services), Slang AI and ConverseNow (restaurants), Toma (auto), 7 more | Per seat, per location or per outcome | Each wins by integrating with one industry's system of record. **This is where new companies are still being funded.** |
| Evaluation and monitoring | Hamming, Coval, Cekura, Roark, Braintrust | Per test or per monitored minute | Tools that test and score voice agents. Named by the same market map as underexplored. |

*Layer membership follows Hustle Fund's 51-company voice-AI market map (17 September 2026); pricing from vendor pages and third-party comparisons dated June–November 2026. Air AI, named in the brief, was not re-verified here; it was the subject of an FTC complaint in 2025 over earnings claims (recalled, not re-checked).*

**How many companies do it?** One investor map names 51 across the stack, of which 28 sell agents directly to businesses. Comparison articles add at least eight more small-business receptionist brands that are not on that map. Counting white-label agencies reselling Vapi, Retell and Synthflow, the true number of sellers is likely in the hundreds; that last figure is an estimate, not a count.

**Dead or not?** The horizontal version (a number, a bot, a per-minute meter, a dashboard) is finished as a startup idea: it is a feature of well-funded platforms that already price near $0.09 a minute. The category is very much alive, with $50M rounds closing in May and June 2026. What remains open:

- **A vertical with a system-of-record integration.** The agent that writes the booking into the dental practice system or the dispatch board is worth $0.35 a minute and does not churn at 4%.
- **Languages and markets the US platforms serve badly.** Non-English small business, or countries where Twilio-first products have weak local numbers and voices.
- **Outcome pricing.** Charging per booked appointment or per qualified lead rather than per minute, which the per-minute platforms cannot match without owning the workflow.
- **Agency or reseller of an existing platform.** Lowest capital, thinnest margin, and a fast way to learn which vertical is worth building for.

---

## Section 09 — Risk register

**The analytical question:** What can break this, and what specifically prevents it?

**Exhibit 14 — Ranked exposures**

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Funded platforms and vertical rivals outspend on acquisition | High | High | Choose one vertical and one channel (an industry association, a software partner) rather than paid search. |
| Price compression toward $0.10–0.15 | High | High | Sell a plan with an outcome attached (booked jobs) and a monthly minimum, not a bare meter. |
| Churn above 4% a month | High | High | Integrate with the client's calendar or job system; integrated clients have something to lose by leaving. |
| Agent gives wrong information (price, hours, medical or legal detail) | Medium | High | Answer only from retrieved client content, hand off to a human on low confidence, carry E&O cover, log every call. |
| Outbound misuse by a client triggers TCPA claims | Medium | Severe | Launch inbound-only; gate outbound behind consent records and contract indemnity. |
| Vendor price or API change (speech, LLM, Twilio) | Medium | Medium | Keep each layer behind an interface; the cost table shows at least two substitutes per line. |
| Phone or model vendor bundles the product for free | Medium | High | Same answer as the first row: the workflow integration is the only part a bundle does not include. |
| Latency or audio quality drives hang-ups | Medium | Medium | Streaming speech both ways, regional servers, and a tracked hang-up-in-first-10-seconds rate. |

---

## Section 10 — Recommendation

**The analytical question:** Given all of it, what should the founder do?

Four findings converge:

1. **The minute is cheap and the markup is large** (Sections 03, 05): about $0.042 to make, $0.25 to sell, 78% gross margin.
2. **The margin is not defended by anything** (Section 02): all seven cost lines are rented commodities, and renting the whole stack costs a rival only five cents more.
3. **Client count decides the outcome** (Sections 06, 07): about 171 clients to match a salary, and no price fixes a weak acquisition channel.
4. **The horizontal seat is taken; vertical seats are not** (Section 08).

> **Recommended structure and sequence**
>
> **Pick one vertical before writing the voice pipeline.** Choose it by access (an industry the founder can reach cheaply) and by a system of record with an API.
>
> **Sell the first 10 to 20 clients on a rented platform** (Retell or Vapi at about $0.09–0.10 a minute). At $0.25 this still leaves about 60% gross margin and costs days, not months.
>
> **Move to the self-built stack past roughly 30,000 minutes a month**, when the five-cent saving reaches $1,500 a month and repays the engineering. Use the cost table in Exhibit 3 as the bill of materials.
>
> **Price at $0.25 a minute with a $29 monthly minimum, inbound only, with AI and recording disclosure in the greeting.** Add an outcome-priced plan once the integration exists.

> **What would change this recommendation**
>
> If the founder already owns a distribution channel (an existing client base, an agency, a software product with users who miss calls), the horizontal product becomes viable as an add-on, because acquisition cost falls toward zero. If measured acquisition cost is above about $800 or churn above 6% a month, the per-minute model does not reach a market wage at any realistic scale and should be dropped in favour of reselling.

### Metrics to run it on

- **Paying clients**, against the breakeven of about 171.
- **Cost per signed client and payback months**; the model assumes $400 and four months.
- **Monthly logo churn**; the model assumes 4%.
- **All-in cost per billable minute**, against $0.042, rebuilt from invoices each month.
- **Calls resolved without human handoff**, the one number that says whether the product works.

---

**ANALYTICAL BASIS** — Figures are directional estimates for a bootstrapped, US, inbound-first AI phone agent sold to small businesses by the minute, built for structural analysis and not as an audited forecast. Vendor prices are public pay-as-you-go list prices read on 17 November 2026 (Twilio, Deepgram, Retell) or from third-party comparisons dated June–November 2026 (text-to-speech, LLM, competitor plans, funding and revenue figures), and will move. Claude prices are Anthropic list prices as cached 3 November 2026. Token counts per minute, talk share, unbillable-minute rate, minutes per client, acquisition cost, churn, database allowance, fixed-cost steps and market-size layers below the SBA counts (themselves recalled, not re-fetched) are assumptions and are labelled as such. Regulatory notes are for planning and are not legal advice. The earlier memo in this hub, the AI receptionist for NYC salons, covers the vertical version of the same product.

**FRAMEWORKS APPLIED** — Market funnel (TAM/SAM/SOM) with an acquisition-and-churn capacity cap · Porter's Five Forces · Value chain and margin-pool analysis · Domain-specific regulatory and engineering analysis · Bottom-up unit economics with build-versus-rent cost decomposition · Volume-tier margin table · Two-variable sensitivity · Adverse-case scenario · Competitive layer map · Risk register · Economic profit adjustment for owner labor.

**SOURCES** — [Twilio Voice pricing (US)](https://www.twilio.com/voice/pricing/us) · [Deepgram pricing](https://deepgram.com/pricing) · [Soniox TTS price comparison](https://soniox.com/compare/tts/pricing) · [Retell AI pricing](https://retellai.com/pricing) · [Morph: Vapi vs Retell vs Bland vs Synthflow](https://www.morphllm.com/comparisons/vapi-vs-retell-vs-bland-vs-synthflow) · [Stork.ai: ElevenLabs Agents pricing](https://www.stork.ai/blog/elevenlabs-agents-pricing-2026) · [Dupple: best AI receptionists, priced](https://dupple.com/learn/best-ai-receptionists) · [Hustle Fund voice AI market map](https://www.hustlefund.vc/post/voice-ai-market-map) · [eCorp IT: budget LLM prices](https://ecorpit.com/budget-llm-tier-cost-comparison-flash-lite-luna-sonnet-2026/) · [Softcery: US voice AI regulations](https://softcery.com/lab/ai-voice-agents-legal-compliance-regulatory-overview/)
