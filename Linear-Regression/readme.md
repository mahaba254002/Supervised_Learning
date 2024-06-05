# Linear Regression

## Table of Contents
- [Introduction](#introduction)
- [Example Applications of Linear Regression](#example-applications-of-linear-regression)
- [Objective](#objective)
- [Key Terms](#key-terms)
  - [Centroid](#1-centroid)
  - [Observed Value (ε)](#2-Observed-Value)
  - [Residuals (ε)](#3-residuals-ε)
  - [Error](#4-error)
  - [Sum of Squared Errors (SSE)](#5-sum-of-squared-errors-sse)
  - [Total Sum of Squares (SST)](#6-total-sum-of-squares-sst)
  - [Mean Squared Error (MSE)](#7-mean-squared-error-mse)

## Introduction
Linear regression is a branch of regression analysis that focuses on modeling the relationship between a dependent variable and one or more independent variables by fitting a linear equation to observed data.
- Assumes there is a linear relationship between the variables.

## Example Applications of Linear Regression
- Analyzing trends and sales estimates
- Salary forecasting
- Real estate prediction
- Arriving at ETAs in traffic

## Objective
The aim of linear regression is to find a line that best fits the data, called the **Least Squares Line**, which minimizes the sum of the squared residuals (SSE). 
- The equation for the line is \[ \hat{y} = b_0 + b_1 x + ε \]
![Regression Equation](linear-regression-equations.jpg)


Where:
- \( \hat{y} \) is the predicted value of y.
- \( b_0 \) is the y-intercept of the line.
- \( b_1 \) is the slope of the line.

## Key Terms
- In this explanation we will use sample data for easy understanding.Given the following dataset:
| Independent (x) | Actual (y) |
|-----------------|------------|
| 1               | 4          |
| 2               | 2          |
| 3               | 5          |
| 4               | 7          |
| 5               | 3          |

- Given the above table we will explain the terms

### 1. Centroid
- Mean of the x-variable and mean of the y-variable.
- The best-fit line must always pass through this point.
\[ \sum x = 1 + 2 + 3 + 4 + 5 = 15 \]
\[ \sum y = 4 + 2 + 5 + 7 + 3 = 21 \]
\[ \bar{x} = \frac{15}{5} = 3 \]
\[ \bar{y} = 4.2 \]
The centroid is \((3, 4.2)\).

### 2. Observed value(Predicted)
- It is calculated using the regression equation
\[ \hat{y} = b_0 + b_1 x + ε \]
\[ \sum xy = (1 \cdot 4) + (2 \cdot 2) + (3 \cdot 5) + (4 \cdot 7) + (5 \cdot 3) = 4 + 4 + 15 + 28 + 15 = 66 \]
\[ \sum x^2 = 1^2 + 2^2 + 3^2 + 4^2 + 5^2 = 1 + 4 + 9 + 16 + 25 = 55 \]
\[ n = 5 \]

- Now, let's compute \( b_1 \) and \( b_0 \):

\[ b_1 = \frac{5(66) - (15)(21)}{5(55) - (15)^2} \]
\[ b_1 = \frac{330 - 315}{275 - 225} \]
\[ b_1 = \frac{15}{50} \]
\[ b_1 = 0.3 \]

\[ b_0 = \frac{21 - 0.3(15)}{5} \]
\[ b_0 = \frac{21 - 4.5}{5} \]
\[ b_0 = \frac{16.5}{5} \]
\[ b_0 = 3.3 \]

- So, the regression equation is:
\[ \hat{y} = 3.3 + 0.3x \]
- Using the equation we can calculate \[\hat{y}\]
| Independent (x) | Actual (y) | Predicted (ŷ) |
|-----------------|------------|---------------|
| 1               | 4          | 3.3 + 0.3(1) = 3.6 |
| 2               | 2          | 3.3 + 0.3(2) = 3.9 |
| 3               | 5          | 3.3 + 0.3(3) = 4.2 |
| 4               | 7          | 3.3 + 0.3(4) = 4.5 |
| 5               | 3          | 3.3 + 0.3(5) = 4.8 |

### 3. Residuals (ε)
- Refer to the differences between the observed values of the dependent variable and the corresponding predicted values based on the linear regression model.
- Formula: \( \epsilon = y - \hat{y} \)
- where \( y \) is the observed value and \( \hat{y} \) is the predicted value.
| Residual (e) |
|--------------|
| 0.4          |
| -1.9         |
| 0.8          |
| 2.5          |
| -1.8         |

### 4. Error
- Differences between the observed values of the dependent variable and the true (actual) values.
- Same as residual

### 5. Sum of Squared Errors (SSE)
- Measure used to quantify the difference between the observed values of the target variable and the values predicted by the regression model.
- Calculated by summing the squared differences between each observed value and its corresponding predicted value.
\[ SSE = \sum e_i^2 \]
\[ SSE = (0.4)^2 + (-1.9)^2 + (0.8)^2 + (2.5)^2 + (-1.8)^2 \]
\[ SSE = 0.16 + 3.61 + 0.64 + 6.25 + 3.24 \]
\[ SSE = 13.9 \]

### 6. Total Sum of Squares (SST)
- Represents the total variation in the dependent variable (or target variable) \( y \) from its mean.

\[ \bar{y} = \frac{21}{5} = 4.2 \]
\[ SST = \sum (y_i - \bar{y})^2 \]
\[ SST = (4 - 4.2)^2 + (2 - 4.2)^2 + (5 - 4.2)^2 + (7 - 4.2)^2 + (3 - 4.2)^2 \]
\[ SST = (-0.2)^2 + (-2.2)^2 + (0.8)^2 + (2.8)^2 + (-1.2)^2 \]
\[ SST = 0.04 + 4.84 + 0.64 + 7.84 + 1.44 \]
\[ SST = 14.8 \]



### 7. Mean Squared Error (MSE)
- A common measure used to evaluate the performance of a regression model or predictor.
- Calculates the average of the squares of the errors, or differences, between actual and predicted values in a regression problem.
- A lower MSE indicates that the model's predictions are closer to the actual values, implying better performance.

\[ MSE = \frac{SSE}{n} = \frac{13.9}{5} = 2.78 \]
![Mean Squared Error](MSE.png)

