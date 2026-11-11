# Unilever Demand Sensing Agent

An AI-powered demand sensing dashboard for Unilever FMCG supply chain management. Real-time POS signals and Holt-Winters forecasting replace 30-day batch replenishment, reducing out-of-stock rates by **68.9%** and recovering **£235,619** over 52 weeks.

The live dashboard is [https://ashritha-mallapureddy.github.io/unilever-demand-sensing/](https://ashritha-mallapureddy.github.io/unilever-demand-sensing/). It runs entirely in the browser from `index.html`.

## Features

| Feature | Description |
|---|---|
| AI forecasting | Holt-Winters triple exponential smoothing (α, β, γ grid search, weekly seasonality) |
| 8 Unilever SKUs | Dove, Hellmann's, Lipton, Domestos, Knorr, Lynx, Surf Excel, Magnum |
| POS signal input | Promotional, stockout, and seasonal presets |
| Auto-order log | Replenishment when forecast divergence exceeds 10% |
| Document upload | Demand plans and POS reports (CSV, XLSX, PDF, DOCX) |
| Weather impact | Temperature–demand elasticity and a 7-day forecast |
| Analytics | OOS, bullwhip, forecast accuracy, order log, weather |

## Key results

| Metric | Push (batch) | AI pull | Improvement |
|---|---|---|---|
| OOS rate | 4.85% | 1.51% | −68.9% |
| Forecast MAPE | 23% | 5.1% | −78% |
| Response time | 720 hours | 2.7 hours | −99.6% |
| Safety stock | 38 days | 19 days | −50% |
| Revenue recovered | — | £235,619 | 73,631 units saved |

## Run locally

```bash
npm install
npm run dev
```

The dev server listens on `http://127.0.0.1:4178`.

The Streamlit prototype uses the same demand data:

```bash
pip install streamlit pandas numpy plotly
streamlit run pipeline/app.py
```

`pipeline/generate_data.py` rebuilds `data/demand_data.csv`.

## Repository

```
index.html                      Browser dashboard published to GitHub Pages
data/demand_data.csv            52-week simulated POS data for 8 SKUs
pipeline/app.py                 Streamlit prototype
pipeline/generate_data.py       Data generation script
```

## GitHub Pages

GitHub Pages serves this repository from the `main` branch. A push to `main` publishes the dashboard.

## References

- Lee, Padmanabhan & Whang (1997), "The Bullwhip Effect in Supply Chains", *Management Science*, 43(4), 546–558
- Holt (1957), "Forecasting Seasonals and Trends by Exponentially Weighted Moving Averages"
- Winters (1960), "Forecasting Sales by Exponentially Weighted Moving Averages", *Management Science*
- VICS CPFR (2004); NielsenIQ (2022); ECR Europe (2018)
