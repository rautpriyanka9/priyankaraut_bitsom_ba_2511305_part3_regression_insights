# Residual Analysis

## Overview

Residual analysis was performed using the final multiple regression model. Predicted sales were calculated using the regression equation, and residuals were computed as:

**Residual = Actual Sales − Predicted Sales**

Residuals help identify stores where the model significantly under-predicted or over-predicted sales performance.

---

## Largest Positive Residuals

The following records showed the largest positive residuals after sorting the residual column in descending order.

| Rank | Store ID | Actual Sales | Predicted Sales |   Residual |
| ---- | -------- | -----------: | --------------: | ---------: |
| 1    | STR-1058 |   870,937.40 |      759,919.94 | 111,017.46 |
| 2    | STR-1028 |   713,611.16 |      610,531.95 | 103,079.21 |
| 3    | STR-1073 |   813,316.71 |      721,415.92 |  91,900.79 |
| 4    | STR-1051 |   787,715.51 |      701,381.34 |  86,334.17 |
| 5    | STR-1026 |   625,514.04 |      540,234.62 |  85,279.42 |

### Interpretation

These stores performed substantially better than predicted by the model. Possible explanations include:

* Strong local demand not captured by the available variables.
* Successful local marketing campaigns.
* Favorable store locations or customer demographics.
* Seasonal or special events affecting sales.
* Store management effectiveness and operational excellence.

The model under-predicted sales for these stores, indicating that additional explanatory variables may improve model performance.

---

## Largest Negative Residuals

The following records showed the largest negative residuals after sorting the residual column in ascending order.

| Rank | Store ID | Actual Sales | Predicted Sales |    Residual |
| ---- | -------- | -----------: | --------------: | ----------: |
| 1    | STR-1023 |   627,171.90 |      764,038.71 | -136,866.81 |
| 2    | STR-1017 |   685,379.08 |      805,279.85 | -119,900.77 |
| 3    | STR-1012 |   595,467.60 |      709,913.78 | -114,446.18 |
| 4    | STR-1007 |   800,451.94 |      912,344.87 | -111,892.93 |
| 5    | STR-1060 |   721,079.35 |      808,021.71 |  -86,942.36 |

### Interpretation

These stores performed worse than predicted by the model. Possible reasons include:

* Local competitive pressures not fully captured by the competitor distance variable.
* Operational challenges affecting store performance.
* Temporary declines in customer traffic.
* Regional economic factors not included in the dataset.
* Inventory, staffing, or customer service issues.

The model over-predicted sales for these stores, suggesting the presence of additional factors influencing performance.

---

## Business Insights

The residual analysis indicates that while the multiple regression model explains a significant portion of sales variation (R² ≈ 0.857), some store-specific factors remain unaccounted for.

Positive residuals suggest hidden growth opportunities, whereas negative residuals highlight stores that may require operational review.

The model does not show consistent over-prediction or under-prediction for a specific store type or region. Instead, prediction errors appear to be concentrated in individual stores, suggesting that local factors play an important role in sales performance.

---

## Conclusion

The multiple regression model provides strong predictive performance and explains approximately 85.7% of the variation in monthly sales. However, the residual analysis reveals that certain stores consistently perform above or below model expectations.

Future improvements could include additional variables such as:

* Local demographics
* Promotional campaigns
* Customer loyalty metrics
* Store age
* Economic indicators
* Competitor density

These variables may help reduce prediction errors and improve forecasting accuracy.
