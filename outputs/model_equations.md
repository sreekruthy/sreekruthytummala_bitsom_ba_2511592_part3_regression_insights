# Model Equations

## Purpose

This document explains the regression equations used in the analysis, the meaning of each coefficient, the dummy variable approach, the reference category, and the final model selected.

## Dependent Variable

The dependent variable for all models is:

`monthly_sales`

This represents the monthly sales performance of a store.

## Simple Regression Equation Format

The general simple regression equation is:

`monthly_sales = intercept + coefficient x independent_variable`

## Simple Regression Model 1: Footfall

Equation:

`monthly_sales = 446410.58 + 35.68 x footfall`

Coefficient interpretation:

The coefficient for `footfall` is `35.68`. This means each additional unit of footfall is associated with an estimated `35.68` increase in monthly sales.

Business interpretation:

Footfall is a strong business driver because higher customer traffic gives stores more chances to sell. This model has an R-squared of `0.7363`, meaning footfall alone explains about 73.63% of monthly sales variation.

Usefulness:

This variable appears useful because the relationship is positive, statistically significant, and easy to interpret in business terms.

## Simple Regression Model 2: Marketing Spend

Equation:

`monthly_sales = 560777.35 + 2.13 x marketing_spend`

Coefficient interpretation:

The coefficient for `marketing_spend` is `2.13`. This means each additional unit of marketing spend is associated with an estimated `2.13` increase in monthly sales.

Business interpretation:

Marketing spend is positively associated with sales. However, the R-squared is `0.1672`, so marketing spend alone explains less variation than footfall.

Usefulness:

This variable appears useful, but it is not as strong as footfall when used by itself.

## Simple Regression Model 3: Average Discount Percentage

Equation:

`monthly_sales = 697835.63 - 138730.45 x avg_discount_pct`

Coefficient interpretation:

The coefficient for `avg_discount_pct` is `-138730.45`. This indicates a negative relationship in the simple regression model.

Business interpretation:

The p-value is `0.1040`, which is above 0.05, so average discount percentage is not statistically significant in the simple regression. Discounting alone does not explain sales performance well.

Usefulness:

This variable does not appear useful as a standalone predictor. It should be interpreted only after considering other variables.

## Dummy Variable Approach

Dummy variables were created for `store_type` because regression requires numerical inputs.

The original store type categories were:

- Airport
- High Street
- Mall
- Residential

The dummy variables created were:

- `store_type_high_street`
- `store_type_mall`
- `store_type_residential`

### Reference category used

The reference category is:

`Airport`

Airport was not given its own dummy variable. Airport is represented when all three store-type dummy variables are 0.

This avoids dummy variable redundancy. If all store-type categories were included with an intercept, the model would have perfect multicollinearity because the dummy variables would add up to 1 for every row.

## Multiple Regression Equation

The selected multiple regression equation is:

`monthly_sales = 69706.91 + 1.16(marketing_spend) + 27.90(footfall) - 73572.78(avg_discount_pct) + 3129.92(inventory_availability_pct) + 12616.70(clean_customer_rating) + 3184.96(staff_count) + 13822.07(holiday_flag) - 4555.94(store_type_high_street) + 2922.41(store_type_mall) - 26500.27(store_type_residential)`

## Multiple Regression Coefficient Explanation

### Intercept

The intercept is `69706.91`.

It is the model's estimated monthly sales when all predictors are zero and the store is in the Airport reference category. This is mainly a mathematical baseline and should not be heavily interpreted because zero values for variables like footfall, staff count, and inventory availability are not realistic operating conditions.

### Marketing Spend

Coefficient: `1.16`

P-value: `9.83E-18`

Direction: Positive

Interpretation:

Holding other variables constant, higher marketing spend is associated with higher monthly sales. This variable is statistically significant.

### Footfall

Coefficient: `27.90`

P-value: `2.03E-24`

Direction: Positive

Interpretation:

Holding other variables constant, higher customer footfall is associated with higher monthly sales. This is one of the strongest and clearest business drivers in the model.

### Average Discount Percentage

Coefficient: `-73572.78`

P-value: `0.0431`

Direction: Negative

Interpretation:

Holding other variables constant, higher discount percentage is associated with lower monthly sales. This variable is statistically significant, but it is difficult to interpret. It may mean discounts are used more often when demand is weak, not necessarily that discounts cause sales to decrease.

### Inventory Availability Percentage

Coefficient: `3129.92`

P-value: `6.09E-11`

Direction: Positive

Interpretation:

Higher inventory availability is associated with higher monthly sales. This has strong business meaning because stores cannot convert customer demand into sales if products are unavailable.

### Clean Customer Rating

Coefficient: `12616.70`

P-value: `0.0090`

Direction: Positive

Interpretation:

Higher customer rating is associated with higher monthly sales. Better customer experience may support better conversion and repeat visits.

### Staff Count

Coefficient: `3184.96`

P-value: `0.0122`

Direction: Positive

Interpretation:

Higher staff count is associated with higher monthly sales. This may reflect better service capacity, faster customer handling, and stronger store operations.

### Holiday Flag

Coefficient: `13822.07`

P-value: `0.0383`

Direction: Positive

Interpretation:

Holiday months are associated with higher monthly sales than non-holiday months, holding other variables constant.

### Store Type: High Street

Coefficient: `-4555.94`

P-value: `0.4817`

Direction: Negative

Interpretation:

High Street stores are estimated to have lower sales than Airport stores, holding other variables constant. However, this result is not statistically significant, so it should not be over-interpreted.

### Store Type: Mall

Coefficient: `2922.41`

P-value: `0.6883`

Direction: Positive

Interpretation:

Mall stores are estimated to have higher sales than Airport stores, holding other variables constant. However, this result is not statistically significant, so it should not be treated as a reliable store-type effect.

### Store Type: Residential

Coefficient: `-26500.27`

P-value: `0.0002`

Direction: Negative

Interpretation:

Residential stores are estimated to have lower monthly sales than Airport stores, holding other variables constant. This result is statistically significant.

## Final Model Selected

The final selected model is the multiple regression model.

## Reason for Selecting the Final Model

The multiple regression model was selected because:

- It has the highest R-squared: `0.8281`.
- It has a strong adjusted R-squared: `0.8226`.
- It includes several business drivers together.
- It includes store-type dummy variables.
- It gives more useful business insight than a one-variable model.
- It supports stronger recommendations for leadership.
