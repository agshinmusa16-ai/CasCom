# Cassaria Commodity — CasCom
### Quantitative Portfolio Research | Capped Risk Parity

---

## What is CasCom?

**Cassaria Commodity (CasCom)** is a systematic, rules-based commodity portfolio constructed on April 14, 2025 as a direct response to rising tariff risks and global trade uncertainty.

The thesis is simple: **real assets outperform when tariff-driven inflation and supply chain disruption threaten paper assets.** Gold, silver, copper miners, agriculture, and oil act as natural hedges in an inflationary/deglobalisation regime.

This is not an all-weather fund. It is a directional bet — built for a specific macro environment, with documented limitations for deflationary panics.

---

## Live Performance (Apr 2025 — Apr 2026)

| Metric | Value |
|--------|-------|
| CasCom Return | **+52.72%** |
| SPY Return | +28.72% |
| Raw Alpha vs SPY | **+24.00 pp** |
| Portfolio Beta | 0.50 |
| Jensen's Alpha (5Y) | +7.06% |
| OOS Sharpe (net costs) | 2.54 |
| Max Drawdown (5Y) | -18.67% |
| Copula MC Median 1Y Return | +20.86% |
| Prob. Positive Return (MC) | 89.6% |

*Live portfolio tracked on Yahoo Finance Paper Trading — $1,012,662 → $1,545,542 (+52.62%)*

---

## Portfolio — 10 Assets

| Ticker | Name | Class | Weight |
|--------|------|-------|--------|
| DBA | Invesco DB Agriculture ETF | Commodity | 22.55% |
| IAU | iShares Gold Trust | Metals | 19.00% |
| SPY | SPDR S&P 500 ETF Trust | Equity Index | 14.81% |
| PPLT | abrdn Physical Platinum Shares | Metals | 8.11% |
| USO | United States Oil Fund | Commodity | 7.69% |
| SLV | iShares Silver Trust | Metals | 7.17% |
| BHP | BHP Group Limited | Mining | 6.36% |
| SHY | iShares 1-3 Year Treasury Bond ETF | Bond | 6.00% |
| TECK | Teck Resources Limited | Mining | 4.20% |
| FCX | Freeport-McMoRan Inc. | Mining | 4.12% |

---

## Weighting Model — Capped Risk Parity (CRP)

Six models were tested via rolling out-of-sample backtest (3Y train, quarterly rebalance, net 10bps transaction costs):

| Model | Ann. Return | Volatility | Net Sharpe |
|-------|-------------|------------|------------|
| Mean-Variance | 16.88% | 9.56% | 1.65 |
| Capped Mean-Variance | 15.20% | 7.80% | 2.19 |
| Black-Litterman | 13.08% | 6.81% | 0.19 |
| Risk Parity | 12.84% | 4.71% | 2.53 |
| **Capped Risk Parity ★** | **15.85%** | **6.24%** | **2.11** |
| Hierarchical Risk Parity | 10.36% | 5.72% | 1.68 |

**CRP selected:** Risk Parity with SHY bond capped at 6%. Uncapped RP allocates ~40% to SHY — contradicting the commodity thesis. The 0.03 Sharpe sacrifice is negligible; the mandate improvement is not.

---

## What's Inside

```
📁 CasCom/
├── CasCom Research Report.pdf  # 33-page research report
├── CasCom_final.ipynb          # Full analysis notebook (VS Code)
├── LICENCE
├── README.md
```

### Notebook Contents

| Section | Description |
|---------|-------------|
| Data Pipeline | yfinance download, cleaning, returns |
| Asset Selection | Correlation filter, Decay Sharpe (λ=0.9945), thesis filter |
| 6 Weighting Models | MVO, BL, RP, CRP, CMV, HRP |
| Rolling Backtest | 3Y train, quarterly OOS, net 10bps costs |
| Beta Analysis | vs SPY and vs VIX (fear sensitivity) |
| Jensen's Alpha | OLS regression, 5Y and live period |
| Drawdown Analysis | Max DD, recovery, top 5 periods |
| GARCH(1,1) | All assets + portfolio, walk-forward backtest |
| VaR & CVaR | Historical, Parametric, Monte Carlo — 95% & 99% |
| Dynamic GARCH-VaR | Kupiec & Christoffersen backtests |
| Factor Model | 5-factor OLS, R²=93.9% |
| Regime Switching | 2-state HMM (Bull/Bear) |
| Copula Monte Carlo | t-Copula, 10,000 simulations, walk-forward validation |
| Stress Testing | COVID crash, 2022 rate shock, 2025 tariff shock |
| Sensitivity Analysis | SHY cap, weight perturbation, lambda, correlation cutoff |
| Live Performance | Apr 2025 — Apr 2026 vs SPY |
| Summary Dashboard | All key metrics in one view |

---

## Key Results

**Factor Model (R² = 93.9%):** CasCom is fundamentally a precious metals portfolio.
Silver and Gold are the top two return drivers. 60% of portfolio variance is unexplained
by the market — confirming genuine diversification.

**Regime Switching (HMM):** Portfolio spends 98.9% of time in Bull regime.
Current state: Bull (86.3% probability) as of April 2026.

**Copula Monte Carlo:** Median 1-year forward return +20.86%.
Probability of loss >10%: only 2.27%.

**Stress Tests:**
- COVID crash: -25% (vs SPY -34%) — known weakness, deflation not CasCom's environment
- 2022 rate shock: +15% (vs SPY -20%) — thesis validated
- 2025 tariff shock: -9% (vs SPY -14%) — origin scenario, recovered faster

---

## Setup

```bash
pip install yfinance pandas numpy matplotlib seaborn scipy arch hmmlearn statsmodels
```

Data is downloaded automatically via `yfinance` — no manual data files needed to reproduce the analysis.

---

## AI Declaration

Python code was generated with AI assistance (Claude by Anthropic).
Document layout and structure were produced with AI assistance.
All investment decisions, asset selection, model selection, thesis development,
and result interpretation are the author's own work.

---

## License

© 2026 Agshin Musayev. All rights reserved.

This repository is shared strictly for educational and research purposes. Commercial use, redistribution, or repackaging of this strategy without explicit written permission is not permitted.

Disclaimer: This software is provided "as is" without warranty of any kind. The author is not responsible for any financial losses or damages. This is not financial advice.

---

*CasCom is not investment advice. Past performance does not guarantee future results.*
