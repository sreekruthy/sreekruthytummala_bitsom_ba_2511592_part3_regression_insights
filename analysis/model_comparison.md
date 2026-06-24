# Model Comparison

## Purpose

This document compares the simple regression models and the multiple regression model used to explain monthly sales performance across stores.

The comparison follows the required items from the assignment:

| Required Item | Explanation |
|---|---|
| Model name | Name each model clearly |
| Variables used | List dependent and independent variables |
| R-squared | Compare explanatory power |
| Significant variables | Identify variables with useful p-values |
| Business usefulness | Explain whether the model helps decision-making |
| Limitations | Explain what the model does not capture |

## Significance Rule Used

A variable is treated as statistically significant when its p-value is below `0.05`.

A p-value below 0.05 means the relationship is useful enough to discuss as statistically significant in this analysis. A p-value above 0.05 means the result should be treated carefully and not over-interpreted.

## Model Comparison Table

| Model Name | Variables Used | R-squared | Significant Variables | Business Usefulness | Limitations |
|---|---|---:|---|---|---|
| Simple Regression - Footfall | Dependent: `monthly_sales`; Independent: `footfall` | 0.7363 | `footfall` is significant because p-value = `4.75E-94` | Very useful. Footfall directly measures customer traffic and explains a large share of monthly sales variation. | Does not control for marketing, inventory, staffing, discounting, customer rating, holidays, or store type. |
| Simple Regression - Marketing Spend | Dependent: `monthly_sales`; Independent: `marketing_spend` | 0.1672 | `marketing_spend` is significant because p-value = `2.48E-14` | Useful. It shows that marketing spend is positively associated with monthly sales. | Explains much less variation than footfall and does not show whether marketing remains important after controlling for other variables. |
| Simple Regression - Avg Discount | Dependent: `monthly_sales`; Independent: `avg_discount_pct` | 0.0083 | No significant variable at 5% level because p-value = `0.1040` | Limited usefulness. It shows that discounting alone is not a strong sales predictor. | Does not control for demand, marketing, store traffic, inventory, or whether discounts are used in weak-sales situations. |
| Multiple Regression Model | Dependent: `monthly_sales`; Independents: `marketing_spend`, `footfall`, `avg_discount_pct`, `inventory_availability_pct`, `clean_customer_rating`, `staff_count`, `holiday_flag`, `store_type_high_street`, `store_type_mall`, `store_type_residential` | 0.8281 | `marketing_spend`, `footfall`, `avg_discount_pct`, `inventory_availability_pct`, `clean_customer_rating`, `staff_count`, `holiday_flag`, `store_type_residential` | Most useful. It evaluates several business drivers together and gives a stronger basis for recommendation. | Still does not prove causation and may miss store size, product mix, local market conditions, competition quality, weather, and manager quality. |

## Model 1: Simple Regression - Footfall

### Model Name

`Simple Regression - Footfall`

### Variables Used

Dependent variable:

`monthly_sales`

Independent variable:

`footfall`

### R-squared

R-squared is `0.7363`.

This means footfall alone explains about 73.63% of the variation in monthly sales. Among the simple regression models, this is the strongest explanatory power.

### Significant Variables

`footfall` is statistically significant because its p-value is `4.75E-94`, which is below 0.05.

### Business Usefulness

This model is very useful for decision-making because store traffic has a clear business link to sales. More visitors usually create more sales opportunities.

### Limitations

The model only studies footfall. It does not control for marketing spend, inventory availability, customer rating, staff count, discounting, holiday periods, or store type. It cannot explain whether high footfall is caused by marketing, location, seasonality, or other factors.

## Model 2: Simple Regression - Marketing Spend

### Model Name

`Simple Regression - Marketing Spend`

### Variables Used

Dependent variable:

`monthly_sales`

Independent variable:

`marketing_spend`

### R-squared

R-squared is `0.1672`.

This means marketing spend alone explains about 16.72% of the variation in monthly sales.

### Significant Variables

`marketing_spend` is statistically significant because its p-value is `2.48E-14`, which is below 0.05.

### Business Usefulness

The model is useful because it shows a positive relationship between marketing spend and monthly sales. This supports the idea that marketing investment is associated with sales performance.

### Limitations

The model has limited explanatory power compared with the footfall model. It does not show whether marketing spend directly causes higher sales, and it does not control for customer traffic, inventory availability, staffing, holidays, or store type.

## Model 3: Simple Regression - Avg Discount

### Model Name

`Simple Regression - Avg Discount`

### Variables Used

Dependent variable:

`monthly_sales`

Independent variable:

`avg_discount_pct`

### R-squared

R-squared is `0.0083`.

This means average discount percentage explains only about 0.83% of the variation in monthly sales.

### Significant Variables

There are no significant variables in this simple model at the 5% significance level. The p-value for `avg_discount_pct` is `0.1040`, which is greater than 0.05.

### Business Usefulness

This model has limited usefulness. It suggests discount percentage alone is not a strong predictor of monthly sales.

### Limitations

Discounting is difficult to interpret by itself. A higher discount may be used to respond to weak demand, clear inventory, or run promotions. Without controlling for other variables, this model does not explain why discounts are happening or whether they help sales.

## Model 4: Multiple Regression Model

### Model Name

`Multiple Regression Model`

### Variables Used

Dependent variable:

`monthly_sales`

Independent variables:

- `marketing_spend`
- `footfall`
- `avg_discount_pct`
- `inventory_availability_pct`
- `clean_customer_rating`
- `staff_count`
- `holiday_flag`
- `store_type_high_street`
- `store_type_mall`
- `store_type_residential`

### R-squared

R-squared is `0.8281`.

Adjusted R-squared is `0.8226`.

This means the model explains about 82.81% of the variation in monthly sales. This is the highest explanatory power among the models compared.

### Significant Variables

The significant variables are:

- `marketing_spend`, p-value = `9.83E-18`
- `footfall`, p-value = `2.03E-24`
- `avg_discount_pct`, p-value = `0.0431`
- `inventory_availability_pct`, p-value = `6.09E-11`
- `clean_customer_rating`, p-value = `0.0090`
- `staff_count`, p-value = `0.0122`
- `holiday_flag`, p-value = `0.0383`
- `store_type_residential`, p-value = `0.0002`

The statistically weak variables are:

- `store_type_high_street`, p-value = `0.4817`
- `store_type_mall`, p-value = `0.6883`

### Business Usefulness

This is the most useful model for decision-making because it considers multiple drivers at the same time. It shows which factors remain important after controlling for other variables.

The model suggests that leadership should focus on footfall, marketing effectiveness, inventory availability, customer experience, staffing, holiday planning, and the performance gap for Residential stores.

### Limitations

The model does not capture every business factor that may affect sales. Missing factors may include store size, product mix, pricing strategy, local income levels, competitor quality, local events, weather, online demand, and store manager quality.

The model also shows association, not causation. A significant coefficient does not automatically prove that changing that variable will cause sales to change by the coefficient amount.

## Final Model Selection

The multiple regression model is selected as the final model.

Reasons:

- It has the highest R-squared at `0.8281`.
- It has a strong adjusted R-squared at `0.8226`.
- It includes at least three numerical independent variables.
- It includes store-type dummy variables.
- It gives more complete business insight than a simple one-variable model.
- It supports practical recommendations for marketing, traffic, inventory, staffing, and store performance review.
