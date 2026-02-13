# Assignment 04 Interpretation Memo

**Student Name:** [Your Name]
**Date:** [Submission Date]
**Assignment:** REIT Annual Returns and Predictors (Simple Linear Regression)

---

## 1. Regression Overview

Three simple OLS regressions of REIT annual returns on single predictors were estimated:

- `ret ~ div12m_me` (dividend yield)
- `ret ~ prime_rate` (year-end prime loan rate)
- `ret ~ ffo_at_reit` (funds from operations scaled by assets)

All model output and scatter plots are saved in the `Results/` folder.

---

## 2. Coefficient Comparison (All Three Regressions)

**Model 1: ret ~ div12m_me**
- Intercept (β₀): 0.1082 (SE: 0.0060, p < 0.001)
- Slope (β₁): -0.0687 (SE: 0.0325, p = 0.035)
- R²: 0.002 | N: 2527

**Model 2: ret ~ prime_rate**
- Intercept (β₀): 0.2801 (SE: 0.0154, p < 0.001)
- Slope (β₁): -0.0363 (SE: 0.0030, p < 0.001)
- R²: 0.056 | N: 2527

**Model 3: ret ~ ffo_at_reit**
- Intercept (β₀): 0.0973 (SE: 0.0092, p < 0.001)
- Slope (β₁): 0.5770 (SE: 0.5669, p = 0.309)
- R²: ~0.000 | N: 2518

> Note: `Model 3` has slightly fewer observations because `ffo_at_reit` contains missing values and rows are dropped listwise.

---

## 3. Slope Interpretation (Economic Units)

**Dividend Yield (div12m_me):**
- The estimated slope of -0.0687 implies that a one-unit increase in `div12m_me` is associated with a -0.0687 change in annual return. The sign is negative and statistically significant at the 5% level, but the economic magnitude is very small and the model explains virtually none of the variation in returns.

**Prime Loan Rate (prime_rate):**
- A one percentage point (1.0) increase in the year-end `prime_rate` is associated with an estimated -0.0363 decrease in annual REIT return. This relationship is statistically highly significant and is the most robust among the three single-predictor models.

**FFO to Assets (ffo_at_reit):**
- The point estimate is 0.5770 but is not statistically significant (p = 0.309). There is no reliable evidence in this sample that higher `ffo_at_reit` predicts higher annual returns.

---

## 4. Statistical Significance (5% level)

- **div12m_me:** Significant (p = 0.035) — negative but economically tiny.
- **prime_rate:** Significant (p < 0.001) — negative and the strongest relationship found here.
- **ffo_at_reit:** Not significant (p = 0.309) — no evidence of a relationship.

**Strongest evidence:** `prime_rate` shows the clearest statistical relationship with annual returns.

---

## 5. Model Fit (R-squared)

`prime_rate` yields the highest R² (~0.056), but even that explains only about 5.6% of the variation in annual REIT returns. The other models have negligible R². Overall, single-predictor models leave most variation unexplained — suggesting omitted factors (firm-level characteristics, market risk, leverage, sector allocation, etc.) are important.

---

## 6. Omitted Variables (Examples)

- Leverage / capital structure: affects sensitivity to interest rates and return volatility.
- Property sector mix (e.g., industrial, retail, residential): different sectors perform differently across cycles.
- Market beta or exposure to common equity factors: systematic risk not captured by single predictors.

Potential bias arises if omitted variables correlate with both the predictor and `ret`.

---

## 7. Summary and Next Steps

**Key Takeaway:**
The year-end `prime_rate` shows the most statistically robust negative association with REIT annual returns, but overall explanatory power of single-predictor OLS is low. Dividend yield has a statistically detectable negative association but with negligible economic impact; FFO/Assets shows no reliable relationship in this sample.

**Next steps:**
- Estimate multivariate regressions that include several predictors together.
- Test OLS assumptions (heteroskedasticity, nonlinearity) and use robust SEs if needed.
- Explore cross-sectional heterogeneity by sector and time subsamples.

---

## Reproducibility Checklist
- [x] Script runs end-to-end without errors (see `assignment04_regression.py`)
- [x] Regression output saved to `Results/regression_div12m_me.txt`, `Results/regression_prime_rate.txt`, `Results/regression_ffo_at_reit.txt`
- [x] Scatter plots saved to `Results/scatter_div12m_me.png`, `Results/scatter_prime_rate.png`, `Results/scatter_ffo_at_reit.png`
- [x] Report reflects regression results in `Results/`



