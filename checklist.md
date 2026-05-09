# Assignment 11.1 Checklist

## Project Organization

- [x] README file includes summary of findings.
- [x] README links to the completed notebook.
- [x] Jupyter notebook has clear headings following the CRISP-DM workflow.
- [x] Files and folders have appropriate names.
- [x] Submission folder excludes extra course/starter materials and includes only project files.

## Syntax and Code Quality

- [x] Libraries are imported and aliased correctly.
- [x] Notebook runs without errors.
- [x] Notebook has no captured warning output.
- [x] Outputs are kept reasonably compact.
- [x] Demonstrates competency with pandas for inspection, cleaning, grouping, and feature engineering.
- [x] Demonstrates competency with seaborn/matplotlib for EDA visualizations.
- [x] Code comments explain important decisions and workflow steps.
- [x] Variable names are clear and sensible.

## Visualizations

- [x] Includes continuous-variable plots for price, log price, vehicle age, and odometer.
- [x] Includes categorical-variable plots for condition, title status, vehicle type, fuel type, manufacturer, age bucket, mileage bucket, and drivetrain.
- [x] Plots have readable labels.
- [x] Plots have descriptive titles.
- [x] Axes are legible.
- [x] Subplots are used where useful.
- [x] Plots are scaled appropriately for notebook viewing.

## Data Preparation

- [x] Invalid or suspicious low prices are removed.
- [x] Extreme high-price listings are handled with a documented 95th-percentile business-scope cap.
- [x] Unrealistic vehicle years are removed.
- [x] Unrealistic odometer values are removed.
- [x] Missing categorical values are preserved as `"unknown"` where appropriate.
- [x] Missingness indicators are added for important dirty fields.
- [x] High-cardinality `model` is simplified.
- [x] `region`, `model_simplified`, and `make_model` are retained because they improve predictive performance.
- [x] Numeric and categorical preprocessing are handled inside sklearn pipelines.
- [x] Train/test split is used.

## Feature Engineering

- [x] `vehicle_age`
- [x] `odometer_log`
- [x] `miles_per_year`
- [x] age and mileage buckets
- [x] title-status flags
- [x] drivetrain, diesel, manual, truck/SUV, and luxury-brand indicators
- [x] `cylinders_num`
- [x] `condition_rank`
- [x] `model_simplified`
- [x] `make_model`
- [x] interaction features such as `age_x_odometer_log`, `luxury_x_age`, and `truck_x_4wd`

## Modeling

- [x] Multiple regression models are used.
- [x] Median baseline is included.
- [x] Linear Regression is included.
- [x] Ridge Regression is included.
- [x] Log-price Ridge is included.
- [x] Histogram Gradient Boosting challenger is included.
- [x] Cross-validation is performed.
- [x] Grid search is used for Ridge/log-Ridge hyperparameter tuning.
- [x] Coefficients are interpreted for Ridge.
- [x] Permutation importance is included for feature interpretation.
- [x] Evaluation metric is clearly identified.
- [x] MAE is used as the primary business-facing metric.
- [x] RMSE and R² are included as supporting metrics.

## Evaluation

- [x] Models are compared in a single results table.
- [x] Cross-validated metrics are included for the best boosted-tree model.
- [x] Test-set metrics are included.
- [x] Best model is identified by holdout MAE.
- [x] Notebook distinguishes between the best predictive model and the most interpretable model.
- [x] Overfitting risk is partially addressed by comparing CV and test performance.

## Findings

- [x] Business problem is clearly stated.
- [x] Notebook includes organized data cleaning.
- [x] Descriptive statistics are interpreted through EDA.
- [x] Model results are interpreted clearly.
- [x] Findings are written for a nontechnical dealership audience.
- [x] Actionable recommendations are highlighted.
- [x] Next steps are included.

## Submission Notes

- [x] Completed notebook: `prompt_II_codex.ipynb`
- [x] README: `README.md`
- [x] Checklist: `checklist.md`
- [x] Dataset path used by notebook: `data/vehicles.csv`
- [x] GitHub-ready folder excludes office-hour recordings, starter kits, duplicate scaffold notebooks, and unrelated course materials.
