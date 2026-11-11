# If AI replaces office workers, who still gets paid from GDP?

**Artifact:** https://claude.ai/artifact/4yNsP3SkphqqC6PKTUPsKB
**Related memos:** [AI developer replacement (USA)](../research/ai-developer-replacement-usa.md) · [AI developer agents, independent view](../research/ai-developer-agents-independent-usa.md)

*Macro note, not a business teardown memo. It lives in `reports/` so it stays out of `research/compare.md`. US data for 2025; labor force as of October 2026.*

> About half of US national income comes back to people as pay. White-collar workers take 69% of the measured wage bill, about a quarter of all GDP. Software developers are only 3.3% of white-collar pay, or 0.8% of GDP.

| Key figure | Value |
|---|---|
| US GDP 2025 | $30.86T (GDI, income side: $30.91T) |
| Paid to employees (wages + benefits) | $15.72T, 51% of GDI |
| White-collar wages | $7.52T, 87.1M jobs |
| Software developer wages | $250B, 1.69M jobs |

## Exhibit 1 — Where every dollar of GDP goes (GDI 2025)

| Slice | $ | % of GDI |
|---|---:|---:|
| **Paid to employees** | **$15.72T** | **50.9%** |
| White-collar wages | $7.52T | 24.3% |
| Blue-collar wages | $1.95T | 6.3% |
| Pink-collar & service wages | $1.38T | 4.5% |
| Other: wages outside OES (bonuses, stock pay, military, farm, household) | $2.15T | 7.0% |
| Other: employer benefits & payroll taxes | $2.72T | 8.8% |
| **Not paid as wages** | **$15.19T** | **49.1%** |
| Depreciation (consumption of fixed capital) | $5.06T | 16.4% |
| Corporate profits (IVA, CCAdj) | $4.03T | 13.0% |
| Self-employed (proprietors' income) | $2.02T | 6.5% |
| Rental income of persons | $1.14T | 3.7% |
| Production taxes less subsidies, net interest, other (residual) | $2.95T | 9.5% |
| **Total GDI** | **$30.91T** | **100%** |

*Collar slices are BLS OES wages (employment × annual mean wage, May 2025; total $10.85T). OES excludes bonuses and stock pay, farms, private households, the self-employed and the military; that gap to BEA's $13.0T of wages is shown separately.*

### Collar definitions

| Collar | BLS major groups | Jobs | Share of jobs | Wages | Share of OES wages |
|---|---|---:|---:|---:|---:|
| White-collar | Management; business & financial; computer & math; architecture & engineering; life/physical/social science; community & social service; legal; education; arts & media; healthcare practitioners; sales; office & admin support | 87.1M | 56.0% | $7.52T | 69.3% |
| Blue-collar | Farming; construction & extraction; installation & repair; production; transportation & material moving | 35.2M | 22.6% | $1.95T | 18.0% |
| Pink-collar & service | Healthcare support; protective service; food prep & serving; building & grounds cleaning; personal care | 33.2M | 21.3% | $1.38T | 12.7% |

*Production and transportation are combined as the residual of the BLS total (22.2M jobs, mean $50,553). Sales and office/admin are the "routine" white-collar jobs most exposed to AI (31M jobs, $1.65T).*

## Exhibit 2 — What white-collar pay is made of

| Group | Wages | % of white-collar | % of GDP |
|---|---:|---:|---:|
| Management | $1,617B | 21.5% | 5.24% |
| Healthcare practitioners | $1,068B | 14.2% | 3.46% |
| Business & financial ops | $1,003B | 13.3% | 3.25% |
| Office & admin support | $915B | 12.2% | 2.97% |
| Sales & related | $738B | 9.8% | 2.39% |
| Education & library | $615B | 8.2% | 1.99% |
| **Software developers** | **$250B** | **3.3%** | **0.81%** |
| Other computer & math | $382B | 5.1% | 1.24% |
| Architecture & engineering | $280B | 3.7% | 0.91% |
| Legal | $182B | 2.4% | 0.59% |
| Community & social service | $169B | 2.2% | 0.55% |
| Arts, design, media | $163B | 2.2% | 0.53% |
| Life, physical & social science | $139B | 1.9% | 0.45% |
| **Total white-collar** | **$7,522B** | **100%** | **24.4%** |

> Software developers: 1,687,890 jobs × $148,100 mean = **$250B**, 3.3% of white-collar pay, 2.3% of all measured wages, 0.81% of GDP. With QA testers (186,740 × $111,490) it is $271B, 0.88% of GDP. Loaded with employer taxes and benefits it is ~$346B, the payroll pool used in the AI developer replacement memo.

## Exhibit 3 — What unemployment rate means recession, depression or collapse

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

## Exhibit 4 — Two scenarios

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

**ANALYTICAL BASIS** — GDP and GDI components: BEA NIPA via FRED, 2025 annual (GDPA $30,861B; compensation = wages and salaries $12,999B + supplements $2,720B; corporate profits with IVA/CCAdj $4,025B; proprietors' income $2,017B; rental income $1,140B; GDI $30,908B and consumption of fixed capital $5,055B are averages of 2025 quarterly SAAR values; the remaining $2,952B is the residual). Occupations and wages: BLS Occupational Employment and Wages, May 2025 (released May 15, 2026; 155,495,730 jobs, mean $69,770). Labor force: BLS Employment Situation, October 2026. Historical rates: BLS; Lebergott (US 1933); ELSTAT (Greece); INE (Spain); German Reich statistics (1932). Sahm rule: Claudia Sahm (2019). Natural rate: CBO. Figures are directional estimates for structural analysis, not forecasts; the collar boundaries are a judgment call and each group is shown so it can be reassigned.

**FRAMEWORKS APPLIED** — Income-side GDP (GDI) decomposition · Occupational wage-bill sizing (employment × mean wage) · Collar segmentation · Historical unemployment benchmarking · Sahm rule · Okun's law · Keynesian demand multiplier (one round) · Hysteresis · Labor share of income.
