# Dummy Variable Creation for Regression Models

## Purpose
Regression models require numerical inputs. To include categorical variables such as **region** and **store_type**, we convert them into dummy variables. This allows the model to capture differences across categories without introducing redundancy.

---

##  Variables Converted

### 1. Region
- Original categories: **East, West, North, South**
- Dummy variables created:
  - `region_East`
  - `region_West`
  - `region_North`
- **Reference category**: South  
  (South is omitted to avoid the "dummy variable trap" — perfect multicollinearity.)

### 2. Store Type
- Original categories: **Residential, High Street, Mall, Airport**
- Dummy variables created:
  - `store_Residential`
  - `store_HighStreet`
  - `store_Mall`
- **Reference category**: Airport  
  (Airport is omitted as the baseline category.)

---

##  Example Transformation

| store_id | region   | store_type   | region_East | region_West | region_North | store_Residential | store_HighStreet | store_Mall |
|----------|----------|--------------|-------------|-------------|--------------|-------------------|------------------|------------|
| STR-1001 | East     | Residential  | 1           | 0           | 0            | 1                 | 0                | 0          |
| STR-1002 | East     | High Street  | 1           | 0           | 0            | 0                 | 1                | 0          |
| STR-1003 | North    | Airport      | 0           | 0           | 1            | 0                 | 0                | 0          |
| STR-1004 | South    | Mall         | 0           | 0           | 0            | 0                 | 0                | 1          |

---

##  Notes
- **Holiday Flag** is already binary (0/1), so no dummy creation needed.  
- Reference categories serve as baselines. Coefficients of dummy variables represent differences relative to the baseline.  
- This approach ensures the regression model avoids multicollinearity while capturing categorical effects.

---

##  Usage in Regression Equations
When included in regression models, the equation for **monthly_sales** looks like:

\[
\text{monthly_sales} = \beta_0 + \beta_1(\text{marketing_spend}) + \beta_2(\text{footfall}) + \beta_3(\text{avg_discount_pct}) + \dots + \beta_{region_East} + \beta_{region_West} + \beta_{region_North} + \beta_{store_Residential} + \beta_{store_HighStreet} + \beta_{store_Mall} + \epsilon
\]

Where:
- Baseline region = South  
- Baseline store type = Airport  

---

##  Conclusion
Dummy variables allow categorical features to be incorporated into regression models. By carefully selecting reference categories, we avoid redundancy and ensure interpretable coefficients.

