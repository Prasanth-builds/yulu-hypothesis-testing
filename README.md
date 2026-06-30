🚲 Yulu Bikes — Hypothesis Testing & Demand Analysis

A statistical case study identifying the key factors driving demand for shared electric cycles in the Indian market, using real-world hourly rental data.

📌 Problem Statement

Yulu, India's leading micro-mobility provider, experienced a significant decline in revenue. This project analyzes 10,886 hourly rental records to answer four business-critical questions:

- Does working day status affect rental demand?
- Does demand vary significantly across seasons?
- Does demand vary significantly across weather conditions?
- Is weather type statistically dependent on season?

🗂️ Dataset

| | |
|---|---|
| **Source** | Hourly bike rental records |
| **Size** | 10,886 records |
| **Period** | January 2011 – December 2012 |
| **Features** | 12 (datetime, season, holiday, workingday, weather, temp, atemp, humidity, windspeed, casual, registered, count) |

🧪 Methodology

1. **Exploratory Data Analysis** — univariate and bivariate analysis of all features, normality checks via Q-Q plots, correlation analysis
2. **2-Sample T-Test** — working day vs non-working day demand
3. **One-Way ANOVA** — demand across seasons and weather types
4. **Chi-Square Test** — independence between weather and season

All tests conducted at **α = 0.05** significance level, with assumption checks (Levene's test for variance, CLT-based normality reasoning for large samples).

## 📊 Key Findings

| Test | Result |
|---|---|
| Working Day Effect | **Not significant** (t=1.21, p=0.226) — demand is balanced across day types |
| Season Effect | **Significant** (F=236.95, p<0.0001) — Fall peaks, Spring troughs at ~50% of Fall |
| Weather Effect | **Significant** (F=65.53, p<0.0001) — Clear weather drives 72% more rentals than Light Rain |
| Weather ⊥ Season | **Dependent** (χ²=49.16, p<0.0001) — weather patterns shift meaningfully by season |

## 💡 Business Recommendations

- Maintain a uniform 7-day fleet baseline instead of weekday-only positioning
- Schedule preventive fleet maintenance during low-demand Spring months
- Trigger automated ride credits / subscription extensions during sustained Light Rain periods
- Use Season × Weather interaction terms in future demand forecasting models to avoid multicollinearity

## 🛠️ Tools Used

`Python` · `pandas` · `numpy` · `scipy` · `matplotlib` · `seaborn`

## 📁 Repository Structure

```
yulu-hypothesis-testing/
├── Yulu_Hypothesis_Testing.ipynb   # Full analysis notebook
├── bike_sharing.csv                 # Dataset
└── README.md
```

## ▶️ How to Run

1. Clone the repo or download the files
2. Open `Yulu_Hypothesis_Testing.ipynb` in Jupyter Notebook, JupyterLab, VS Code, or Google Colab
3. Ensure `bike_sharing.csv` is in the same directory
4. Run all cells

```bash
pip install pandas numpy matplotlib seaborn scipy
jupyter notebook Yulu_Hypothesis_Testing.ipynb
```

---

*Part of the Scaler Data Science & Machine Learning curriculum.*
