# bushraanjum_2511048_part3_regression_insights
Part 3 of Capstone Project

# Retail Store Performance Regression Analysis

##  Objective
The goal of this project is to identify which factors most strongly influence **monthly sales performance** across retail stores. Insights will guide leadership decisions on marketing, staffing, discounting, inventory, and store prioritization.

---

##  Dependent Variable
- **monthly_sales**  
  This is the target variable we want to explain and predict.

---

##  Potential Independent Variables
These are the predictors that may influence monthly sales:

- **marketing_spend** (numeric)  
- **footfall** (numeric)  
- **avg_discount_pct** (numeric)  
- **staff_count** (numeric)  
- **inventory_availability_pct** (numeric)  
- **competitor_distance_km** (numeric)  
- **holiday_flag** (categorical/binary: 0 or 1)  
- **customer_rating** (numeric, scale ~1–5)  
- **region** (categorical: East, West, North, South)  
- **store_type** (categorical: Residential, High Street, Mall, Airport)

---

##  Numerical Variables
- marketing_spend  
- footfall  
- avg_discount_pct  
- staff_count  
- inventory_availability_pct  
- competitor_distance_km  
- customer_rating  
- monthly_profit (may be correlated with sales, use cautiously)

---

##  Categorical Variables
- region  
- store_type  
- holiday_flag (binary categorical)

---

##  Variables Needing Cleaning/Transformation
- **month**: Currently appears as a numeric code (e.g., 45658). Needs conversion to actual date or month index.  
- **holiday_flag**: Convert to binary dummy variable (0/1).  
- **region** and **store_type**: Encode using one-hot encoding or dummy variables.  
- **avg_discount_pct**: Check for extreme values (e.g., 0 or >0.25) that may distort regression.  
- **competitor_distance_km**: Some values are very small (close to 0), may need log transformation.

---

##  Variables Potentially Not Useful for Regression
- **store_id**: Identifier, not predictive.  
- **monthly_profit**: Highly correlated with monthly_sales (risk of multicollinearity). Could be used in a separate profitability model but not in sales regression.  
- **month**: If treated as raw numeric, meaningless. Needs transformation into seasonality/holiday features.

---

##  Next Steps
1. **Data Cleaning**  
   - Convert month into proper time features (seasonality, holiday periods).  
   - Encode categorical variables.  
   - Handle missing or extreme values.  

2. **Regression Modeling**  
   - Start with multiple linear regression.  
   - Check multicollinearity (VIF).  
   - Consider interaction terms (e.g., marketing_spend × holiday_flag).  

3. **Business Recommendations**  
   - Identify strongest drivers of sales.  
   - Suggest actionable strategies (e.g., optimize discounting, allocate staff efficiently, target high-performing regions).

---

##  Notes
- Regression will highlight **marginal impact of each factor** on sales.  
- Leadership can use results to prioritize **marketing vs. discounting vs. staffing** strategies.  
- Seasonal and regional effects may require additional feature engineering.
