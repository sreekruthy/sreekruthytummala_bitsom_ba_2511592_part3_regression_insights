# Residual Analysis

## Purpose

This document explains the residual analysis for the selected final model, which is the multiple regression model.

Residual analysis is used to understand where the model predicts well and where it does not. It helps identify stores that performed much better or much worse than expected after considering the variables included in the model.

## Selected Final Model Used for Prediction

The selected final model is the multiple regression model using:

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

The dependent variable is:

`monthly_sales`

## Predicted Sales Calculation

Predicted sales were calculated for each record using the coefficients from the selected multiple regression model.

The prediction equation used was:

`predicted_sales = intercept + b1(marketing_spend) + b2(footfall) + b3(avg_discount_pct) + b4(inventory_availability_pct) + b5(clean_customer_rating) + b6(staff_count) + b7(holiday_flag) + b8(store_type_high_street) + b9(store_type_mall) + b10(store_type_residential)`

This calculation was completed in the `Predictions_residuals` sheet of `analysis/regression_workbook.xlsx`.

## Residual Calculation

The residual formula is:

`residual = actual monthly sales - predicted monthly sales`

Interpretation:

- Positive residual: actual sales were higher than predicted.
- Negative residual: actual sales were lower than predicted.
- Residual close to zero: the model predicted sales relatively accurately.

## Largest Positive Residuals

The largest positive residuals identify records where the store performed much better than the model predicted.

| Rank | Store ID | Month | Region | Store Type | Actual Sales | Predicted Sales | Residual |
|---:|---|---|---|---|---:|---:|---:|
| 1 | STR-1030 | 2025-02-01 | West | Residential | 820,519.04 | 717,077.41 | 103,441.63 |
| 2 | STR-1028 | 2025-04-01 | East | Mall | 713,611.16 | 612,453.45 | 101,157.71 |
| 3 | STR-1051 | 2025-02-01 | East | Airport | 787,715.51 | 692,203.02 | 95,512.49 |
| 4 | STR-1064 | 2025-02-01 | South | Airport | 799,046.94 | 704,038.78 | 95,008.16 |
| 5 | STR-1027 | 2025-03-01 | West | High Street | 795,153.84 | 702,083.25 | 93,070.59 |

## Business Meaning of Positive Residuals

These stores generated more sales than expected based on the model inputs.

Possible explanations include:

- Strong local demand not captured by the dataset
- Better store execution
- Better sales conversion from customer visits
- Stronger product mix
- Better local promotions
- Better store management
- Better customer service than reflected in the rating
- Local events or market conditions not included in the model

These stores should be studied as possible best-practice examples. For example, STR-1030, STR-1028, STR-1051, STR-1064, and STR-1027 may have store-level practices or local advantages that are not fully represented by the regression variables.

## Largest Negative Residuals

The largest negative residuals identify records where the store performed much worse than the model predicted.

| Rank | Store ID | Month | Region | Store Type | Actual Sales | Predicted Sales | Residual |
|---:|---|---|---|---|---:|---:|---:|
| 1 | STR-1017 | 2025-03-01 | West | High Street | 685,379.08 | 846,187.37 | -160,808.29 |
| 2 | STR-1023 | 2025-02-01 | South | Mall | 627,171.90 | 753,975.25 | -126,803.35 |
| 3 | STR-1012 | 2025-01-01 | West | Residential | 595,467.60 | 714,141.07 | -118,673.47 |
| 4 | STR-1007 | 2025-02-01 | West | Mall | 800,451.94 | 900,671.79 | -100,219.85 |
| 5 | STR-1009 | 2025-01-01 | North | Residential | 641,865.03 | 736,471.60 | -94,606.57 |

## Business Meaning of Negative Residuals

These stores generated less sales than expected based on the model inputs.

Possible explanations include:

- Weak conversion even with reasonable footfall
- Local competition pressure
- Poor product mix
- Inventory availability may not reflect availability of the right products
- Marketing spend may not have been effective locally
- Store operations or service issues
- Pricing or discounting issues
- Local demand weakness not captured by the model

These stores should be reviewed for operational improvement. STR-1017 has the largest negative residual, so it should be a priority for deeper review.

## Under-Prediction and Over-Prediction by Store Type

The model under-predicts records with large positive residuals. In the top positive residual list, the store types include Residential, Mall, Airport, and High Street. This means under-prediction is not limited to only one store type. The model may be missing store-level advantages that cut across different formats, such as local execution, product mix, or market demand.

The model over-predicts records with large negative residuals. In the top negative residual list, the store types include High Street, Mall, and Residential. This suggests that some non-Airport stores may have visible inputs that look strong in the model but still fail to convert those inputs into actual sales.

Residential stores deserve special attention because the multiple regression coefficient for `store_type_residential` is negative and statistically significant. This means Residential stores are estimated to perform lower than Airport stores after controlling for other variables. However, STR-1030 is a Residential store with the largest positive residual, so Residential performance is not uniformly weak. Some Residential stores may be outperforming while others underperform.

Mall stores also appear in both positive and negative residual lists. Because the `store_type_mall` coefficient is not statistically significant, leadership should not assume all Mall stores behave the same way. Store-level review is more useful than broad assumptions.

## Business Use of Residual Analysis

Residual analysis helps leadership identify where the model is not fully explaining performance.

Recommended uses:

- Study large positive residual stores to identify best practices.
- Investigate large negative residual stores for operational issues.
- Compare stores within the same store type to avoid broad generalizations.
- Use residual outliers to identify missing variables for future analysis.
- Combine model evidence with field-level business review.

## Limitation

Residual analysis identifies unusual performance, but it does not prove why that performance happened. A large positive or negative residual should be treated as a signal for deeper investigation, not as a final diagnosis.
