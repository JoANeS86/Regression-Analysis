## Module 1: Introduction to complex data relationships

<ins>Regression analysis or Regression models</ins>: A group of statistical techniques that use existing data to estimate the relationships between
a single dependent variable and one or more independent variables.

<ins>Model assumptions</ins>: Statements about the data that must be true to justify the use of particular data science techniques.

<ins>Linear regression</ins>: A technique that estimates the linear relationship between a continuos dependent variable Y and one or more independent variables X
(i.e., linear regression is a way to model linear relationships).

    Dependent variable (Y): The variable a given model estimates, also referred to as a response or outcome variable.
    Independent variable (X): A variable that explains trends in the dependent variable, also referred to as an explanatory
    or predictor variable.

    Y = slope * X + intercept

    Slope: The amount that Y increases or decreases per one-unit increase of X.

    Intercept: The value of Y, the dependent variable, when X, the independent variable, equals 0.

Correlation is not Causation: Causation describes a cause-and-effect relationship where one variable directly causes the other to change in a
particular
way.

    E.g., although we can say that as someone gets older, the number of places they have visited tends to rise,
    we cannot necessarily say that someone's age causes the number of places they had visited to increase.

Linear regression analysis focuses on the mean of Y given a particular value of X:

<p align="center">
  <img src="https://github.com/user-attachments/assets/db72cf7a-61f3-42bf-89e0-be3f1f6a03e5" />
</p>

To calculate the regression coefficients, we use the Ordinary Least Squares Estimation (OLS).

In linear regression analysis, we as data professionals, are trying to minimize something called a Loss Function. The Loss Function is a function
that measures the distance between the observed values and the models estimated values.

## Module 2: Simple Linear Regression

<ins>Best fit line</ins>: The line that fits the data best by minimizing some loss function or error.

<ins>Predicted values</ins>: The estimated Y values for each X calculated by a model.

<ins>Residual</ins>: The difference between observed or actual values and the predicted values of the regression line.

        The sum of the residuals is always equal to 0 for OLS estimators.

<ins>Sum of Squared Residuals (SSR)</ins>: The sum of the squared differences between each observed value and its associated predicted value.

<p align="center">
  <img src="https://github.com/user-attachments/assets/69232158-35f2-4883-969d-0355ea8c146e" />
</p>

<ins>Ordinary Least Squares (OLS)</ins>: A method that minimizes the sum of squared residuals to estimate parameters in a linear regression model.

When two variables are summarized together, there is another relevant statistic called **r**, **Pearson’s correlation coefficient** (named after the person
who helped develop it), or simply the **linear correlation coefficient**. The correlation coefficient quantifies the strength of the linear relationship
between two variables. It always falls in the range of [-1, 1].

<p align="center">
  <img src="https://github.com/user-attachments/assets/ff562c12-09ea-46a8-b65a-56291e3d950b" />
</p>

An easier way of thinking about this calculation is: the numerator—the covariance—represents the extent to which X and Y vary together from their respective means. When this value is positive, it suggests that high values of X tend to be associated with high values of Y, indicating a positive correlation. Conversely, if the value is negative, it suggests that high values of X tend to be associated with low values of Y and vice versa, indicating a negative correlation. 

The denominator—the product of the standard deviations—standardizes the units of the numerator. It adjusts for the inherent variability of the individual variables. This makes r a statistic without a unit. It is a pure number, without dimension.

The slope of the regression line is:

<p align="center">
  <img src="https://github.com/user-attachments/assets/ab6adb4f-bc2f-45e0-9e51-a86b59c066cb" />
</p>

There, the ratio SDy/SDx adjusts that relationship into the proper scale of “change in Y per change in X.

**Simple linear regression assumptions**

To recap, there are four assumptions of simple linear regression:

        Linearity: Each predictor variable (Xi) is linearly related to the outcome variable (Y).
        Normality: The errors are normally distributed.*
        Independent Observations: Each observation in the dataset is independent.
        Homoscedasticity: The variance of the errors is constant or similar across the model.*

*Note on errors and residuals

This course has rather interchangeably used the terms "errors" and "residuals" in connection with regression. You may see this in other online resources and materials throughout your time as a data professional. In actuality, there is a difference:

        Residuals are the difference between the predicted and observed values. You can calculate
        residuals after you build a regression model by subtracting the predicted values from the observed values.

        Errors are the natural noise assumed to be in the model.

Residuals are used to estimate errors when checking the normality and homoscedasticity assumptions of linear regression.

To use Ordinary Least Squares estimation we use the following code in Python:

        from statsmodels.formula.api import ols

And we'll probably need the following too:

        import statsmodels.api as sm

**Interpret measures of uncertainty in regression**

We can then quantify how uncertain the entire model is through a few measures of uncertainty:

        Confidence intervals around beta coefficients
        P-values for the beta coefficients
        Confidence band around the regression line

Summary of results (Example):

<p align="center">
  <img src="https://github.com/user-attachments/assets/eba11aac-9b5f-4d12-a478-343dc7539aae" />
</p>

<ins>P-values</ins>

When running regression analysis, you want to know if X is really correlated with y or not. So we do a hypothesis test on the regression results. In regression analysis, for each beta coefficient, we are testing the following set of null and alternative hypotheses:

    - H0 (null hypothesis): B1 = 0
    - H1 (alternative hypothesis): B1 != 0

In our example, because the p-value is less than 0.05, we can reject the null hypothesis that B1 is equal to 0, and state that the coefficient is statistically significant, which means that a difference in bill length of a penguin is truly correlated with a difference in body mass.

<ins>Confidence Intervals</ins>

Each beta coefficient also has a confidence interval associated with its estimate. A 95% interval means the interval itself has a 95% chance of containing the true parameter value of the coefficient. So there is 5% chance that our confidence interval [131.788, 150.592] does not contain the true value of B1. More precisely, this means that if you were to repeat this experiment many times, 95% of the confidence intervals would contain the true value of B1.

But, since there is uncertainty in both of the estimated beta coefficients, then the estimated y values also have uncertainty. This is where confidence bands become useful.

<ins>Confidence band</ins>: The area surrounding the line that describes the uncertainty around the predicted outcome. You can think of the confidence band as representing the confidence interval surrounding each point estimate of y. Since there is uncertainty at every point in the line, we use the confidence band to summarize the confidence intervals across the regression model. The confidence band is always narrowest towards the mean of the sample and widest at the extremities.

**Evaluation metrics for simple linear regression**

<ins>R²: The coefficient of determination</ins>

R² measures the proportion of variation in the dependent variable, Y, explained by the independent variable(s), X.

        R² = 1 - Sum of squared residuals/Total sum of squares

R² ranges from 0 to 1. So, if a model has an R² of 0.85, that means that the X variables explain about 85% of the variation in the Y variable.

<ins>MSE (mean squared error)</ins>: Is the average of the squared difference between the predicted and actual values.

<ins>MAE (mean absolute error)</ins>: Is the average of the absolute difference between the predicted and actual values.

Adjusted R²





Logistic regression: A technique that models a categorical dependent variable based on one or more independent variables.



## Module 3: Multiple Regression

Multiple linear regression, also known as multiple regression, is a technique that estimates the linear relationship between one continuous dependent
variable and two or more independent variables

One Hot Encoding: A data transformation technique that turns one categorical variable into several binary variables.

Variance Inflation Factors (VIF): Quantifies how correlated each independent variable is with all of the other independent variables.



    





