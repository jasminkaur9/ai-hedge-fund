# Investment Thesis: Tariff Regime Shift & the AI-Hedge-Fund Framework

**Author:** Jasmin Kaur
**Date:** 2026-02-23
**Course:** MGMT 69000 — Mastering AI for Finance

---

## The Macro Regime Shift

We are living through the largest US trade policy reversal since WWII. The average effective tariff rate jumped from **2.4% (2024) to 7.7% (2025)** — the highest since 1947. On Feb 20, 2026, the Supreme Court struck down IEEPA tariffs (6-3 ruling), but the administration immediately pivoted to Section 122, imposing a 10% global tariff effective Feb 24, 2026.

This isn't a one-off event — it's a **regime shift**. The rules of global trade that held for 30+ years are being rewritten in real-time.

### Key Numbers
- China effective tariff rate: **~10% → ~45%** (peak mid-2025)
- Average household tax increase from tariffs: **~$1,000/year** (2025)
- 53% of US firms report **increased reshoring activity**
- 61% of affected companies **switched suppliers in Q1 2026 alone**
- Pharma tariffs potentially rising to **200% by late 2026**

---

## Winners and Losers

### Tariff Winners (Long Candidates)
| Sector | Why | Tickers |
|--------|-----|---------|
| **Domestic Steel** | Foreign competition priced out; Nucor seeing margin expansion | NUE, CLF |
| **US Semiconductors** | CHIPS Act + tariffs on imported chips; Intel foundry business benefits | INTC |
| **Domestic Pharma** | Companies pledging US plant expansions get tariff waivers | PFE, LLY |
| **US Automakers** | Shielded from Hyundai/Kia competition (Hyundai net profit -18%) | F, GM |
| **Defense/Industrials** | Reshoring trend + domestic manufacturing preference | LMT, GD, CAT |

### Tariff Losers (Short Candidates)
| Sector | Why | Tickers |
|--------|-----|---------|
| **Foreign Automakers** | Hyundai/Kia facing 18% profit cut in 2026 | HYMTF |
| **China-Dependent Retailers** | 45% tariffs on Chinese imports crush margins | Low-cost importers |
| **Global Supply Chain Firms** | Disruption from 61% supplier switching rate | Companies with heavy China exposure |

---

## Connecting to the AI-Hedge-Fund Framework

The AI-Hedge-Fund's multi-agent architecture is **uniquely suited** for this regime-shift environment. Here's how:

### 1. Agent Diversity = Regime-Shift Resilience

The system's 18 agents represent **different investing philosophies**, and they disagree — that's the point. In a regime shift:

- **Stanley Druckenmiller Agent** — The macro agent. Built to detect exactly this kind of macro regime change. His focus on "asymmetric risk-reward" and "top-down analysis" makes him the most relevant agent for tariff plays.
- **Michael Burry Agent** — The contrarian. When the market overreacts to tariff headlines (both panic-selling and euphoria), Burry's deep-value approach finds mispricings.
- **Cathie Wood Agent** — The disruption agent. Identifies companies that benefit from forced innovation (reshoring drives automation/robotics investment).
- **Warren Buffett Agent** — The moat agent. Companies with pricing power can pass tariff costs to consumers. Buffett's moat analysis identifies who survives vs. who gets squeezed.

### 2. Proposed Enhancement: Tariff Exposure Score

The current agents analyze fundamentals, sentiment, and technicals — but none explicitly model **tariff exposure**. A new data dimension could be added:

```
Tariff Exposure Score = f(
    % revenue from imports,
    % COGS from tariffed materials,
    domestic manufacturing capacity,
    supply chain diversification index,
    pricing power (ability to pass costs)
)
```

This score could feed into every agent's analysis, giving the system an edge that pure fundamentals miss.

### 3. The Consensus Mechanism Matters More Now

In stable markets, most agents agree. In regime shifts, **disagreement is the signal**. When the Druckenmiller agent says "bullish" on steel but the Fundamentals agent says "bearish" (because P/E looks stretched), that tension is valuable information.

The Portfolio Manager's job of synthesizing conflicting signals becomes critical — it's the difference between catching the reshoring trade early and getting whipsawed by policy reversals.

### 4. Backtesting Against Policy Dates

The backtester (`src/backtesting/`) could be run with start/end dates aligned to key policy events:

| Period | Event | Test Hypothesis |
|--------|-------|-----------------|
| 2024-11-01 to 2025-02-01 | Post-election, pre-tariff | Did agents position for tariffs? |
| 2025-04-01 to 2025-06-01 | "Liberation Day" tariffs | How did agents react to the shock? |
| 2026-02-20 to 2026-03-01 | Supreme Court IEEPA ruling | Did agents adapt to the reversal? |

---

## The Core Thesis

**In a tariff regime shift, the AI-Hedge-Fund's multi-agent disagreement is a feature, not a bug.**

Traditional quant models trained on 30 years of free-trade data will break. But a system where a Druckenmiller macro agent, a Burry contrarian agent, and a Buffett moat agent each independently analyze the same stocks creates a **built-in regime-shift detector**.

**The trade:**
- **Long** domestic manufacturers with pricing power (NUE, LLY, INTC)
- **Short** foreign-dependent companies with thin margins (HYMTF, China-exposed retailers)
- **Use the export feature** (`--export`) to build a timestamped audit trail of how agent consensus shifts as policy evolves

**The edge:** Most hedge funds use one model. This system uses 18 independent perspectives that naturally capture the disagreement that *is* the regime shift.

---

## Sources

- [St. Louis Fed: Shifting US Import Landscape](https://www.stlouisfed.org/on-the-economy/2026/jan/shifting-us-import-landscape-recent-changes-tariffs-trade)
- [J.P. Morgan: US Tariffs Impact](https://www.jpmorgan.com/insights/global-research/current-events/us-tariffs)
- [Tax Foundation: Trump Tariffs Trade War](https://taxfoundation.org/research/all/federal/trump-tariffs-trade-war/)
- [Morgan Lewis: Key Shifts in 2025](https://www.morganlewis.com/pubs/2026/01/us-international-trade-and-investment-key-shifts-in-2025-and-what-businesses-should-know-for-2026)
- [Euromonitor: Tariff Winners and Losers](https://www.euromonitor.com/article/trumps-new-tariffs-in-effect-winners-losers-and-what-comes-next)
- [SupplyChainBrain: Reshoring Trends 2025](https://www.supplychainbrain.com/blogs/1-think-tank/post/41852-how-tariffs-are-reshaping-global-supply-chains-in-2025)
- [Congress.gov: Presidential Tariff Actions Timeline](https://www.congress.gov/crs-product/R48549)
- [Equitable Growth: Business Impact 2026](https://equitablegrowth.org/u-s-businesses-report-that-tariff-policies-will-likely-lead-to-price-increases-and-labor-market-impacts-in-2026/)
