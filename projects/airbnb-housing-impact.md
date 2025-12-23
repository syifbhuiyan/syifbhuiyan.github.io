# The Airbnb Effect: Impact on NYC Housing

**Syif M. Bhuiyan | Data Analyst**  
[Back to Home](../index.md)

---

![Graph showing correlation between Airbnb density and House Prices](../assets/results_graph.png)

## Goal

Determine if *“platformization”* of housing (via Airbnb) correlates with higher local housing costs in New York City neighborhoods.

---

## Tools Used

- **Python (Pandas):** For cleaning and merging disparate datasets.
- **Statsmodels (OLS Regression):** To statistically quantify the relationship.
- **Plotly:** For geospatial and regression visualization.
- **GitHub:** For version control and reproducibility.

---

## Project Overview

In the debate over urban housing affordability, short-term rentals are often cited as a driver of rising costs. This project utilizes **Computational Social Science** techniques to empirically test this theory using real-world data from **Inside Airbnb** and **Zillow Research**.

I built a data pipeline to merge listing data with neighborhood-level housing value indices (ZHVI) across **164 NYC neighborhoods** to perform a regression analysis.

---

## Key Insights & Findings

- **Statistically Significant:**  
  The model yielded a **P-value of 0.000**, confirming the relationship is non-random.

- **The “Airbnb Premium”:**  
  The regression coefficient suggests that **for every 1 new Airbnb listing** added to a neighborhood, average annual home values increase by approximately **$585**.

- **Correlation vs Causation:**  
  While the model explains approximately **10% of price variance** (R-squared = 0.097), it highlights that short-term rental density is a significant market signal, functioning alongside other variables like location desirability.

---

## Code Snippet: The Regression Model

```python
# Running Ordinary Least Squares (OLS) Regression
import statsmodels.api as sm

Y = master_df['avg_house_price']
X = master_df['airbnb_count']
X = sm.add_constant(X)

model = sm.OLS(Y, X).fit()
print(model.summary())
```

---

## Methodological Note

While this OLS regression establishes a statistically significant correlation ($R^2=0.097$) between short-term rental density and housing prices, I acknowledge that correlation does not imply causation. A future iteration of this study would ideally employ a Difference-in-Differences (DiD) approach or Instrumental Variable (IV) analysis to better isolate the causal impact of Airbnb market entry.

---

👉 **[View Full Code on GitHub](https://github.com/syifbhuiyan/nyc-airbnb-impact)**

---
