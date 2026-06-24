# Final Recommendation

## Purpose

This document provides the final business recommendation based on the regression results, model comparison, and residual analysis.

The final selected model is the multiple regression model because it explains about `82.81%` of the variation in monthly sales and includes several important business drivers.

## Which Factors Appear Most Strongly Associated With Monthly Sales?

The factors most strongly associated with monthly sales are the variables that have useful p-values and clear business meaning in the multiple regression model.

The significant variables are:

- `footfall`
- `marketing_spend`
- `inventory_availability_pct`
- `clean_customer_rating`
- `staff_count`
- `holiday_flag`
- `avg_discount_pct`
- `store_type_residential`

### Footfall

Footfall is one of the strongest factors. In the simple regression model, footfall alone explains `73.63%` of the variation in monthly sales. In the multiple regression model, it remains statistically significant with a positive coefficient.

Business meaning:

Stores with more visitors tend to generate higher sales. Increasing quality store traffic should be a major priority.

### Marketing Spend

Marketing spend is positively associated with monthly sales and is statistically significant in both the simple and multiple regression models.

Business meaning:

Marketing investment appears useful, but leadership should focus on marketing efficiency rather than spending more without tracking results. The goal should be marketing that increases footfall and conversion.

### Inventory Availability

Inventory availability has a positive and significant relationship with monthly sales.

Business meaning:

Even if customers visit the store, sales can be lost if products are unavailable. Better inventory availability helps stores convert demand into sales.

### Customer Rating

Customer rating is positive and statistically significant.

Business meaning:

Better customer experience is associated with stronger monthly sales. This may reflect better service, better store experience, or stronger customer loyalty.

### Staff Count

Staff count is positive and statistically significant.

Business meaning:

More staff may support better service, faster checkout, better shelf management, and stronger sales conversion.

### Holiday Flag

Holiday months are associated with higher monthly sales.

Business meaning:

Holiday periods should be planned carefully with enough inventory, staffing, and marketing support.

### Average Discount Percentage

Average discount percentage is statistically significant in the multiple regression model, but its coefficient is negative.

Business meaning:

This does not automatically mean discounts reduce sales. It may mean discounts are used during weaker demand periods or when stores are trying to push sales. This variable needs careful interpretation.

### Store Type: Residential

Residential store type has a negative and statistically significant coefficient compared with Airport stores.

Business meaning:

Residential stores may need closer review because, after controlling for other factors, they are estimated to perform lower than Airport stores.

## Which Variables Should Leadership Focus On?

Leadership should focus on variables that are statistically significant, have clear business meaning, and can be acted upon.

Recommended focus areas:

1. Increase quality footfall.
2. Improve marketing effectiveness.
3. Maintain strong inventory availability.
4. Improve customer experience and customer ratings.
5. Review staffing levels and staff productivity.
6. Prepare better for holiday months.
7. Investigate Residential store performance.
8. Use residual analysis to identify stores needing deeper review.

These areas are actionable and connected to the regression evidence.

## Which Variables Should Not Be Over-Interpreted?

### Store Type: High Street

`store_type_high_street` has a p-value of `0.4817`, which is greater than 0.05. This means the coefficient is not statistically significant.

Leadership should not conclude that High Street stores are meaningfully different from Airport stores based on this model.

### Store Type: Mall

`store_type_mall` has a p-value of `0.6883`, which is greater than 0.05. This means the coefficient is not statistically significant.

Leadership should not make broad conclusions about Mall stores based only on this coefficient.

### Average Discount Percentage

Although `avg_discount_pct` is statistically significant in the multiple regression model, it should still be interpreted carefully because the coefficient is negative.

A negative discount coefficient may reflect reverse business logic: stores may use discounts when demand is already weak. Therefore, discounting should not be treated as a simple lever that automatically increases or decreases sales.

### Intercept

The intercept should not be over-interpreted because it represents a theoretical case where all predictors are zero. This is not a realistic retail operating situation.

## What Business Action Would You Recommend?

The main recommendation is to use the multiple regression model as a decision-support tool and focus on improving controllable sales drivers.

Recommended actions:

1. Increase quality footfall through targeted local marketing, store visibility, and customer engagement.
2. Measure marketing campaigns based on whether they increase store visits and sales conversion.
3. Improve inventory availability, especially in stores with high footfall.
4. Strengthen customer experience to improve customer ratings.
5. Review staffing levels to ensure stores can handle customer traffic effectively.
6. Plan holiday months with stronger inventory, staffing, and campaign readiness.
7. Investigate Residential stores to understand why they are estimated to perform lower than Airport stores.
8. Review stores with large negative residuals to identify operational problems.
9. Study stores with large positive residuals to identify best practices.
10. Avoid relying only on discounting as a sales growth strategy.

### Residual-Based Business Recommendation

The residual analysis identified stores where actual sales were much higher or lower than predicted.

Stores with large positive residuals should be reviewed as possible best-practice stores. These stores may have strong execution, better local demand, stronger product mix, or better conversion than the model captures.

Stores with large negative residuals should be reviewed for operational issues. For example, STR-1017 in March 2025 had actual sales far below predicted sales. This store should be investigated for possible conversion problems, competition pressure, product mix issues, or local execution gaps.

Residual analysis should be used as a store review tool, not just as a statistical output.

## What Risks or Limitations Should Leadership Keep in Mind?

The model has several limitations.

### Omitted Variables

The dataset does not include every possible sales driver. Missing factors may include:

- Store size
- Product mix
- Pricing strategy
- Local income levels
- Local market demand
- Local competition quality
- Weather
- Local events
- Online sales influence
- Store manager quality
- Brand visibility

If these variables affect sales, the model may not fully explain store performance.

### Linear Relationship Assumption

The model assumes a linear relationship between each predictor and monthly sales. Real retail behavior may be non-linear. For example, marketing spend may help up to a point and then produce smaller returns.

### Historical Data Limitation

The model is based on historical data. Future customer behavior, competition, pricing, and economic conditions may change.

### Missing Value Treatment

Missing values in selected variables were handled using median imputation. This keeps records usable, but imputed values are still estimates rather than observed values.

### ToolPak Regression Limitation

Excel ToolPak provides regression output, but business interpretation still requires judgment. The model should be used with operational knowledge, not by itself.

## Why Does Regression Show Association but Not Automatically Prove Causation?

Regression identifies statistical relationships between variables. It shows whether variables move together after controlling for other variables in the model. However, this does not automatically prove that one variable causes another.

For example, marketing spend is positively associated with monthly sales. This does not prove that marketing spend alone caused higher sales. There are several possible explanations:

- Stores with higher expected sales may receive larger marketing budgets.
- Better locations may receive both higher marketing spend and higher footfall.
- A third factor, such as local demand, may increase both marketing activity and sales.
- Marketing may increase sales in some stores but not others depending on execution quality.

Similarly, footfall is strongly associated with sales, but the model does not prove what caused the footfall. Footfall may be influenced by location, brand awareness, local events, competitor activity, or store experience.

To prove causation, the business would need stronger methods such as controlled experiments, A/B testing, campaign lift studies, or before-and-after analysis with comparable control stores.

Therefore, regression should be used as decision support. It helps identify important patterns and priorities, but leadership should combine it with business judgment and further testing before making major decisions.

## Final Recommendation

Leadership should use the multiple regression model as the final model and focus on the most actionable drivers of monthly sales.

The strongest practical recommendation is:

Improve sales by increasing quality footfall, improving inventory availability, using marketing spend more efficiently, strengthening customer experience, planning better for holiday periods, and reviewing under-performing stores through residual analysis.

The business should avoid making decisions based only on discounting or broad store-type assumptions. Instead, leadership should use the regression findings to target deeper investigation and practical operational improvements.
