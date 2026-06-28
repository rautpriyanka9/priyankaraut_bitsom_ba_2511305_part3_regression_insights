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
