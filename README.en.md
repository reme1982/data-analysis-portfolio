🇲🇽 [Versión en español](README.md)

# Data Analysis Portfolio — Hector Cárdenas

**Data and football analyst · Scouting and tactical analysis**

Eight business cases solved end to end with Python and SQL. Each project follows a 5-day assignment format: data audit, cleaning, surface ranking, discovery of the key insight, control of confounding variables, and an executive one-pager with visualizations. The common question: **does the metric shown on the dashboard (volume, revenue, occupancy) match the one that actually makes money?**

## Projects

Each project folder contains a `README.md` (Spanish) and a `README.en.md` (English). Notebooks are in Spanish.

| # | Project | Sector | Description | Folder |
|---|---|---|---|---|
| 1 | **BrightCart** | Retail / Fashion e-commerce | Real profitability of a sale campaign after returns and reverse logistics. | [`brightcart/`](brightcart/) |
| 2 | **AulaViva** | EdTech / Online courses | Value and LTV by acquisition channel: completion, renewal and value share. | [`aulaviva/`](aulaviva/) |
| 3 | **Ampara** | Insurance | Technical profitability by channel: Loss Ratio, Combined Ratio, renewal and margin. | [`ampara/`](ampara/) |
| 4 | **El Mirador** | Hospitality | Occupancy → ADR → RevPAR → GOPPAR ladder by hotel and sales channel. | [`elmirador/`](elmirador/) |
| 5 | **PlayLoop** | Mobile gaming (F2P) | Cohort retention, level funnel, ROAS/LTV by channel and churn model. | [`playloop/`](playloop/) |
| 6 | **NidoHogar** | Real-estate portal (proptech) | Visit → contact → contract funnel and the real effect of featured listings. | [`nidohogar/`](nidohogar/) |
| 7 | **VueltaFit** | Fitness / Gyms | Annual vs. monthly plan: renewal, survivorship bias and the first-21-days habit. | [`vueltafit/`](vueltafit/) |
| 8 | **RutaSabor** | Foodtech / Ghost kitchens (delivery) | GMV vs. contribution by brand after ingredients, marketplace commissions and incidents. | [`rutasabor/`](rutasabor/) |

## Skills demonstrated

- **Python:** Pandas, NumPy — forensic EDA, systematic cleaning and typing, joins and business metrics.
- **SQL:** DuckDB — rankings, `JOIN`s, funnels, cohorts and KPIs on clean tables.
- **Visualization:** Matplotlib and Seaborn — decision-oriented executive charts.
- **Machine Learning:** scikit-learn (churn prediction model in PlayLoop).
- **Business metrics:** LTV, CAC, ROAS, cohort retention, Loss/Combined Ratio, RevPAR/GOPPAR, contribution margin, return rate.
- **Analytical thinking:** control of confounding variables (Simpson's paradox), survivorship bias, counterfactuals.
- **Communication:** executive one-pagers with actionable recommendations.

## Structure

```
<project>/
├── dia_01.ipynb … dia_05.ipynb   # notebooks with outputs
├── data/raw/ · data/clean/      # case data
├── reports/                      # charts and ONE_PAGER.md
├── README.md                     # Spanish
└── README.en.md                  # English
```

## How to run

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

## Contact

- GitHub: [@reme1982](https://github.com/reme1982)
- LinkedIn: [hector-cardenas-datos](https://www.linkedin.com/in/hector-cardenas-datos/)
- X: [@Datos_Scout_Fut](https://x.com/Datos_Scout_Fut)

> The case data is synthetic and intended for training purposes.
