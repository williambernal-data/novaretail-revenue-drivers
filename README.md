# NovaRetail+ — Customer Behavior Drivers of Annual Revenue

Correlational analysis identifying which customer behavior signals are most strongly associated with revenue generation on a Latin American e-commerce platform, using a synthetic 2024 customer behavior dataset (15,000 customers).

> **Note:** the underlying dataset is not included in this repository. The notebook is provided with all outputs (tables, charts, and results) already generated, so the full analysis can be reviewed directly on GitHub without re-running any code.

## Business Problem

NovaRetail+'s Growth & Retention team needed to answer one question ahead of their 2025 planning cycle:

> **Which customer behavior factors are most strongly associated with the annual revenue a customer generates?**

The goal was to move the team's growth strategy away from assumptions and toward evidence — identifying which levers (purchase frequency, site traffic, advertising spend, demographics, membership tier) actually track with customer value, and which don't.

## Key Business Findings

- **Purchase frequency is the strongest driver of revenue** (Pearson r = 0.967) — by a wide margin the most important signal in the dataset. Growth strategy should prioritize increasing repeat purchases over most other levers.
- **Traffic alone doesn't convert to revenue** (r ≈ 0.34) — a large share of high-visit customers generate zero revenue, pointing to a conversion problem rather than a traffic problem.
- **Personal income level is a poor segmentation variable** (r ≈ 0.02) — customers' estimated purchasing power shows no meaningful relationship with what they actually spend on the platform.
- **Advertising spend correlates with visits (r = 0.58), not with revenue (r = 0.20)** — ad campaigns are doing their job of driving traffic, but the conversion gap downstream is where the revenue opportunity is being lost.
- **Premium membership has a statistically significant, but weak, link to churn** (Cramér's V = 0.12, p < 0.0001) — real enough to justify a churn-prevention initiative targeted at premium customers, but not strong enough to be treated as the primary churn driver on its own.

## Methodology

- Data validation and cleaning (dtypes, missing values, binary/categorical checks)
- Correlation analysis using the coefficient appropriate to each variable pair:
  - **Pearson & Spearman** for numeric–numeric relationships
  - **Point-biserial** for numeric–binary relationships
  - **Cramér's V** for categorical–categorical associations
- Visual exploration via correlation heatmaps and targeted scatterplots (no generalized pairplot — variables with no linear signal were excluded to keep the analysis focused)
- Explicit "what we can and can't claim" framing for every finding, to keep correlation from being read as causation

## Repository Structure

```
├── notebooks/
│   └── novaretail_revenue_correlation_analysis.ipynb   (includes all outputs)
├── LICENSE
├── requirements.txt
└── README.md
```

## Tech Stack

Python · pandas · NumPy · seaborn · matplotlib · SciPy · Jupyter

## Limitations

This is an exploratory, correlational analysis — it identifies associations, not causal relationships. It covers a single year (2024), so findings reflect a snapshot rather than a long-term trend. The dataset also doesn't include product-level detail (categories, promotions, campaign-level interaction data), which would sharpen the revenue and churn findings further.

## Next Steps

- Predictive modeling for annual revenue and churn probability
- Customer segmentation via clustering on behavioral variables
- Controlled experiments on purchase-frequency interventions (loyalty programs, personalized recommendations)
- Retention/survival modeling for the premium segment

---

**Author:** William Andrés Bernal Sosa — [GitHub](https://github.com/williambernal-data)
