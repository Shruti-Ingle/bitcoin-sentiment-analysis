<a href="https://colab.research.google.com/github/Shruti-Ingle/bitcoin-sentiment-analysis/blob/main/bitcoin_sentiment_analysis.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" width="250"/>
</a>

Analyze Bitcoin sentiment using NLP and machine learning techniques.
[Do not run any code]
# 📊 Bitcoin Market Sentiment × Trader Performance Analysis

> Exploring how the Fear & Greed Index shapes trading behaviour and profitability on Hyperliquid.

---

## 🗂️ Repository Structure

```
├── bitcoin_sentiment_analysis.ipynb   ← Main analysis notebook (run this)
├── historical_data.csv                ← Hyperliquid trader data (211K trades)
├── fear_greed_index.csv               ← Daily Fear & Greed Index (2018–2025)
├── summary_pnl_by_sentiment.csv       ← PnL stats per sentiment class
├── summary_top_traders.csv            ← Top 20 trader leaderboard
├── summary_top_coins.csv              ← Top 15 coins by volume & PnL
├── summary_contrarian_strategy.csv    ← "Buy Fear" strategy metrics
└── README.md
```

---

## 📦 Datasets

| Dataset | Rows | Columns | Period |
|---|---|---|---|
| Hyperliquid Trades | 211,224 | 16 | Jan–Dec 2024 |
| Fear & Greed Index | 2,644 | 4 | Feb 2018–May 2025 |

**Trade columns:** Account, Coin, Execution Price, Size USD, Side, Direction, Closed PnL, Fee, Timestamp IST, …  
**FG Index columns:** date, value (0–100), classification

---

## 🔬 Analysis Sections

| # | Section | What It Covers |
|---|---|---|
| 1 | Imports & Setup | Libraries, dark theme styling, sentiment colour palette |
| 2 | Load & Preview | Shape, dtypes, sample rows |
| 3 | Cleaning & Merge | Date parsing, joining trades ↔ sentiment, feature engineering |
| 4 | EDA | FG distribution, trade volume/count/size by sentiment |
| 5 | PnL vs Sentiment | Win rate, avg PnL, total PnL, boxplot by classification |
| 6 | Long/Short Bias | Directional trade breakdown across sentiment regimes |
| 7 | Top Trader Analysis | Leaderboard, per-sentiment PnL breakdown for top 5 |
| 8 | Time Series | Daily PnL rolling average overlaid with FG index, 2024 |
| 9 | Coin Analysis | Top 15 coins by volume and realised PnL |
| 10 | Liquidations | Forced liquidations & large losses clustered by sentiment |
| 11 | Correlation | Heatmap — execution price, size, PnL, fees vs FG value |
| 12 | Temporal Patterns | Win rate & volume by day-of-week and hour-of-day (IST) |
| 13 | Contrarian Strategy | "Buy Fear / Sell Greed" simulation on long-closing trades |
| 14 | Key Findings | Narrative summary of 6 insights + strategy table |
| 15 | Export | Summary CSVs |

---

## 💡 Key Findings

1. **Greed = Volume** — Trade activity peaks in Greed/Extreme Greed phases (momentum-chasing).  
2. **Extreme Fear = Best avg PnL per trade** — Contrarian entries during fear yield higher per-trade gains.  
3. **Persistent long bias** — 60%+ of directional trades are longs *even* in Extreme Fear.  
4. **Top traders profit in Greed, survive in Fear** — Elite accounts stay positive across all sentiments.  
5. **Liquidations cluster at Extreme Fear** — Over-leveraged longs get wiped at sentiment lows.  
6. **Best hours: 14:00–18:00 IST** — Overlaps European session open; lowest win rates 00:00–06:00 IST.

### Sentiment-Aware Sizing Guide
| Sentiment | Index Range | Suggested Stance |
|---|---|---|
| Extreme Fear | < 25 | Reduce leverage; watch for capitulation reversal |
| Fear | 25–45 | Cautious longs, tight stops, contrarian setups |
| Neutral | 45–55 | Normal sizing, trend-following |
| Greed | 55–75 | Scale in with trend, tighten exits |
| Extreme Greed | > 75 | Reduce size, book profits, watch for reversal |

---

## ⚙️ How to Run

```bash
# 1. Clone the repo
git clone https://github.com/YOUR_USERNAME/bitcoin-sentiment-analysis.git
cd bitcoin-sentiment-analysis

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# 3. Launch the notebook
jupyter notebook bitcoin_sentiment_analysis.ipynb
```

> **Tip:** Run all cells top-to-bottom (`Kernel → Restart & Run All`). All charts save as `.png` files automatically.

---

## 🛠️ Dependencies

```
pandas >= 1.5
numpy >= 1.23
matplotlib >= 3.6
seaborn >= 0.12
jupyter / nbconvert
```

---

*Assignment submission — Hyperliquid trading data analysis.*
