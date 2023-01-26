# Linear Regression

## Simple Linear Regression

Linear regression is a supervised learning model which is used to find th linear relationship between given set of input and output data points, then based on the relationship identified it predicts the output for new data.

Linear regression in its simple form is defined as

``` y = b0 + b1x ```

Where:

y is the dependent variable (outcome)
x is the independent variable (predictor)
b1 is the slope of the line, which represents the relationship between x and y
b0 is the y-intercept, which represents the point at which the line crosses the y-axis

## Multiple Linear Regression

The above equation represents a simple linear regression model, which has one independent variable, but linear regression can also be used to model relationships with multiple independent variables using the equation:

``` y = b0 + b1x1 + b2x2 + ... + bnxn ```

Where:

- y is the dependent variable
- x1, x2, ..., xn are the independent variables
- b0, b1, b2, ..., bn are the coefficients of the independent variables, also known as beta coefficients.

The goal here is to create a line that best fits/represents the given data points and predicts new data with greater accuracy.

## Ridge & Lasso Regression
As the number of coefficients grow, it is possible that the model creates the regression line that tends to be very similary the data points rather than than being a generlized one that can approximate the points better overall, this is overfitting.
We do not want to overfit our model because the prediction for new unseen data will be poor.

To tackle this, we can use L1 and L2 regularization called Lasso and Ridge regression, they both attempt to do the same thing: penalize by reducing the coefficients if they start to overfit the model

Lasso regression forumla:

``` (1/N) * ∑ (y_i - (b0 + b1x1 + b2x2 + ... + bn*xn))^2 + alpha * (b1^2 + b2^2 + ... + bn^2) ```

Ridge regression formula:

``` (1/N) * ∑ (y_i - (b0 + b1x1 + b2x2 + ... + bn*xn))^2 + alpha * (|b1| + |b2| + ... + |bn|) ```

Where:

- N is the number of observations
- y_i is the outcome variable
- x1, x2, ..., xn are the independent variables
- b0, b1, b2, ..., bn are the coefficients of the independent variables
- alpha is the regularization strength

## Cost function

The goal of linear regression is to find the values of the coeffcients that minimze the cost function (predicts with least error).

The cost function is used to determine the difference between the predicted and actual values. It calculates the Mean squared error (MSE) which approximates the error in prediction, by finding the model with the lowest MSE/cost function, we can get the best model.

``` Cost function / MSE (y, ŷ) = (1/N) * ∑ (y_i - ŷ_i)^2 ```

Where:

- y is the vector of actual values
- ŷ is the vector of predicted values
- y_i is the i-th actual value
- ŷ_i is the i-th predicted value
- N is the number of observations

## Gradient Descent

Gradient descent is used to optimize the cost function by getting to the lowest value, it starts with a value and iteratively keeps updating the parameters so that the cost function reaches minimum or maximum iterations is reached.

It is derived by the formula

![Gradient Descent formula](https://github.com/RanganMahesh/Machine-Learning/blob/main/Linear%20Regression/Gradient%20Descent%20forumla.png)

Where:

- theta j is the current value of cost function
- alpha is the learning rate
- m is the number of observations
- h theta(x_i) is the predicted value
- y_i is the actual observation value
- x_i is the data point
