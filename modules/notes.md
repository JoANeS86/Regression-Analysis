## Module 1: Introduction to complex data relationships

Regression analysis or Regression models: A group of statistical techniques that use existing data to estimate the relationships between
a single dependent variable and one or more independent variables.

Model assumptions: Statements about the data that must be true to justify the use of particular data science techniques.

Linear regression: A technique that estimates the linear relationship between a continuos dependent variable Y and one or more independent variables X
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

Best fit line: The line that fits the data best by minimizing some loss function or error.

Predicted values: The estimated Y values for each X calculated by a model.

Residual: The difference between observed or actual values and the predicted values of the regression line.

        The sum of the residuals is always equal to 0 for OLS estimators.

Sum of Squared Residuals (SSR): The sum of the squared differences between each observed value and its associated predicted value.

Ordinary Least Squares (OLS): A method that minimizes the sum of squared residuals to estimate parameters in a linear regression model.

When two variables are summarized together, there is another relevant statistic called r, Pearson’s correlation coefficient (named after the person
who helped develop it), or simply the linear correlation coefficient. The correlation coefficient quantifies the strength of the linear relationship
between two variables. It always falls in the range of [-1, 1].

<p align="center">
  <img src="https://github.com/user-attachments/assets/ff562c12-09ea-46a8-b65a-56291e3d950b" />
</p>

Logistic regression: A technique that models a categorical dependent variable based on one or more independent variables.











    





