# Model Comparison

## Simple Regression – Marketing Spend
- **Variables used:** monthly_sales ~ marketing_spend  
- **R-squared:** ~0.62  
- **Significant variable:** Marketing Spend (positive, useful)  
- **Business usefulness:** Shows sales rise with marketing spend.  
- **Limitations:** Ignores other drivers.

---

## Simple Regression – Footfall
- **Variables used:** monthly_sales ~ footfall  
- **R-squared:** ~0.71  
- **Significant variable:** Footfall (positive, very useful)  
- **Business usefulness:** Strong link between store traffic and sales.  
- **Limitations:** Does not include marketing, discounts, or region.

---

## Multiple Regression – Combined Drivers
- **Variables used:** monthly_sales ~ marketing_spend + footfall + avg_discount_pct + region_East  
- **R-squared:** ~0.78  
- **Significant variables:** Marketing Spend (+), Footfall (+), Avg Discount % (–), Region_East (+)  
- **Business usefulness:** Best overall model. Shows combined effects and regional differences.  
- **Limitations:** Still linear, some weaker variables not included.

---

## Key Takeaway
- Simple models are easy but limited.  
- Multiple regression explains more variation and gives better guidance for decisions.  
