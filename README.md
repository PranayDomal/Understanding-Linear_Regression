# **Linear Regression Analysis on Advertising Dataset**
Understanding - Linear Regression through Advertising Dataset

## Project Overview

This project explores and validates **Linear Regression models** to understand how different advertising channels—**TV, Radio, and Newspaper**—influence product **Sales**.
The goal is not only to build predictive models but to **demonstrate a correct**, **assumption-driven regression workflow**, including EDA, model diagnostics, and interpretation.

## Dataset Description

- Dataset: Advertising Dataset
- Observations: 200
- Features:
  - `TV` – TV advertising spend
  - `Radio` – Radio advertising spend
  - `Newspaper` – Newspaper advertising spend
- Target:
  - `Sales` – Product sales

The dataset is fully numeric, contains no missing values, and requires minimal preprocessing (removal of a non-informative index column).

## Exploratory Data Analysis (EDA)

- Key findings from EDA:
- The target variable (Sales) follows an approximately normal distribution with no extreme outliers.
- TV advertising shows a strong linear relationship with Sales.
- Radio advertising shows a moderate but noisier linear trend.
- Newspaper advertising shows little to no linear relationship with Sales.
- Correlation analysis confirms:
  - TV → strong correlation
  - Radio → moderate correlation
  - Newspaper → weak correlation
- Low inter-feature correlations indicate minimal multicollinearity, making Linear Regression appropriate.

## Modeling Approach

### Simple Linear Regression (TV → Sales)

A **Simple Linear Regression** model was built using **TV advertising spend only**, to clearly understand regression fundamentals such as slope, intercept, and residual behavior.

**Performance:**
| Metric   | Value  |
| -------- | ------ |
| R² Score | 0.6767 |
| RMSE     | 3.19   |
| MAE      | 2.44   |

**Key Insight:**
TV advertising alone explains ~67% of the variance in Sales, making it a strong but incomplete predictor.

### Multiple Linear Regression (TV + Radio + Newspaper → Sales)

The model was extended to include all advertising channels to capture their combined linear effect.

**Model Coefficients:**
| Feature   | Coefficient |
| --------- | ----------- |
| TV        | 0.0498      |
| Radio     | 0.1826      |
| Newspaper | −0.0115     |

**Performance:**
| Metric   | Value  |
| -------- | ------ |
| R² Score | 0.9097 |
| RMSE     | 1.69   |
| MAE      | 1.44   |

**Key Insight:**
Including multiple predictors significantly improves model performance, demonstrating that Sales are influenced by a **combination of advertising channels**, not TV alone.

## Model Diagnostics

**Residual Analysis**
- Residuals are centered around zero for both models.
- The Multiple Linear Regression model shows reduced variance compared to the simple model.
- Residual distributions are approximately normal.
- No systematic patterns are observed against predictors, confirming linearity assumptions.

**Multicollinearity Check (VIF)**

| Feature   | VIF   |
| --------- | ----- |
| TV        | ~2.50 |
| Radio     | ~3.49 |
| Newspaper | ~3.27 |

All VIF values are well below critical thresholds, confirming no multicollinearity issues.

## Why Newspaper Is a Weak Predictor

- Scatter plots show no clear linear relationship with Sales.
- Correlation with Sales is weak compared to TV and Radio.
- The regression coefficient is close to zero and slightly negative.
- Low VIF confirms that its weakness is intrinsic, not due to redundancy.

Despite this, Newspaper was retained to:
- Control for confounding effects
- Preserve interpretability
- Demonstrate principled feature evaluation

## Final Conclusion

- Simple Linear Regression with TV provides a strong and interpretable baseline.
- Multiple Linear Regression significantly improves predictive accuracy and error reduction.
- Model assumptions are validated through residual diagnostics and VIF analysis.
- The final model is statistically sound, interpretable, and well-justified.

This project demonstrates a correct, professional approach to Linear Regression, focusing on understanding, validation, and explanation—not just performance metrics.

## Limitations

- Assumes strictly linear relationships.
- Mild heteroscedasticity at higher advertising spends.
- Small dataset limits generalization.
- External factors (seasonality, competition, branding) are not included.

## Tools & Libraries

- Python
- pandas, numpy
- matplotlib, seaborn
- scikit-learn
- statsmodels (VIF)

## Repository Structure
```
├── Advertising.csv
├── Linear_Regression_Advertising.ipynb
├── README.md
```

## How to Run

1. Clone the repository:
```bash
git clone https://github.com/PranayDomal/Understanding-Linear_Regression.git
```
2. Navigate to the folder:
```bash
cd Understanding-Linear_Regression
```
3. Run the notebook:
```bash
jupyter notebook Linear_Regression_Advertising.ipynb
```

## Author

https://www.linkedin.com/in/pranay-domal-a641bb368/
