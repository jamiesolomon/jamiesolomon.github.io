---
layout: post
title:  "Baseball Modeling: A Comparison of Regression Techniques"
date:   2022-11-01
desc: "Overview of project with a link to the GitHub repository"
keywords: "baseball, regression, modeling"
categories: [Data Science]
tags: [regression, modeling, machine learning]
icon: icon-baseball
---

[Baseball Modeling (Code)](https://github.com/jamiesolomon/Baseball_Modeling) <br>
[Full Report](/images/FullReport.pdf)

This report iterates through various regression models in predicting the outcome of an MLB season. The dataset used in this project contains batting statistics from Major League Baseball teams from 1951 to 2021.

### Data Preprocessing

Before training the models, the data was preprocessed to remove any rows with missing values and to normalize the data. The target variable, runs scored, was also log-transformed to improve the linearity of the data.

### Linear Regression

A simple linear regression model was trained on the preprocessed data, achieving an R-squared score of 0.31 on the test data.

### Polynomial Regression

Polynomial regression was used to fit a quadratic model to the data. The degree of the polynomial was chosen using 10-fold cross-validation, resulting in a degree of 2. The model achieved an R-squared score of 0.43 on the test data.

### Ridge Regularization

A polynomial regression model with ridge regularization was trained on the preprocessed data. The regularization parameter, alpha, was chosen using 10-fold cross-validation and was found to be 0.01. The model achieved an R-squared score of 0.43 on the test data.


### Random Forest Regression

A random forest regression model was trained on the preprocessed data using 500 trees. The model achieved an R-squared score of 0.47 on the test data.


### Conclusion

The random forest regression model performed the best in predicting runs scored in a baseball game, achieving an R-squared score of 0.47 on the test data. However, all the models except for the simple linear regression model achieved similar performance, with R-squared scores ranging from 0.43 to 0.47.

Overall, this report shows that a variety of regression techniques can be used to predict runs scored in a baseball game, and that the choice of technique may depend on the specific problem and data at hand.
