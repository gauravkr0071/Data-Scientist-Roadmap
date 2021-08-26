# __Linear Regression__

### [Assumptions ](https://www.analyticsvidhya.com/blog/2016/07/deeper-regression-analysis-assumptions-plots-solutions/)

Regression is a parametric approach. ‘Parametric’ means it makes assumptions about data for the purpose of analysis. Due to its parametric side, regression is restrictive in nature. It fails to deliver good results with data sets which doesn’t fulfill its assumptions. Therefore, for a successful regression analysis, it’s essential to validate these assumptions.

- __Linearity :__ There should be a __linear and additive relationship__ between dependent (response) variable and independent (predictor) variable(s). A linear relationship suggests that a change in response Y due to one unit change in X¹ is constant, regardless of the value of X¹. An additive relationship suggests that the effect of X¹ on Y is independent of other variables.
- There should be no correlation between the residual (error) terms. Absence of this phenomenon is known as Autocorrelation.
- The error terms must have constant variance. This phenomenon is known as homoscedasticity. The presence of non-constant variance is referred to heteroscedasticity. 
- The error terms must be normally distributed.

### __What if these assumptions get violated ?__

Let’s dive into specific assumptions and learn about their outcomes (if violated):

- __Linear and Additive__:  If you fit a linear model to a non-linear, non-additive data set, the regression algorithm would fail to capture the trend mathematically, thus resulting in an inefficient model. Also, this will result in erroneous predictions on an unseen data set.

How to check: Look for residual vs fitted value plots (explained below). Also, you can include polynomial terms (X, X², X³) in your model to capture the non-linear effect.

 

- __Autocorrelation__: The presence of correlation in error terms drastically reduces model’s accuracy. This usually occurs in time series models where the next instant is dependent on previous instant. If the error terms are correlated, the estimated standard errors tend to underestimate the true standard error.

If this happens, it causes confidence intervals and prediction intervals to be narrower. Narrower confidence interval means that a 95% confidence interval would have lesser probability than 0.95 that it would contain the actual value of coefficients. Let’s understand narrow prediction intervals with an example:

For example, the least square coefficient of X¹ is 15.02 and its standard error is 2.08 (without autocorrelation). But in presence of autocorrelation, the standard error reduces to 1.20. As a result, the prediction interval narrows down to (13.82, 16.22) from (12.94, 17.10).

Also, lower standard errors would cause the associated p-values to be lower than actual. This will make us incorrectly conclude a parameter to be statistically significant.

How to check: Look for [Durbin – Watson (DW)](https://www.investopedia.com/terms/d/durbin-watson-statistic.asp) statistic. It must lie between 0 and 4. If DW = 2, implies no autocorrelation, 0 < DW < 2 implies positive autocorrelation while 2 < DW < 4 indicates negative autocorrelation. Also, you can see residual vs time plot and look for the seasonal or correlated pattern in residual values.

 

- __Multicollinearity__: This phenomenon exists when the independent variables are found to be moderately or highly correlated. In a model with correlated variables, it becomes a tough task to figure out the true relationship of a predictors with response variable. In other words, it becomes difficult to find out which variable is actually contributing to predict the response variable.

Another point, with presence of correlated predictors, the standard errors tend to increase. And, with large standard errors, the confidence interval becomes wider leading to less precise estimates of slope parameters.

Also, when predictors are correlated, the estimated regression coefficient of a correlated variable depends on which other predictors are available in the model. If this happens, you’ll end up with an incorrect conclusion that a variable strongly / weakly affects target variable. Since, even if you drop one correlated variable from the model, its estimated regression coefficients would change. That’s not good!

How to check: You can use scatter plot to visualize correlation effect among variables. Also, you can also use __[VIF factor](https://www.analyticsvidhya.com/blog/2020/03/what-is-multicollinearity/)__. VIF value <= 4 suggests no multicollinearity whereas a value of >= 10 implies serious multicollinearity. Above all, a correlation table should also solve the purpose.

 

- __Heteroskedasticity__: The presence of non-constant variance in the error terms results in heteroskedasticity. Generally, non-constant variance arises in presence of outliers or extreme leverage values. Look like, these values get too much weight, thereby disproportionately influences the model’s performance. When this phenomenon occurs, the confidence interval for out of sample prediction tends to be unrealistically wide or narrow.

How to check: You can look at residual vs fitted values plot. If heteroskedasticity exists, the plot would exhibit a funnel shape pattern (shown in next section). Also, you can use Breusch-Pagan / Cook – Weisberg test or White general test to detect this phenomenon.

 

- __Normal Distribution of error terms__: If the error terms are non- normally distributed, confidence intervals may become too wide or narrow. Once confidence interval becomes unstable, it leads to difficulty in estimating coefficients based on minimization of least squares. Presence of non – normal distribution suggests that there are a few unusual data points which must be studied closely to make a better model.

How to check: You can look at __[QQ plot](https://www.google.com/search?q=whta+is+quantile+in+qq+plot&oq=whta+is+quantile+in+qq+plot&aqs=chrome..69i57j0i22i30j0i390l2.9049j0j7&sourceid=chrome&ie=UTF-8#kpvalbx=_yHwnYfzwHsiY4-EPzoKMOA14)__ (shown below). You can also perform statistical tests of normality such as Kolmogorov-Smirnov test, Shapiro-Wilk test.

- __Residual vs Fitted Values__

![image](https://user-images.githubusercontent.com/51910127/130816806-3415a592-58c8-4fbb-bb26-883de9966a36.png)
![image](https://user-images.githubusercontent.com/51910127/130816857-72911a70-9d81-4f68-acc6-3f876efd4172.png)

This scatter plot shows the distribution of residuals (errors) vs fitted values (predicted values). It is one of the most important plot which everyone must learn. It reveals various useful insights including outliers. The outliers in this plot are labeled by their observation number which make them easy to detect.

There are two major things which you should learn:

If there exist any pattern (may be, a parabolic shape) in this plot, consider it as signs of non-linearity in the data. It means that the model doesn’t capture non-linear effects.
If a funnel shape is evident in the plot, consider it as the signs of non constant variance i.e. heteroskedasticity.

Solution: To overcome the issue of non-linearity, you can do a non linear transformation of predictors such as log (X), √X or X² transform the dependent variable. To overcome heteroskedasticity, a possible way is to transform the response variable such as log(Y) or √Y. Also, you can use weighted least square method to tackle heteroskedasticity.

- __Residual vs Fitted Values__
![image](https://user-images.githubusercontent.com/51910127/130817979-941a0e3f-8bb3-4029-89a7-40c8d506838e.png)

This q-q or quantile-quantile is a scatter plot which helps us validate the assumption of normal distribution in a data set. Using this plot we can infer if the data comes from a normal distribution. If yes, the plot would show fairly straight line. Absence of normality in the errors can be seen with deviation in the straight line.

If you are wondering what is a ‘quantile’, here’s a simple definition: Think of quantiles as points in your data below which a certain proportion of data falls. Quantile is often referred to as percentiles. For example: when we say the value of 50th percentile is 120, it means half of the data lies below 120.

Solution: If the errors are not normally distributed, non – linear transformation of the variables (response or predictors) can bring improvement in the model.

- __Scale Location Plot__

![image](https://user-images.githubusercontent.com/51910127/130818254-8f3fa39a-407f-4517-ae70-c6a719fc163b.png)

This plot is also used to detect homoskedasticity (assumption of equal variance). It shows how the residual are spread along the range of predictors. It’s similar to residual vs fitted value plot except it uses standardized residual values. Ideally, there should be no discernible pattern in the plot. This would imply that errors are normally distributed. But, in case, if the plot shows any discernible pattern (probably a funnel shape), it would imply non-normal distribution of errors.

Solution: Follow the solution for heteroskedasticity given in plot 1.

- __Residuals vs Leverage Plot__
![image](https://user-images.githubusercontent.com/51910127/130818402-2f6b456b-fa39-47d8-8711-2ec034f98478.png)

It is also known as Cook’s Distance plot. Cook’s distance attempts to identify the points which have more influence than other points. Such influential points tends to have a sizable impact of the regression line. In other words, adding or removing such points from the model can completely change the model statistics.

But, can these influential observations be treated as outliers? This question can only be answered after looking at the data. Therefore, in this plot, the large values marked by cook’s distance might require further investigation.

Solution: For influential observations which are nothing but outliers, if not many, you can remove those rows. Alternatively, you can scale down the outlier observation with maximum value in data or else treat those values as missing values.

### __Types of Linear Regression__

- __Simple Linear Regression__ 
Simple linear regression establishes a linear relationship between one input and one output variable, along with a constant co-efficient.
![image](https://user-images.githubusercontent.com/51910127/130856902-904a989e-6f4c-46ae-b33e-7d02d179e3ec.png)

- __Multiple Linear Regression__
When multiple input variables are linearly combined to get the value of outcome, it is called multiple linear regression.
![image](https://user-images.githubusercontent.com/51910127/130856956-6c80fcf1-6697-4b3a-8812-564d24a921ab.png)

In the above equations,
- y = the target variable.
- x = the input variable.(x1,x2,…xn in case of multiple regression)
- b0 = the intercept value.
- b1, b2,.. bn = Coefficients describing the linear relationship between a combination of the input variables and target variable.
- __Effect of b0 on x-y relationship:__
The value of b0 defines the expected mean of target (y) when input (x) is 0. If we assign b0 to be 0, then we’re forcibly trying to pass the regression line through the origin, where both x and y are 0 and 0. This may be helpful in some cases, while reducing accuracy in others. Thus, it’s important to experiment with the values of b0, as per the needs of the dataset you’re working with.
- __Effect of b1 on x-y relationship:__
If b1 is greater than zero, then the input variable has a positive impact on the target. The increase in one would lead to an increase in the value of the other. Whereas, if b1 is less than zero, the input and output variables will have an inversely proportional or negative relationship. Thus, an increase in one would lead to a decrease in the value of the other.

- ### __Feature Scaling__
Feature scaling refers to normalizing data to converge within a certain range. The process modifies data values to better fit a given model. Two of the most widely used scaling methods are:
- __Log transform__ 
Log transformation is used when the values of an attribute span a very large interval. __[Log transformation](https://kenbenoit.net/assets/courses/ME104/logmodels2.pdf)__ makes data more easily comparable and interpretable, and also help avoid overflows.
![image](https://user-images.githubusercontent.com/51910127/130857661-d75c2f81-f7b8-41ac-8364-b8b7fe11c645.png)
- __Min-max scaling/normalization__
Min-max normalization scales the data between 0 and 1. The formula used is:
![image](https://user-images.githubusercontent.com/51910127/130857772-e79dfcea-b33d-49ca-8d70-83426b12adb6.png)

### __Mathematical Equation : Ordinary Least Squares__
![image](https://user-images.githubusercontent.com/51910127/130860931-6fc663df-6051-4d00-a8ac-b87846df0062.png)
![image](https://user-images.githubusercontent.com/51910127/130861001-26950a63-1798-45bc-b891-75dfa1d1b4c8.png)
![image](https://user-images.githubusercontent.com/51910127/130861076-d3ffc807-c938-4a0d-b24c-1e7153c1c242.png)
![image](https://user-images.githubusercontent.com/51910127/130861122-fe2b6e62-6f32-4db1-bcb7-bd1e195c9002.png)

![image](https://user-images.githubusercontent.com/51910127/130861796-ea12fcf7-a6bc-42d7-8be5-8bab44899578.png)

### __[Performance Metrics](https://www.analyticsvidhya.com/blog/2017/06/a-comprehensive-guide-for-linear-ridge-and-lasso-regression/)__
- __R-Square__: It determines how much of the total variation in Y (dependent variable) is explained by the variation in X (independent variable). Mathematically, it can be written as:
![image](https://user-images.githubusercontent.com/51910127/130868289-e5ccd7fd-5c8b-4b4e-bddd-b17f9cd80180.png)
- __Adjusted R-square__: The only drawback of R2 is that if new predictors (X) are added to our model, R2 only increases or remains constant but it never decreases. We can not judge that by increasing complexity of our model, are we making it more accurate? \

That is why, we use “Adjusted R-Square”. \

The Adjusted R-Square is the modified form of R-Square that has been adjusted for the number of predictors in the model. It incorporates model’s degree of freedom. The adjusted R-Square only increases if the new term improves the model accuracy. \

![image](https://user-images.githubusercontent.com/51910127/130868516-dfd07ff4-ab2b-405b-8508-f37bcad5b413.png)

