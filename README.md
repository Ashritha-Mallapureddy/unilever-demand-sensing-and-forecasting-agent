# 🟣 Unilever Demand Sensing Agent

An AI-powered demand sensing dashboard built for Unilever FMCG supply chain management. Demonstrates how real-time POS data and Holt-Winters forecasting replace 30-day batch replenishment, reducing Out-of-Stock rates by **68.9%** and recovering **£235,619** in revenue over 52 weeks.

## 🔗 Live Demo

**[Open the Live App →](https://ashritha-mallapureddy.github.io/unilever-demand-sensing/)**

> Fully interactive — no installation needed. Runs entirely in the browser.

---

## ✨ Features

| Feature | Description |
|---|---|
| **AI Forecasting** | Holt-Winters Triple Exponential Smoothing (α, β, γ grid search, m=52 weekly seasonality) |
| **8 Unilever SKUs** | Dove, Hellmann's, Lipton, Domestos, Knorr, Lynx, Surf Excel, Magnum |
| **POS Signal Input** | Real-time demand ingestion with promotional, stockout & seasonal presets |
| **Auto-Order Log** | Exception-triggered replenishment at >10% divergence threshold |
| **Document Upload** | Upload demand plans, POS reports, retailer forecasts (CSV, XLSX, PDF, DOCX) |
| **Weather Impact** | Temperature–demand elasticity for FMCG categories + 7-day forecast alerts |
| **Analytics Tabs** | OOS Analysis · Bullwhip Effect · Forecast Accuracy · Order Log · Weather Impact |

---

## 📊 Key Results

| Metric | Push (Batch) | AI Pull (This Agent) | Improvement |
|---|---|---|---|
| OOS Rate | 4.85% | 1.51% | **−68.9%** |
| Forecast MAPE | 23% | 5.1% | **−78%** |
| Response Time | 720 hours | 2.7 hours | **−99.6%** |
| Safety Stock | 38 days | 19 days | **−50%** |
| Revenue Recovered | — | £235,619 | **73,631 units saved** |

---

## 🌦️ Weather–Demand Integration

Weather knowingly and unknowingly affects demand sensing forecasting:

| Category | Driver | Elasticity |
|---|---|---|
| Ice Cream / Magnum | Temperature ↑ | +2.8% per °C above 12°C |
| Hot Beverages / Lipton | Temperature ↑ | −1.9% per °C above 15°C |
| Soups / Knorr | Cold front ↓ | −2.1% per °C above 10°C |

Weather signals give the agent a **7–14 day anticipatory advantage**, pre-triggering stock before shelves empty.

---

## 📁 Repository Structure

```
unilever-demand-sensing/
├── index.html                 # Live interactive dashboard (GitHub Pages)
├── data/
│   └── demand_data.csv        # 52-week simulated POS data for 8 SKUs
├── pipeline/
│   ├── app.py                 # Streamlit live agent prototype
│   └── generate_data.py       # Data generation script
└── README.md
```

---

## 🚀 Run Locally (Streamlit)

```bash
pip install streamlit pandas numpy plotly
streamlit run pipeline/app.py
```

---

## 📚 Academic References

- **Lee, Padmanabhan & Whang (1997)** — "The Bullwhip Effect in Supply Chains", *Management Science*, 43(4), 546–558
- **Holt (1957)** — "Forecasting Seasonals and Trends by Exponentially Weighted Moving Averages"
- **Winters (1960)** — "Forecasting Sales by Exponentially Weighted Moving Averages", *Management Science*
- **VICS CPFR (2004)** — Collaborative Planning, Forecasting & Replenishment framework
- **NielsenIQ (2022)** — "State of Retail Availability"
- **ECR Europe (2018)** — Out-of-Stock Benchmark Study

---

## 🏢 Context

Built as a demonstration for **Unilever FMCG** supply chain optimization, showing how demand sensing with AI replaces traditional push-based batch forecasting with real-time pull replenishment.

---

*Built with Holt-Winters Triple Exponential Smoothing · Pure HTML/CSS/JS · No external dependencies*
