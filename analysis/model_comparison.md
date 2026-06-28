# Model Comparison

## Overview

Three regression models were developed to understand the factors influencing monthly sales:

1. Simple Regression Model 1 – Marketing Spend
2. Simple Regression Model 2 – Footfall
3. Multiple Regression Model

The objective is to compare their explanatory power, statistical significance, and business usefulness.

---

## Comparison Table

| Model               | Dependent Variable | Independent Variables                                                                                                                                                           | R-Squared | Significant Variables                                               | Business Usefulness                            |
| ------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- | ------------------------------------------------------------------- | ---------------------------------------------- |
| Simple Regression 1 | monthly_sales      | marketing_spend                                                                                                                                                                 | 0.166     | marketing_spend (p = 3.52E-14)                                      | Useful for evaluating marketing ROI            |
| Simple Regression 2 | monthly_sales      | footfall                                                                                                                                                                        | 0.737     | footfall (p = 6.52E-94)                                             | Strong predictor of store sales performance    |
| Multiple Regression | monthly_sales      | marketing_spend, footfall, avg_discount_pct, staff_count, inventory_availability_pct, competitor_distance_km, holiday_flag, customer_rating, region dummies, store type dummies | 0.857     | Most variables significant except avg_discount_pct and Region_South | Best model for forecasting and decision-making |

---

## R-Squared Comparison

### Simple Regression 1: Marketing Spend

* R-Squared = 0.166
* Explains approximately 16.6% of sales variation.

Interpretation:

Marketing spend influences sales but many other factors affect store performance.

---

### Simple Regression 2: Footfall

* R-Squared = 0.737
* Explains approximately 73.7% of sales variation.

Interpretation:

Customer traffic is a very strong predictor of monthly sales.

---

### Multiple Regression Model

* R-Squared = 0.857
* Explains approximately 85.7% of sales variation.

Interpretation:

Combining operational, marketing, customer, and location variables produces the most accurate model.

---

## Significant Variables

### Statistically Significant Variables

| Variable                   | P-value  |
| -------------------------- | -------- |
| marketing_spend            | 1.06E-21 |
| footfall                   | 6.55E-27 |
| staff_count                | 0.0027   |
| inventory_availability_pct | 5.13E-12 |
| competitor_distance_km     | 7.22E-10 |
| holiday_flag               | 0.014    |
| customer_rating            | 0.005    |
| Region_North               | 0.022    |
| Region_East                | 0.000024 |
| Store_Mall                 | 1.90E-07 |
| Store_HighStreet           | 0.00033  |
| Store_Airport              | 5.73E-07 |

### Statistically Weak Variables

| Variable         | P-value |
| ---------------- | ------- |
| avg_discount_pct | 0.224   |
| Region_South     | 0.538   |

These variables do not provide strong evidence of a relationship with monthly sales.

---

## Business Usefulness

### Marketing Spend Model

Useful for:

* Estimating expected sales impact of marketing campaigns.
* Evaluating return on marketing investments.

Limitation:

* Ignores customer traffic, store operations, and location effects.

---

### Footfall Model

Useful for:

* Understanding how customer visits influence sales.
* Tracking store performance using traffic data.

Limitation:

* Does not explain why footfall changes.

---

### Multiple Regression Model

Useful for:

* Sales forecasting.
* Store performance analysis.
* Marketing budget allocation.
* Staffing decisions.
* Inventory planning.
* Location strategy evaluation.

This model provides the most comprehensive understanding of sales drivers.

---

## Model Limitations

1. Regression identifies relationships but does not prove causation.
2. External factors such as economic conditions, weather, competitor promotions, and local events are not included.
3. The model assumes linear relationships between variables.
4. Future changes in customer behavior may reduce predictive accuracy.
5. Some variables may interact with each other in ways not captured by the model.

---

## Final Recommendation

The Multiple Regression Model should be used for business decision-making because it explains the highest proportion of sales variation (85.7%) and incorporates multiple operational and market factors.

The Footfall Simple Regression Model can be used as a quick performance indicator when only customer traffic data is available.

The Marketing Spend Simple Regression Model is useful for evaluating marketing effectiveness but should not be used as a standalone forecasting model.
