# What Drives the Price of a Used Car?

## Project Overview

This project analyzes a used-car listings dataset to identify the factors most associated with higher and lower vehicle prices. The audience is a used-car dealership that wants practical guidance for acquisition, pricing, merchandising, and risk control.

The analysis follows the CRISP-DM process and is implemented in [`prompt_II.ipynb`](prompt_II.ipynb).

## Business Question

What vehicle characteristics most strongly influence the listed price of a used car?

## Data

The dataset contains Craigslist used-car listings with fields such as price, year, manufacturer, model, condition, cylinders, fuel type, odometer, title status, transmission, drivetrain, vehicle type, paint color, state, and region.

Because the raw data is noisy, the notebook performs substantial cleaning and feature engineering before modeling. The final analysis uses 350,161 cleaned rows after excluding invalid listings and the top 5% of prices, which scopes the model to ordinary dealership inventory rather than exotic, collector, or likely erroneous listings.

## Methodology

The notebook follows these steps:

- Define the business problem as a regression and interpretation task.
- Inspect missingness, outliers, suspicious prices, and categorical cardinality.
- Clean invalid prices, unrealistic years, odometer outliers, and messy categorical values.
- Engineer vehicle age, mileage intensity, title-risk, drivetrain, luxury-brand, make-model, and interaction features.
- Compare models using MAE as the primary metric, with RMSE and R² as supporting metrics.
- Interpret price drivers using Ridge coefficients, permutation importance, EDA, and business judgment.

## Models Used

- Median baseline
- Linear Regression
- Ridge Regression
- Log-price Ridge Regression
- Histogram Gradient Boosting Regressor

The boosted tree is the best predictive model. Ridge is retained as the clearest interpretation model because its encoded coefficients and permutation importance are easier to connect to dealership recommendations.

## Evaluation Metric

MAE is the primary metric because it is easy to explain in dollars: it represents the average absolute pricing error. RMSE is also reported because it penalizes large misses, and R² is included as a general measure of model fit.

## Model Results

| Model | CV MAE | Test MAE | Test RMSE | Test R² |
|---|---:|---:|---:|---:|
| HistGradientBoosting challenger | $2,993.08 | $2,983.47 | $4,493.08 | 0.85 |
| Ridge Regression | $3,175.48 | $3,152.80 | $4,817.89 | 0.82 |
| Log-price Ridge | $3,399.34 | $3,380.46 | $5,283.04 | 0.79 |
| Linear Regression | $3,560.80 | $3,554.13 | $5,274.11 | 0.79 |
| Median baseline | $9,536.56 | $9,568.71 | $11,685.83 | -0.04 |

## Key Findings

1. Vehicle age is one of the strongest drivers of price. Newer vehicles generally command higher listed prices.
2. Mileage strongly affects value. Lower odometer readings are associated with higher prices.
3. Title status matters. Clean-title vehicles carry stronger value than vehicles with title issues.
4. Manufacturer, model, and make-model combinations add important pricing signal.
5. Vehicle type, drivetrain, fuel type, and luxury-brand status help explain meaningful price differences.

## Recommendations for Dealers

Prioritize newer, lower-mileage vehicles with clean titles, desirable body types, and strong make-model combinations. Use mileage, age, title status, and condition as primary pricing adjustment factors. Highlight low mileage, clean title, good condition, desirable drivetrain, and popular body type in listings. Be cautious with high-mileage vehicles, title issues, missing condition details, and incomplete listings unless acquisition cost leaves enough margin.

## Next Steps

Future work could improve the analysis by adding days-on-market, actual transaction prices, trim-level data, vehicle history reports, regional demand indicators, and SHAP-based explanations for the boosted model.

