
## Linear Regression Notes

This repository contains notes summarizing the key points on Linear Regression. These notes serve as a quick reference for understanding the fundamentals of linear regression. 

### Key Points:

1. Linear regression is a statistical method used to model the relationship between a dependent variable and one or more independent variables.

2. The goal of linear regression is to find the best-fitting line that minimizes the differences between the predicted and actual values of the dependent variable.

3. The line in linear regression is represented by the equation: Y = β0 + β1*X1 + β2*X2 + ... + βn*Xn, where Y is the dependent variable, X1, X2, ..., Xn are the independent variables, β0 is the intercept, and β1, β2, ..., βn are the coefficients representing the effect of each independent variable.

4. The coefficients are estimated using ordinary least squares (OLS), which minimizes the sum of squared differences between the predicted and actual values.

5. Linear regression assumes a linear relationship between the independent variables and the dependent variable.

6. Linear regression can handle multiple independent variables, but assumes no multicollinearity among them.

7. It is important to assess assumptions such as linearity, independence of errors, homoscedasticity, and normality of errors.

8. Linear regression can be used for prediction and inference.

9. The coefficient of determination (R-squared) measures how well the model fits the data.

10. Interpretation of coefficients considers their magnitudes and statistical significance.


## Assumptions of Linear Regression

Linear regression relies on certain assumptions to ensure the validity and reliability of the results. Here are the key assumptions to consider when working with linear regression:

1. **Linearity:** Linear regression assumes a linear relationship between the independent variables and the dependent variable. If the relationship is nonlinear, the model may not be appropriate, and alternative regression techniques should be considered.

2. **Independence of errors:** The errors (residuals) should be independent of each other, meaning there should be no systematic patterns or correlations among the residuals. Violations of this assumption can lead to biased or inefficient estimates.

3. **Homoscedasticity:** Homoscedasticity assumes that the variance of the errors is constant across all levels of the independent variables. In other words, the spread of the residuals should be consistent across the range of predicted values. Heteroscedasticity, where the variance of the errors varies, can affect the accuracy of the model's predictions.

4. **Normality of errors:** Linear regression assumes that the errors (residuals) follow a normal distribution. This assumption allows for valid statistical inference, hypothesis testing, and confidence interval estimation. If the errors are not normally distributed, transformations or alternative regression techniques may be necessary.

5. **No multicollinearity:** Multicollinearity occurs when there is a high correlation between independent variables. Linear regression assumes that the independent variables are not perfectly correlated with each other. Multicollinearity can lead to unstable coefficient estimates and difficulty in interpreting the effects of individual variables.

It is crucial to assess these assumptions when working with linear regression. If any of these assumptions are violated, additional diagnostics or modifications to the data or model may be necessary to obtain reliable results.

Please note that this is a summary of the assumptions, and further research and exploration are recommended to gain a deeper understanding of each assumption and how to assess them in practice.

## OLS vs. Gradient Descent in Linear Regression

When it comes to estimating the parameters in linear regression, two commonly used methods are Ordinary Least Squares (OLS) and Gradient Descent. Here's a brief comparison of these methods:

### Ordinary Least Squares (OLS)
- **Method:** OLS is a closed-form solution that analytically calculates the optimal coefficients for linear regression.
- **Objective:** OLS minimizes the sum of squared differences between predicted and actual values.
- **Advantages:**
  - Provides the exact solution for linear regression if assumptions are met.
  - Computationally efficient for small to moderate-sized datasets.
  - Easy to interpret the coefficient estimates.
- **Assumptions:** OLS relies on assumptions like linearity, independence of errors, homoscedasticity, normality of errors, and no multicollinearity among predictors.

### Gradient Descent
- **Method:** Gradient Descent is an iterative optimization algorithm that gradually updates coefficients based on the slope of the error surface.
- **Objective:** Gradient Descent minimizes the cost function by finding the optimal coefficients iteratively.
- **Advantages:**
  - More flexible and applicable to a wider range of regression problems, including cases where OLS is not feasible.
  - Can handle large datasets efficiently.
  - Does not assume any specific distribution of errors.
- **Considerations:**
  - Selection of learning rate and convergence criteria can impact performance.
  - May require more computational resources for complex models or high-dimensional data.
  - Interpretation of coefficient estimates can be more challenging.

### Choosing the Method:
- **OLS:** OLS is often preferred when the assumptions of linear regression are met, the dataset is small to moderate-sized, and interpretability is crucial.
- **Gradient Descent:** Gradient Descent is suitable for cases where OLS assumptions are violated, large datasets are involved, or more flexible regression models are required.

Understanding the differences between OLS and Gradient Descent helps in selecting the appropriate method based on the specific requirements and characteristics of the regression problem at hand.



## Gradient Descent Steps

Gradient Descent is an iterative optimization algorithm commonly used to find the minimum of a function. Here's a general outline of the steps involved in the Gradient Descent algorithm for parameter estimation:

1. **Initialize Parameters:** Start by initializing the coefficients (parameters) of the model with some initial values.

2. **Calculate Predictions:** Use the current parameter values to make predictions on the training data.

3. **Calculate Cost:** Calculate the cost function, which measures the discrepancy between the predicted and actual values. Commonly used cost functions include Mean Squared Error (MSE) or Mean Absolute Error (MAE).

4. **Calculate Gradients:** Calculate the gradients of the cost function with respect to each parameter. The gradients indicate the direction and magnitude of the steepest ascent or descent.

5. **Update Parameters:** Update the parameter values by taking a step in the opposite direction of the gradients. The size of the step is determined by the learning rate, which controls the convergence speed.

6. **Repeat Steps 2-5:** Repeat steps 2 to 5 until a stopping criterion is met. This criterion can be a maximum number of iterations, reaching a desired level of accuracy, or observing minimal improvement in the cost function.

7. **Obtain Final Parameters:** Once the stopping criterion is satisfied, the algorithm stops, and the final parameter values are obtained.

Gradient Descent iteratively adjusts the parameter values in the direction of steepest descent to minimize the cost function. This process continues until convergence is achieved or the stopping criterion is met.

It's important to note that there are variations of Gradient Descent, such as Batch Gradient Descent, Stochastic Gradient Descent, and Mini-batch Gradient Descent, which differ in how they update the parameters and use the training data.


## Cost Functions in Regression

Cost functions in regression measure the discrepancy between the predicted values and the actual values of the dependent variable. These functions play a crucial role in optimization algorithms, such as Ordinary Least Squares (OLS) or Gradient Descent, which aim to minimize the cost to obtain the optimal parameter estimates. Here are some commonly used cost functions in regression:

1. **Mean Squared Error (MSE):** MSE is one of the most widely used cost functions in regression. It calculates the average of the squared differences between the predicted and actual values. MSE penalizes larger errors more than smaller errors due to the squared term.

2. **Mean Absolute Error (MAE):** MAE is another popular cost function that calculates the average of the absolute differences between the predicted and actual values. Unlike MSE, MAE treats all errors equally without squaring them.

3. **Root Mean Squared Error (RMSE):** RMSE is the square root of MSE. It is often used to express the error in the same unit as the dependent variable, making it easier to interpret.

4. **Mean Absolute Percentage Error (MAPE):** MAPE calculates the average percentage difference between the predicted and actual values. It is commonly used when the scale of the dependent variable varies widely and you want to express the error as a percentage.

5. **Huber Loss:** Huber Loss is a combination of MSE and MAE. It behaves like MSE for smaller errors and like MAE for larger errors. Huber Loss offers a balance between robustness to outliers (like MAE) and sensitivity to smaller errors (like MSE).

These cost functions provide a quantitative measure of how well the model fits the data. The choice of the cost function depends on the specific problem, the nature of the data, and the desired characteristics of the model.



