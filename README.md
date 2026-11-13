# eRes
My research on  Energy Resilience through Renewables, on how electrification and domestic clean power could reduce India’s exposure to oil shocks. It is a work in progress and under review, so its figures and conclusions may change.

> **Status: work in progress · under review.** More analysis, data and detail are being added, and the figures and conclusions may change in later versions.

## The question

India imports most of its energy. In 2024-25 it imported about **89% of its crude oil, half of its natural gas and a quarter of its coal**. This makes our economy vulnerable to events it cannot control. The 2026 Strait of Hormuz crisis showed this clearly: India's crude basket peaked near $157 a barrel and the rupee fell to about 94 per dollar. Extra fossil-fuel import costs reached about $22 billion between March and August 2026.

This project evaluates if **electrifying the economy and generating that electricity from renewable/non-traditional sources** (sunlight, wind and, over time, nuclear) can protect India's economy as well as its climate.

## The central idea: buying fuel vs investing in technology

- **Fuel is a flow.** It is burned once and must be bought again every day, at whatever price the world market sets.
- **Equipment is a stock.** A solar panel is bought once and produces electricity for about 25 years, whatever happens to fuel prices.

Here is a worked example. 1 GW of solar in India produces about 1.62 TWh a year. Over 25 years, allowing for panels losing 0.5% of output a year, that totals about **38 TWh**, the sum of a geometric series. Producing the same electricity from imported LNG would cost **$3.1–8.8 billion** in fuel. The solar hardware costs about **$0.10–0.12 billion**, or 1–4% of the fuel it replaces.

## Key findings so far

1. **Energy imports are a large, recurring cost.** India's gross fossil-fuel import bill is roughly 5% of GDP.
2. **Clean power is now cheaper than new coal.** Solar plus batteries, available at peak times, has been contracted at **₹5.25/kWh for 25 years**. New coal costs ₹5.38–6.30/kWh.
3. **Coal gets more expensive as it runs less.** A coal plant's average cost per unit is a hyperbola in its utilisation: `AC = v + F / (8,760 × PLF)`. At 69% utilisation coal costs about ₹4.80/kWh. At 55% it rises to ₹5.28, and at 40% to ₹6.18.

 <img width="1280" height="680" alt="coal_average_cost" src="https://github.com/user-attachments/assets/1d8d5938-7fd3-4f43-9022-a02d8a2f6b98" />


   *Figure 1. Average cost of coal electricity against plant load factor. The fuel cost per unit stays flat, but the average cost rises steeply as the plant runs less. Author's calculation based on Ember data.*
4. **The outcome depends on how fast India builds.** In the scenario model, a high-ambition path cuts coal's share of electricity from 71% to about **15% by 2047**. Its average generation cost ends about **17% lower** than a stalled path. A stalled path would need roughly **150–600 GW of new coal** (central estimate about 380 GW).
5. **The bottlenecks are the grid and manufacturing, not generation cost.** About 470 GWh of renewable power was curtailed in January–March 2026. India still imports about 100% of its polysilicon and 98% of its solar wafers.

## Scenario model

A year-by-year Python model, 2025–2047. Clean supply = capacity × capacity factor. Coal fills the remaining demand. The model then computes cost, emissions and the oil saved by electric vehicles.

| Result in 2047 | Stalled | Current policy | Electrotech |
|---|---|---|---|
| Coal share of electricity (71% in 2025) | 64% | 46% | 15% |
| Average generation cost (₹/kWh) | 4.55 | 4.23 | 3.76 |
| New coal needed beyond today's pipeline | ≈380 GW | ≈240 GW | 0 |
| Oil saved by EVs, 2025–2047 | 4.1 bn bbl | 7.9 bn bbl | 12.1 bn bbl |

These are projections that depend on the model's assumptions, not forecasts.

<img width="1280" height="680" alt="coal_generation_scenarios" src="https://github.com/user-attachments/assets/57efe68f-f971-4570-a4e3-1512cc576f21" />


*Figure 2. Coal electricity generation under the three scenarios. At today's pace coal generation roughly doubles by 2047; only the high-ambition path makes it decline. Author's scenario model.*

## Oil → inflation regression (first results)

The white paper describes this study as *designed but not yet carried out*. Results are preliminary 

**Method.** Monthly data, Jan 2013 – Sep 2026. Each price index is regressed on the current and previous six months' changes in the rupee price of India's crude basket. The controls are past inflation, month effects and RBI repo-rate changes. The **sum of the oil coefficients** is the pass-through: the share of a crude-price change that reaches each price within seven months.


**What this shows.** Oil shocks reach **wholesale** fuel prices almost fully. They reach **pump** prices only partly, and since 2022 not at all. Because petrol and diesel are only about 2.3% of the consumer basket, headline inflation barely moves. During the 2026 crisis, the cost was absorbed largely by state oil companies, through an excise-duty cut, and by businesses paying market prices for fuel. Consumer prices took little of it. This is lower than the RBI research estimate quoted in the paper (about 20 bps per 10%), which assumes the shock fully reaches retail fuel prices.

**Data.** Every series was checked against published figures, for example CPI inflation of 5.54% and WPI inflation of 11.39% in September 2026, and RBI's core inflation of 4.2% in August 2026. Sources:
- **Prices:** MoSPI CPI and WPI.
- **Repo rate:** RBI Handbook of Statistics, Table 40.
- **Crude and exchange rate:** FRED (IMF/EIA crude, INR/USD) and PPAC (Indian crude basket).



## Next steps (being worked on)
- Oil → inflation regression
- Further Grid Analaysis

## Main sources

Ember (2026) on India's transition, coal costs and transmission. MoSPI *Energy Statistics India 2026*. CREA (2026) on the cost of the Hormuz crisis. RBI Bulletin (Jul 2025) on oil and inflation. PIB (2026) on solar manufacturing. CERC (2025) on grid frequency. The full reference list is in the white paper.
