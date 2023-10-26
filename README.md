# Simple_Linear_Regression_Project
This is a small simple linear regression model project for academic purpose in which we model the linear relationship between altitude and coffee quality.

# Introduction

What makes a good cup of coffee? In this project, we seek to figure out if where and at what altitude makes a difference to the coffee bean quality.

# Project description: 

In order to find the relationship between altitude and coffee quality, we will be using the Simple Linear Regression (SLR) model. Having altitude as the explanatory variable and total cupping points be the indicator of quality as well as the response variable, our goals are:
1) to estimate the association between altitude and total cupping points, and
2) to predict the response for a given value of the total cupping points.
    
H0: There is no relationship between altitude and coffee quality (total cup points) \
H1: there is a relationship between altitude and coffee quality (total cup points)

# Dataset

The dataset we will be using is collected from the Coffee Quality Institute's review pages in January 2018 of reviews of 1062 Arabica coffee beans by James LeDoux. 

Jame LeDoux's GitHub repository: <https://github.com/rfordatascience/tidytuesday/blob/master/data/2020/2020-07-07/readme.md>

# Packages
For this project, we are using the following packages to be used in R.

* tidytuesdayR
* tidyverse
* base R

# Methods

**Linear Regression**

Linear Regression is a statistical technique which is used to find the linear relationship between one dependent and one or more independent variables. We will be using the Single Linear Regression model.

Our model will take the form of Y = 𝛽0 + 𝛽1x 

𝛽0 is the y-intercept which will tell us the estimated average Total Cupping Points for coffee beans with an altitude of 0. \
𝛽1 is the slope which will tell us the average difference in Total Cupping Points for coffee beans whose altitude differs by one meter. \
x being Altitude is the independent variable. \
Y being our Total Cupping Points, and our dependent variable, is an estimate of the mean value of the Total Cupping Points for any value of altitude.

The equation of the fitted regression line is:
Y = 80.8382 + 0.001Altitude
<br>
<br>

# Conditions

Linear regression relies on certain assumptions:

* Linearity
* Independence of errors
* Normality of errors
* Equal variances
<br>
A good way to check conditions is to use some visualizations. Below is a scatterplot of the relationship between coffee quality and altitude. We can see that the points form a slight positive linear relationship and that variance is the same across all values of the x-axis, which prove the assumptions of Linearity and Equal Variance.
<br>

![image](https://github.com/njeanette03/Simple_Linear_Regression_Project/assets/67883452/5c56cef6-ef42-42d6-a125-229c9f6546c4)


To check the independence of errors, we can look at the scatterplot below of the Residuals vs Fitted values. The correlation is approximately 0 and therefore is independent of errors and we can assume there is no relationship between the residuals and the variable, with total cupping points as the response and altitude as the predictor.

![image](https://github.com/njeanette03/Simple_Linear_Regression_Project/assets/67883452/40a6259a-f36e-43b8-995a-30a33a1d545c)


Lastly, to check the normality, we can look at the histogram of the residuals below. It is bell shaped which indicates normality.

![image](https://github.com/njeanette03/Simple_Linear_Regression_Project/assets/67883452/7127f074-3f54-4791-b1c4-0c0563a6c798)


All conditions are met. We can proceed to interpret the regression output and draw inferences regarding our model estimates.
<br>
<br>

**Making Predictions**

Using the predict(), I predicted what the total cupping points would be if the coffee beans were grown at an altitude of 1000, 2000, and 5000.

At an altitude of 1000 meters, the predicted score is 81.84609 total cupping points out of 100.
At an altitude of 1000 meters, the predicted score is 82.85393  total cupping points out of 100.
At an altitude of 1000 meters, the predicted score is 85.87746  total cupping points out of 100.

<br>

**Confidence Interval**

A confidence interval measures the degree or uncertainty or certainty.

Using the confint() to find our confidence interval, we are 95% confident that for every 1 meter in altitude, the total cupping points increase between 0.0006566442 to 0.00135904.


# Interpretation of P-value and Conclusion

Calculating the p-value, we get 2.293869e-08 or 0.00000002293869. Assuming α = 0.05, our p-value is much smaller than our 0.05 level of significance so this tells us to reject our null hypothesis and that our independent variable of altitude has a significant relationship with our dependent variable of cupping points. This also means that our interpretation of our slope was correct and we can conclude that there is a relationship between coffee quality (Total Cup Points) and altitude. Therefore, the higher the altitude of the coffee, the better the quality. So next time you’re stuck between grabbing two bags of coffee beans, you can choose the one with higher elevation (altitude), to statistically give you a better cup of joe.

# Considerations
For this project, we used only Arabica beans as there were not large enough of a sample size for Robusta beans. However, Robusta beans tend to grow on a lower elevation compared to Arabica and I believe a future dataset which includes it would be a more accurate representation between coffee quality and altitude. As linear regressions are sensitive to outliers, we removed any outliers, such as no ratings or extreme altitudes that are poor sampling.
