# Linear Regression for Oil Rate Prediction Using Python

## Project Overview

This project demonstrates how to apply **Simple Linear Regression** in Petroleum Engineering to investigate the relationship between Bottom-Hole Pressure (BHP) and oil production rate.

Using Python and Scikit-learn, a Linear Regression model is trained to predict oil production based on pressure measurements from well data.

The project provides a practical introduction to Machine Learning applications in Petroleum Engineering.

## Project Objectives

- Understand the basic concept of Linear Regression.
- Explore the relationship between well pressure and oil production.
- Prepare input and target variables.
- Split data into training and testing sets.
- Train a Linear Regression model.
- Evaluate model performance using R² and RMSE.
- Visualize actual well data and the regression line.

## Dataset Description

The dataset used in this project is stored in a Pandas DataFrame named `production_valid_df`.

| Variable | Description | Unit |
|---|---|---|
| pressure_psi | Bottom-Hole Pressure | psi |
| actual_oil_bopd | Actual Oil Production Rate | BOPD |

**BOPD:** Barrels of Oil Per Day.

The dataset is assumed to have been validated and cleaned before model development.

## Technologies and Libraries

The following Python libraries are used:

- **NumPy:** Numerical operations.
- **Pandas:** Data manipulation and analysis.
- **Matplotlib:** Data visualization.
- **Scikit-learn:** Machine Learning and model evaluation.

## Methodology

### 1. Feature Selection

The input variable (X) is Bottom-Hole Pressure, while the target variable (y) is actual oil production rate.

```python
X = production_valid_df[['pressure_psi']]
y = production_valid_df['actual_oil_bopd']
```

### 2. Train-Test Split

The dataset is divided into two subsets:

- 80% for training.
- 20% for testing.

```python
X_train, X_test, y_train, y_test = train_test_split(
    X, y,
    test_size=0.2,
    random_state=42
)
```

### 3. Model Training

A Linear Regression model is developed using Scikit-learn.

```python
model = LinearRegression()
model.fit(X_train, y_train)
```

### 4. Prediction

The trained model predicts oil production rates using the test dataset.

```python
y_pred = model.predict(X_test)
```

### 5. Model Evaluation

Model performance is evaluated using two metrics:

**R² Score**

Measures how well the model explains the variation in oil production rates.

**Root Mean Squared Error (RMSE)**

Measures the prediction error magnitude, with greater sensitivity to large errors.

```python
print(f"R2 Score: {r2_score(y_test, y_pred)}")

print(
    f"RMSE: "
    f"{mean_squared_error(y_test, y_pred)**0.5}"
)
```

## Visualization

The project visualizes:

- Actual well data using a scatter plot.
- The fitted Linear Regression line.
- The relationship between Bottom-Hole Pressure and oil production rate.

The visualization helps illustrate how Linear Regression captures a linear trend in the observed data.

## Linear Regression Equation

The model follows the general linear equation:

\[
Oil\ Rate = \beta_0 + \beta_1 \times BHP
\]

Where:

- β₀ = Intercept
- β₁ = Regression coefficient (slope)
- BHP = Bottom-Hole Pressure

## Key Takeaways

- Linear Regression is a simple and interpretable Machine Learning method.
- Pressure measurements can be explored as predictors of oil production.
- Train-test splitting helps evaluate model performance on unseen observations.
- R² and RMSE provide complementary information about prediction quality.
- Visualization helps communicate model behavior and results.

## Limitations

This project is an introductory educational example.

- Only one input feature is used.
- A linear relationship is assumed.
- The model does not account for other production variables such as Water Cut, GOR, permeability, or fluid properties.
- A statistical relationship does not necessarily imply a physical or causal relationship.
- Model performance depends on data quality and the representativeness of the dataset.

The model should not be considered a standalone production forecasting tool without further validation.

## Future Improvements

Possible extensions include:

1. Multiple Linear Regression using BHP, Water Cut, and GOR.
2. Correlation analysis and Multicollinearity assessment using VIF.
3. Residual analysis and model diagnostics.
4. Comparison of different regression models.
5. Statistical Hypothesis Testing using OLS and P-values.

## Applications in Petroleum Engineering

Linear Regression can be explored in several petroleum engineering applications:

- Oil production rate estimation.
- Pressure-production relationship analysis.
- Permeability and porosity estimation.
- Production performance analysis.

## Author

This project is part of an educational series exploring Python, Machine Learning, and Data Science applications in Petroleum Engineering.

**Learning Machine Learning through practical Petroleum Engineering examples.**

If you find this project useful, feel free to star the repository and share your feedback.
