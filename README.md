# Retail Demand Forecasting — Walmart Store Sales

## Business Problem
Walmart operates 45 stores across multiple regions, running markdown 
promotions around major holidays (Super Bowl, Labour Day, Thanksgiving, 
Christmas). The core challenge: can we forecast department-level weekly 
sales accurately enough to optimise markdown timing and inventory 
positioning — even with limited historical data on rare events?

## Key Questions
1. Which departments and stores are most sensitive to holiday markdowns?
2. How accurately can we forecast 4–12 weeks ahead at department level?
3. What does model error cost in real inventory terms?

## Dataset
- **Source:** Walmart Recruiting - Store Sales Forecasting (Kaggle)
- **Scale:** 45 stores, 99 departments, ~2.5 years of weekly sales data
- **Features:** Temperature, fuel price, CPI, unemployment, 
  markdown events (MarkDown1–5), holiday flags

## Approach
### 1. Exploratory Analysis
- Decomposed sales into trend, seasonality, and residuals
- Identified holiday uplift patterns across departments
- Tested stationarity using ADF test

### 2. Feature Engineering
- Lag features: 1, 2, 4, 12 weeks prior sales
- Rolling averages: 4, 12, 52-week windows
- Holiday interaction features

### 3. Models
| Model | Approach |
|-------|----------|
| Facebook Prophet | Weekly + yearly seasonality with holiday regressors |
| LightGBM | Gradient boosting with lag/rolling features |

### 4. Evaluation
Models evaluated using Weighted MAE (WMAE) — holiday weeks 
weighted 5x heavier, consistent with Walmart's business priority.

## Key Findings
- Holiday weeks drive disproportionate variance — especially 
  Thanksgiving and Christmas
- LightGBM with lag features outperformed Prophet on 
  short-horizon forecasts
- Markdown effects vary significantly by department — 
  not all departments respond equally to promotions
- Rolling 52-week features provided strongest signal for 
  seasonal baseline

## Business Recommendations
1. Prioritise markdown investment in high-sensitivity departments 
   identified by elasticity analysis
2. Use 4-week lag features as minimum input for replenishment 
   planning cycles
3. Flag holiday weeks for manual review — model uncertainty 
   increases significantly on sparse holiday data

## Tech Stack
- Python (Pandas, NumPy, Scikit-learn, LightGBM, Prophet)
- Jupyter Notebook
- Matplotlib / Seaborn

## How to Run
```bash
pip install pandas numpy scikit-learn lightgbm prophet matplotlib seaborn
```
Open `walmart_demand_forecasting.ipynb` and run all cells.
Data files are included in the `/data` folder.

## Relevance to Supply Chain Roles
This project directly mirrors the work of a demand planning or 
replenishment analyst — forecasting at SKU/store level, 
accounting for promotional events, and quantifying model 
error in business terms.
