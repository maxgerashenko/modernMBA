# If AI replaces office workers, who still gets paid from GDP?

**Artifact:** https://claude.ai/artifact/4yNsP3SkphqqC6PKTUPsKB
**Notion:** https://app.notion.com/p/415ba21e32d481e58f93f786cb20976e
**Related memos:** [AI developer replacement (USA)](../research/ai-developer-replacement-usa.md) · [AI developer agents, independent view](../research/ai-developer-agents-independent-usa.md)

*Macro note, not a business teardown memo. It lives in `reports/` so it stays out of `research/compare.md`. US data for 2025; labor force as of October 2026.*

> About half of US national income comes back to people as pay. White-collar workers take 69% of the measured wage bill, about a quarter of all GDP. Software developers are only 3.3% of white-collar pay, or 0.8% of GDP.

| Key figure | Value |
|---|---|
| US GDP 2025 | $30.86T (GDI, income side: $30.91T) |
| Paid to employees (wages + benefits) | $15.72T, 51% of GDI |
| White-collar wages | $7.52T, 87.1M jobs |
| Software developer wages | $250B, 1.69M jobs |

## Definitions — Who counts as which collar

| Collar | BLS major groups | Jobs | Share of jobs | Wages | Share of OES wages |
|---|---|---:|---:|---:|---:|
| White-collar | Management; business & financial; computer & math; architecture & engineering; life/physical/social science; community & social service; legal; education; arts & media; healthcare practitioners; sales; office & admin support | 87.1M | 56.0% | $7.52T | 69.3% |
| Blue-collar | Farming; construction & extraction; installation & repair; production; transportation & material moving | 35.2M | 22.6% | $1.95T | 18.0% |
| Pink-collar & service | Healthcare support; protective service; food prep & serving; building & grounds cleaning; personal care | 33.2M | 21.3% | $1.38T | 12.7% |

*Production and transportation are combined as the residual of the BLS total (22.2M jobs, mean $50,553). Sales and office/admin are the "routine" white-collar jobs most exposed to AI (31M jobs, $1.65T).*

## Exhibit 1 — Where every dollar of GDP goes, and how many people get it

| $ | % GDP | Group | % people | People |
|---:|---:|:---:|---:|---:|
| **$15.72T** | **50.9%** | **Paid to employees** | | |
| $7.52T | 24.3% | White-collar | 51.1% | 87.1M |
| $1.95T | 6.3% | Blue-collar | 20.6% | 35.2M |
| $1.38T | 4.5% | Pink-collar & service | 19.4% | 33.2M |
| $2.15T | 7.0% | Other: wages outside OES (bonuses, stock pay, military, farm, household) | — | — |
| $2.72T | 8.8% | Other: employer benefits & payroll taxes | — | — |
| — | — | Other employed (self-employed, farm, household) | 4.8% | 8.1M |
| — | — | Unemployed | 4.1% | 7.1M |
| **$15.19T** | **49.1%** | **Not paid as wages** | | |
| $5.06T | 16.4% | Depreciation (consumption of fixed capital) | — | — |
| $4.03T | 13.0% | Corporate profits (IVA, CCAdj) | — | — |
| $2.02T | 6.5% | Self-employed (proprietors' income) | — | — |
| $1.14T | 3.7% | Rental income of persons | — | — |
| $2.95T | 9.5% | Production taxes less subsidies, net interest, other (residual) | — | — |
| **$30.91T** | **100%** | **Total GDI / labor force** | **100%** | **170.7M** |

*Left side: GDI 2025 dollars; collar dollars are BLS OES wages (May 2025; total $10.85T), which exclude bonuses and stock pay, farms, private households, the self-employed and the military; that gap to BEA's $13.0T of wages is shown separately. Right side: the labor force; collar headcounts are OES jobs (May 2025), "other employed" is the gap to the household survey's 163.6M employed (October 2026), and unemployed/labor force are October 2026, so the people split is approximate. White-collar workers are 51% of the people and get 69% of measured wages; blue and pink-collar workers are 40% of the people and get 31%.*

## Exhibit 2 — What white-collar pay is made of

| $ | % pay | Group | % jobs | People |
|---:|---:|:---:|---:|---:|
| $1,617B | 21.5% | Management | 12.8% | 11.1M |
| $1,068B | 14.2% | Healthcare practitioners | 11.3% | 9.8M |
| $1,003B | 13.3% | Business & financial ops | 12.1% | 10.5M |
| $915B | 12.2% | Office & admin support | 20.4% | 17.8M |
| $738B | 9.8% | Sales & related | 15.4% | 13.4M |
| $615B | 8.2% | Education & library | 10.4% | 9.1M |
| **$250B** | **3.3%** | **Software developers** | **1.9%** | **1.7M** |
| $382B | 5.1% | Other computer & math | 4.1% | 3.6M |
| $280B | 3.7% | Architecture & engineering | 3.0% | 2.6M |
| $653B | 8.7% | Legal, science, social service, arts | 8.6% | 7.5M |
| **$7,522B** | **100%** | **Total white-collar** | **100%** | **87.1M** |

> Software developers: 1,687,890 jobs × $148,100 mean = **$250B**, 3.3% of white-collar pay, 2.3% of all measured wages, 0.81% of GDP, and 1% of the labor force. With QA testers (186,740 × $111,490) it is $271B, 0.88% of GDP. Loaded with employer taxes and benefits it is ~$346B, the payroll pool used in the AI developer replacement memo.

## Exhibit 3 — Which white-collar jobs AI will hit in the next 3 years (projection to late 2029, built on Goldman Sachs and ILO)

Goldman Sachs now expects AI to displace **over 9% of US workers (~15M) over a 10-year adoption period** (June 2026). Taking the first 3 years at an even pace and spreading it by each group's exposure gives **~3.2M white-collar jobs (3.7%) cut or not refilled** by late 2029, about **$269B** of annual pay. Range: 0.7M (today's measured substitution pace continues) to 5.0M (top of Goldman's 3–14% range).

| 2025 jobs | Group | Work AI can automate (GS 2023) | Cut by 2029 (base) | Range | 2029 jobs |
|---:|:---:|---:|---:|---:|---:|
| 17.8M | Office & admin support | 46% | −882K · 5.0% | 1.1–7.7% | 16.9M |
| 13.4M | Sales | 31% | −449K · 3.3% | 0.7–5.2% | 13.0M |
| 11.1M | Management | 32% | −385K · 3.5% | 0.7–5.4% | 10.7M |
| 10.5M | Business & financial | 35% | −398K · 3.8% | 0.8–5.9% | 10.1M |
| 9.8M | Healthcare practitioners | 28% | −297K · 3.0% | 0.6–4.7% | 9.5M |
| 9.1M | Education & library | 27% | −265K · 2.9% | 0.6–4.5% | 8.8M |
| **1.7M** | **Software developers** | **29%** | **−53K · 3.1%** | **0.7–4.9%** | **1.6M** |
| 3.6M | Other computer & math | 29% | −112K · 3.1% | 0.7–4.9% | 3.5M |
| 2.6M | Architecture & engineering | 37% | −105K · 4.0% | 0.9–6.2% | 2.5M |
| 7.5M | Legal, science, social service, arts | 34% | −272K · 3.6% | 0.8–5.6% | 7.2M |
| **87.1M** | **Total white-collar** | **34%** | **−3.2M · 3.7%** | **0.7M–5.0M** | **83.9M** |

> Unemployment by 2029: Goldman's own model adds 0.5 to under 1 point because most displaced workers find new jobs within a year (4.6–5.1%). If none of the 3.2M do, it reaches 6.0%.

**What the sources say**
- **Goldman Sachs (2023):** two-thirds of US jobs exposed; a quarter of work tasks automatable. White-collar groups most exposed (office/admin 46%, legal 44%, engineering 37%, business/finance 35%) vs. 1–9% for most blue-collar groups. 7% of workers fully displaced, 63% complemented, 30% unaffected.
- **Goldman Sachs, "An AI Job Apocalypse?" (June 2026):** displacement estimate raised from 6–7% (range 3–14%) to over 9% over 10 years. AI substitution already cuts ~25K jobs a month from payroll growth and added 0.16 pt to unemployment in the past year (0.1 net). Customer service and back-office roles (8–9M workers) are first in line. College-graduate unemployment 2.7% vs. 2.1% in 2019.
- **ILO (2025):** 34% of jobs in high-income countries exposed to generative AI. The highest-exposure gradient (closest to automation risk) is mostly clerical. Few jobs are fully automatable today; most will change rather than disappear.
- **Challenger, Gray & Christmas:** 121,401 AI-cited announced cuts Jan–Oct 2026, double all of 2025; most displacement shows up as roles not refilled, which these counts miss.

*Method: 3-year economy-wide displacement = Goldman's 10-year share × 3/10 (base 9% → 2.7%; high 14% → 4.2%). Low = today's measured pace (~25K/month × 36 ≈ 0.9M economy-wide). Group rate = economy-wide rate × (group exposure ÷ 25% all-industry exposure), using Goldman's 2023 US exposure by occupation group; developers use the computer & math rate; the legal/science/social/arts row is a job-weighted 34%. Normal job growth is left out to isolate the AI effect. An even pace is an assumption; adoption often starts slow and speeds up. Directional, not a forecast.*

## Exhibit 4 — What unemployment rate means recession, depression or collapse

Today: **4.1%** (October 2026; 7.07M unemployed, 170.68M labor force).

| Level | Unemployment | Evidence |
|---|---:|---|
| Normal | ~4.2–4.4% | CBO natural rate (NAIRU) |
| Recession signal | +0.5 pt | Sahm rule: 3-month average 0.5 pt above its 12-month low marks a recession start; true in every US recession since 1970. Here ≈ 4.6–4.7% |
| Typical recession | 6–11% | US peaks: 1958 7.5%, 1975 9.0%, 1982 10.8%, 2009 10.0%. Okun's law: ~2% of GDP per point above normal |
| Severe shock | 14.8% | April 2020 (COVID); absorbed with ~$5T of federal aid |
| Depression | 25–28% | US 1933 24.9% (GDP −27%); Greece 2013 27.9% (GDP −25%); Spain 2013 26.9% |
| Political collapse | ~30%+ | Germany 1932 ~30% (6M registered jobless), Weimar fell within a year. Sustained >30% only in failed or war-torn states, and chronically in South Africa (~33%) |

> The theoretical danger is the feedback loop: lost pay cuts spending, which cuts more jobs (Keynesian demand spiral); long unemployment destroys skills (hysteresis); loan and mortgage defaults then hit banks.

## Exhibit 5 — Two scenarios

Assumptions: displaced workers stay in the labor force (170.7M); no re-employment in year one. Unemployment = (7.07M + displaced) ÷ 170.68M. Lost pay = collar share of OES wages applied to BEA compensation. Knock-on (one round): unemployment insurance, savings and severance cover 35% of lost wages in year one; households spend 90% of the rest; consumer spending = 68% of GDP; remaining jobs shrink by (spending drop ÷ PCE) × 0.68.

| | Scenario 1: AI replaces all white-collar | Scenario 2: AI + robots replace white and blue-collar |
|---|---:|---:|
| Jobs lost directly | 87.1M | 122.3M |
| Unemployment, direct | **55.2%** | **75.8%** |
| Extra jobs lost from spending cuts | ~13.1M | ~8.9M |
| Unemployment, with knock-on | **~63%** | **~81%** |
| Employee pay lost (incl. benefits) | $10.9T | $13.7T |
| Share of all employee pay | 69% | 87% |
| Share of GDI | 35% | 44% |
| Wages lost (BEA basis) | $9.0T | $11.4T |
| Consumer spending, year 1 | −25% | −32% |
| Labor share of GDI | 51% → 16% | 51% → 6.5% |

> Scenario 1 is about twice the Great Depression peak. If AI kept output the same, the $10.9T would move to the owners of AI and capital, taking corporate profits from $4.0T to ~$15T. Scenario 2 leaves only pink-collar and service work (33M jobs, $1.4T), whose customers just lost their income.

### Partial replacement: how much before a crisis? (direct effect only)

| White-collar jobs replaced | Jobs | Unemployment | Comparable to |
|---|---:|---:|---|
| Software developers only | 1.7M | 5.1% | Triggers the Sahm recession signal (+1.0 pt) |
| 5% | 4.4M | 6.7% | Mild recession |
| 10% | 8.7M | 9.2% | 2009 Great Recession |
| 20% | 17.4M | 14.4% | COVID peak, 2020 |
| 30% | 26.1M | 19.5% | Between COVID and the Great Depression |
| 50% | 43.6M | 29.7% | Weimar Germany 1932 |
| 100% (Scenario 1) | 87.1M | 55.2% | No precedent |

### What decides crisis vs. transition

- **Speed.** Agriculture fell from ~40% to 2% of US jobs over a century without mass unemployment; the same shift in 5 years would look like the table above.
- **Who gets the income.** GDP need not fall, since AI can produce the output, but consumer spending (68% of GDP) is funded mostly by wages. If lost pay becomes profit, demand collapses unless it is taxed and returned to households.
- **Size of the transfer.** Keeping household income whole in Scenario 1 needs ~$9–11T a year, more than all federal spending (~$7T). White-collar workers also pay most of today's income and payroll taxes.
- **Debt.** White-collar households hold most mortgage and student debt, so their job loss hits banks harder than past blue-collar layoffs.

---

**ANALYTICAL BASIS** — GDP and GDI components: BEA NIPA via FRED, 2025 annual (GDPA $30,861B; compensation = wages and salaries $12,999B + supplements $2,720B; corporate profits with IVA/CCAdj $4,025B; proprietors' income $2,017B; rental income $1,140B; GDI $30,908B and consumption of fixed capital $5,055B are averages of 2025 quarterly SAAR values; the remaining $2,952B is the residual). Occupations and wages: BLS Occupational Employment and Wages, May 2025 (released May 15, 2026; 155,495,730 jobs, mean $69,770). Labor force: BLS Employment Situation, October 2026. Historical rates: BLS; Lebergott (US 1933); ELSTAT (Greece); INE (Spain); German Reich statistics (1932). Sahm rule: Claudia Sahm (2019). AI projection: Goldman Sachs, "The Potentially Large Effects of Artificial Intelligence on Economic Growth" (2023, https://candid.technology/wp-content/uploads/2023/03/Goldman-Sachs-300-million-jobs-automation-report.pdf) and "Generative AI Could Raise Global GDP by 7%" (https://www.goldmansachs.com/insights/articles/generative-ai-could-raise-global-gdp-by-7-percent); Goldman Sachs, "An AI Job Apocalypse?" (2026, https://www.goldmansachs.com/pdfs/insights/goldman-sachs-research/an-ai-job-apocalypse/report.pdf); ILO, "Generative AI and Jobs: A Refined Global Index of Occupational Exposure" (2025, https://www.ilo.org/publications/generative-ai-and-jobs-refined-global-index-occupational-exposure). Natural rate: CBO. Figures are directional estimates for structural analysis, not forecasts; the collar boundaries are a judgment call and each group is shown so it can be reassigned.

**FRAMEWORKS APPLIED** — Income-side GDP (GDI) decomposition · Occupational wage-bill sizing (employment × mean wage) · Collar segmentation · Historical unemployment benchmarking · Sahm rule · Okun's law · Keynesian demand multiplier (one round) · Hysteresis · Labor share of income.
