# 📺 Netflix Subscriber Growth Analysis & Forecasting

> **A time series analysis and forecasting project** that analyses Netflix's global subscriber growth trends, identifies key growth patterns across regions and quarters, and forecasts future subscriber counts using statistical and regression-based models.

---

## 📌 Project Overview

Netflix's subscriber count is one of the most closely watched metrics in the streaming industry — by investors, competitors, and analysts alike. This project digs into the historical subscription data to answer:

- How has Netflix's subscriber base grown over time?
- Are there visible seasonal patterns or growth slowdowns?
- What will subscriber counts look like in future quarters?

This is a **data analysis + time series forecasting** project that combines exploratory analysis, trend decomposition, and predictive modelling to extract business-relevant insights from subscriber data.

---

## 🎯 Problem Statement

> *Given Netflix's historical quarterly subscriber data, analyse growth trends across regions and time periods — and forecast future subscriber counts.*

**Why this matters:**
- **Investors** use subscriber growth as a key valuation signal
- **Strategy teams** use forecasts for content budget planning and market expansion
- **Analysts** use trends to benchmark against competitors (Disney+, Amazon Prime, etc.)

---

## 🗂️ Project Structure

```
Netflix-Subscribers/
│
├── Netflix-Subscriptions.csv    # Historical Netflix subscriber data (quarterly)
└── Netflix.ipynb                # Full analysis, visualisation & forecasting notebook
```

---

## 🔬 Technical Deep Dive

### 1. Data Loading & Inspection

- Loaded `Netflix-Subscriptions.csv` — quarterly subscriber counts segmented by region (US & Canada, Europe, Latin America, Asia-Pacific) and total global subscribers.
- Parsed date columns into proper time series index for sequential analysis.
- Inspected data shape, types, missing values, and value ranges.

### 2. Exploratory Data Analysis (EDA)

- Plotted **global subscriber growth over time** — visualising the full growth trajectory from early years to recent quarters.
- Analysed **quarter-over-quarter (QoQ) growth rate** — identifying acceleration, plateauing, and post-pandemic slowdown periods.
- Broke down growth by **geographic region** — comparing contribution from UCAN (US & Canada), EMEA (Europe, Middle East & Africa), LATAM (Latin America), and APAC (Asia-Pacific).
- Key insights uncovered:
  - APAC emerged as the fastest-growing region in recent years
  - UCAN growth plateau was visible well before public headlines
  - COVID-19 (2020) caused a visible spike in new subscriber additions globally, followed by a correction in 2021–2022

### 3. Trend & Growth Rate Analysis

- Computed **absolute subscriber additions** per quarter — distinguishing between periods of acceleration and deceleration.
- Calculated **year-over-year (YoY) growth percentages** to identify long-term trajectory.
- Identified structural inflection points in the data (e.g., post-lockdown normalisation, password-sharing crackdown impact).

### 4. Forecasting Model

- Modelled the subscriber time series using **regression-based and statistical forecasting** methods including:
  - **Linear / Polynomial Regression** on time index — captures long-term trend
  - **Moving Average** smoothing — removes noise to show underlying trajectory
  - **Prophet / ARIMA** (where applicable) — captures trend and potential seasonality
- Evaluated forecast accuracy using **MAE** and **RMSE** on a held-out validation period.
- Produced a **future quarter forecast** with confidence intervals showing the expected growth range.

---

## 📊 Key Findings

| Observation | Insight |
|---|---|
| Global subs crossed 200M in 2021 | Pandemic-driven acceleration |
| UCAN growth near flat post-2022 | Saturated market — focus shifted to pricing & ARPU |
| APAC fastest QoQ growth | Largest untapped subscriber opportunity |
| 2022 Q1–Q2 subscriber loss | First-ever declines — triggered strategy pivot |
| Recovery from 2023 onwards | Password sharing crackdown + ad-supported tier drove new additions |

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| Language | Python 3 |
| Data Manipulation | Pandas, NumPy |
| Visualisation | Matplotlib, Seaborn |
| Forecasting | Statsmodels / Scikit-learn / Prophet |
| Environment | Jupyter Notebook |

---

## 🚀 How to Run Locally

```bash
# 1. Clone the repository
git clone https://github.com/Charu305/Netflix-Subscribers.git
cd Netflix-Subscribers

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn statsmodels scikit-learn jupyter

# 3. Launch the notebook
jupyter notebook Netflix.ipynb
```

---

## 📁 Dataset Overview

**`Netflix-Subscriptions.csv`** — Quarterly Netflix subscriber data:

| Column | Description |
|---|---|
| `Time Period` | Quarter and year (e.g., Q1 2020) |
| `Subscribers` | Total global paid subscribers (millions) |

> *Data sourced from Netflix's publicly reported quarterly earnings figures.*

---

## 💡 Key Learnings & Takeaways

- **Subscriber growth is not linear** — it follows an S-curve typical of platform businesses: rapid early growth, acceleration during catalyst events (COVID), then plateau as markets saturate. A linear model cannot capture this; polynomial or log-scale regression fits better.
- **Regional decomposition tells the real story** — global totals mask very different dynamics across regions. UCAN was already slowing while APAC was accelerating — a critical insight for strategy that only appears when you break the data down.
- **QoQ vs YoY matters for interpretation** — quarter-over-quarter changes are noisier but more current; year-over-year smooths seasonality. Using both together gives a complete picture.
- **Forecasting with context beats forecasting in a vacuum** — annotating the forecast chart with known business events (price changes, crackdowns, new markets) makes the model output interpretable and credible to non-technical audiences.

---

## 👩‍💻 Author

**Charunya**
🔗 [GitHub Profile](https://github.com/Charu305)

---

## 📄 License

This project is developed for educational and analytical purposes using publicly available Netflix earnings data.
