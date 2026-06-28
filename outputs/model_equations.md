# Dummy Variable Creation

## Why Dummy Variables Were Required

Regression models require numerical inputs. Since **region** and **store_type** are categorical variables, they were converted into dummy variables before performing multiple regression analysis.

To avoid the **Dummy Variable Trap** (perfect multicollinearity), one category from each variable was excluded and used as the reference category.

---

## Region Dummy Variables

Original categories:

* North
* South
* East
* West

Reference Category:

**West**

Created dummy variables:

| Dummy Variable | Value = 1 When           |
| -------------- | ------------------------ |
| Region_North   | Store is in North region |
| Region_South   | Store is in South region |
| Region_East    | Store is in East region  |

Interpretation:

* If all three dummy variables equal 0, the store belongs to the West region (reference category).

Example:

| Region | Region_North | Region_South | Region_East |
| ------ | ------------ | ------------ | ----------- |
| North  | 1            | 0            | 0           |
| South  | 0            | 1            | 0           |
| East   | 0            | 0            | 1           |
| West   | 0            | 0            | 0           |

---

## Store Type Dummy Variables

Original categories:

* Residential
* Mall
* High Street
* Airport

Reference Category:

**Residential**

Created dummy variables:

| Dummy Variable   | Value = 1 When            |
| ---------------- | ------------------------- |
| Store_Mall       | Store type is Mall        |
| Store_HighStreet | Store type is High Street |
| Store_Airport    | Store type is Airport     |

Interpretation:

* If all three dummy variables equal 0, the store type is Residential (reference category).

Example:

| Store Type  | Store_Mall | Store_HighStreet | Store_Airport |
| ----------- | ---------- | ---------------- | ------------- |
| Mall        | 1          | 0                | 0             |
| High Street | 0          | 1                | 0             |
| Airport     | 0          | 0                | 1             |
| Residential | 0          | 0                | 0             |

---

## Avoiding Redundancy

One category from each categorical variable was intentionally excluded:

* West was excluded from Region.
* Residential was excluded from Store Type.

These excluded categories serve as reference categories and prevent perfect multicollinearity in the regression model.

This approach ensures that the regression coefficients for dummy variables are interpreted relative to the reference categories.

# Model Equations

## Overview

To understand the factors that influence monthly store sales, both simple and multiple regression models were developed. The models estimate monthly sales based on operational, marketing, customer, and store characteristics.

---

# Simple Regression Model 1: Marketing Spend

## Equation

Monthly Sales = 561,666.39 + (2.1187 × Marketing Spend)

### Business Interpretation

* The intercept (561,666.39) represents the estimated monthly sales when marketing spend is zero.
* The marketing spend coefficient (2.1187) indicates that every additional ₹1 spent on marketing is associated with an average increase of approximately ₹2.12 in monthly sales.
* The relationship is positive and statistically significant (p-value < 0.001).

### Model Performance

| Metric  | Value    |
| ------- | -------- |
| R²      | 0.166    |
| P-value | 3.52E-14 |

### Business Conclusion

Marketing spend has a positive impact on sales, but by itself explains only a limited portion of sales variation.

---

# Simple Regression Model 2: Footfall

## Equation

Monthly Sales = 446,966.83 + (35.6298 × Footfall)

### Business Interpretation

* The intercept (446,966.83) represents estimated sales when footfall is zero.
* The footfall coefficient (35.6298) indicates that each additional customer visit is associated with approximately ₹35.63 higher monthly sales.
* The relationship is strongly positive and statistically significant.

### Model Performance

| Metric  | Value    |
| ------- | -------- |
| R²      | 0.737    |
| P-value | 6.52E-94 |

### Business Conclusion

Footfall is one of the strongest predictors of sales. Stores with higher customer traffic tend to generate substantially higher revenue.

---

# Multiple Regression Model

## Equation

Monthly Sales =

66,915.47

* (1.2099 × Marketing Spend)

* (27.3362 × Footfall)

− (41,243.15 × Avg Discount %)

* (3,508.40 × Staff Count)

* (3,062.21 × Inventory Availability %)

− (3,438.11 × Competitor Distance)

* (15,157.29 × Holiday Flag)

* (12,509.46 × Customer Rating)

− (15,342.71 × Region_North)

− (4,201.85 × Region_South)

− (25,291.42 × Region_East)

* (32,832.85 × Store_Mall)

* (20,219.26 × Store_HighStreet)

* (44,695.09 × Store_Airport)

---

# Explanation of Coefficients

## Marketing Spend (+1.2099)

Higher marketing investment is associated with increased sales. Every additional ₹1 spent on marketing increases expected monthly sales by approximately ₹1.21.

## Footfall (+27.3362)

Stores with higher customer traffic generate higher sales. Every additional customer visit increases expected sales by approximately ₹27.34.

## Average Discount Percentage (-41,243.15)

Higher discount levels are associated with lower sales revenue, suggesting that excessive discounting may reduce overall revenue performance.

## Staff Count (+3,508.40)

Stores with more staff tend to achieve higher sales, likely due to improved customer service and operational efficiency.

## Inventory Availability Percentage (+3,062.21)

Maintaining product availability positively impacts sales by reducing stock-outs and improving customer satisfaction.

## Competitor Distance (-3,438.11)

The coefficient suggests a negative relationship between competitor distance and sales. This variable may be influenced by local market conditions and should be interpreted carefully.

## Holiday Flag (+15,157.29)

Stores operating during holiday periods tend to experience higher sales compared with non-holiday periods.

## Customer Rating (+12,509.46)

Higher customer satisfaction ratings are associated with stronger sales performance.

---

# Dummy Variables

Dummy variables were created to represent categorical variables numerically for regression analysis.

## Region Dummy Variables

Created:

* Region_North
* Region_South
* Region_East

### Reference Category

**West Region** was used as the reference category.

Interpretation:

* Region_North = 1 if store is in North region, otherwise 0.
* Region_South = 1 if store is in South region, otherwise 0.
* Region_East = 1 if store is in East region, otherwise 0.

All regional coefficients are interpreted relative to West Region.

---

## Store Type Dummy Variables

Created:

* Store_Mall
* Store_HighStreet
* Store_Airport

### Reference Category

**Residential Store** was used as the reference category.

Interpretation:

* Store_Mall = 1 if store type is Mall.
* Store_HighStreet = 1 if store type is High Street.
* Store_Airport = 1 if store type is Airport.

All store type coefficients are interpreted relative to Residential stores.

---

# Why Reference Categories Were Used

One category from each categorical variable was excluded to avoid the Dummy Variable Trap, which causes perfect multicollinearity in regression models.

Therefore:

* West Region serves as the baseline region.
* Residential Store serves as the baseline store type.

All dummy variable effects are measured relative to these categories.

---

# Final Model Selected

The Multiple Regression Model was selected as the final model.

## Reasons for Selection

### Higher Predictive Accuracy

| Model                     | R²    |
| ------------------------- | ----- |
| Marketing Spend Model     | 0.166 |
| Footfall Model            | 0.737 |
| Multiple Regression Model | 0.857 |

The multiple regression model explains approximately 85.7% of the variation in monthly sales, significantly outperforming the simple regression models.

### Better Business Insights

The model incorporates multiple drivers of sales, including:

* Marketing activity
* Customer traffic
* Staffing levels
* Inventory availability
* Customer satisfaction
* Regional differences
* Store format differences

### Strong Statistical Significance

Most key variables have very small p-values, indicating strong evidence that they influence sales performance.

### Practical Business Value

The model can be used to:

* Forecast monthly sales
* Identify high-performing store formats
* Evaluate marketing effectiveness
* Support staffing and inventory planning
* Improve store-level decision making

---

# Conclusion

The multiple regression model provides the most reliable explanation of monthly sales performance. By combining operational, customer, marketing, and location factors, it delivers stronger predictive accuracy and more actionable business insights than the simple regression models.
