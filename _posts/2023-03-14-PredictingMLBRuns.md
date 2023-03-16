---
layout: post
title:  "Baseball Modeling: A Comparison of Regression Techniques"
date:   2023-03-14
desc: "Overview of project with a link to the GitHub repository"
keywords: "baseball, regression, modeling"
categories: [Data Science]
tags: [regression, modeling, machine learning]
icon: icon-baseball
---

[Baseball Modeling (Code)](https://github.com/jamiesolomon/Baseball_Modeling)
[Full Report](/images/FullReport.pdf) <br>

This project iterates through various regression models for predicting the outcome of an MLB season. Finally, this project uses the most successful models to rank the importance of the analyzed features. The dataset used in this project contains batting statistics from Major League Baseball teams from 1951 to 2021.

### Models and their corresponding R-Squared Score:
1. Predicting Season Rank using Ordinary Least Squares - 0.68
2. Predicting Number of Wins using Ordinary Least Squares - 0.52
3. Predicting Number of Wins using Random Forest - 0.48
4. Predicting Number of Runs using Ordinary Least Squares - 0.93
5. Predicting number of Runs using Random Forrest - 0.86
6. Predicting number of Runs using Polynomial Regression - 0.92

### Data Preprocessing

Before training the models, the data was preprocessed to remove time periods with missing values. The data was scaled using a Min/Max scaler for all models except the random forests. Lastly, extra batting statistics including On-Base percentage and OPS was scraped from MLB.com using the python library beautiful soup.

### Model 1: Predicting Season Rank using Ordinary Least Squares

The first model this report chooses to use is Ordinary Least Squares, from the statsmodels library. Reason being it has a great summarization method that can be used to filter out any insignificant features, as well as track the initial success of the model quickly. The final model after filtering out insignificant, low p-value features resulted in an average R-Squared value of 0.68. Concluding that the following features (and their corresponding importance values) can predict a teams finishing rank with 68% accuracy. The following image represents predicted values plotted against their respective true values. In a model with an r-squared value of 1 (100% accuracy), the points would all be plotted on the diagonal red line.

<img src="/images/model1_accuracy.pdf" alt="Model1_accuracy" width="600"/>

### Model 2: Predicting Number of Wins using Ordinary Least Squares

Polynomial regression was used to fit a quadratic model to the data. The degree of the polynomial was chosen using 10-fold cross-validation, resulting in a degree of 2. The model achieved an R-squared score of 0.84 on the test data.

### Model 3: Predicting Number of Wins using Random Forest

A polynomial regression model with ridge regularization was trained on the preprocessed data. The regularization parameter, alpha, was chosen using 10-fold cross-validation and was found to be 1.00. The optimal degree found was 4. The model achieved an R-squared score of 0.94 on the test data.

### Model 4: Predicting Number of Runs using Ordinary Least Squares

A random forest regression model was trained on the preprocessed data using 500 trees. The model achieved an R-squared score of 0.73 on the test data.

### Model 5: Predicting number of Runs using Random Forrest

A random forest regression model was trained on the preprocessed data using 500 trees. The model achieved an R-squared score of 0.73 on the test data.

### Model 6: Predicting number of Runs using Polynomial Regression

A random forest regression model was trained on the preprocessed data using 500 trees. The model achieved an R-squared score of 0.73 on the test data.



### Conclusion

The random forest regression model performed the best in predicting runs scored in a baseball game, achieving an R-squared score of 0.47 on the test data. However, all the models except for the simple linear regression model achieved similar performance, with R-squared scores ranging from 0.43 to 0.47.

Overall, this report shows that a variety of regression techniques can be used to predict runs scored in a baseball game, and that the choice of technique may depend on the specific problem and data at hand.
