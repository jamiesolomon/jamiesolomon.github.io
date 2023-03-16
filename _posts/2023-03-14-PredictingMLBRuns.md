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

<br>

### Data Preprocessing

Before training the models, the data was preprocessed to remove time periods with missing values. The data was scaled using a Min/Max scaler for all models except the random forests. Lastly, extra batting statistics including On-Base percentage and OPS was scraped from MLB.com using the python library beautiful soup.

<br>

### Model 1: Predicting Season Rank using Ordinary Least Squares

The first model this report chooses to use is Ordinary Least Squares, from the statsmodels library. Reason being it has a great summarization method that can be used to filter out any insignificant features, as well as track the initial success of the model quickly. The final model after filtering out insignificant, low p-value features resulted in an average R-Squared value of 0.68. Concluding that the following features (and their corresponding importance values) can predict a teams finishing rank with 68% accuracy. The following image represents predicted values plotted against their respective true values. In a model with an r-squared value of 1 (100% accuracy), the points would all be plotted on the diagonal red line.

<img src="/images/model1_accuracy.png" alt="Model1_accuracy" width="600"/>
<br>

### Model 2: Predicting Number of Wins using Ordinary Least Squares

The second model this project chooses is to predict Wins, another outcome that contributes to rank but is possibly more linear and universal. By employing four models to iterate through low p-value features, the resulting r-squared value was 0.53, indicating that the linear model found it more challenging to predict wins compared to rank. This suggests that the relationship between the features and wins is not as strong as the relationship between the features and rank.
<br>

### Model 3: Predicting Number of Wins using Random Forest

Since wins can not be modeled very well linearly, this project decides to try a nonlinear predictive model... a Random Forest, using the already curated features from the previous linear models with low p-values. After running a Bayesian Search for optimal number of estimator, minimum samples per leaf, and max depth, the resulting r-squared value is 0.49... pointing to the fact that the chosen features are not great as stand alone predictors for wins. The model needs more effective features to accurately predict wins, therefore this project will try to predict another variable that directly contributes to wins... Runs.

### Model 4: Predicting Number of Runs using Ordinary Least Squares

A random forest regression model was trained on the preprocessed data using 500 trees. The model achieved an R-squared score of 0.73 on the test data.

### Model 5: Predicting number of Runs using Random Forrest

A random forest regression model was trained on the preprocessed data using 500 trees. The model achieved an R-squared score of 0.73 on the test data.

### Model 6: Predicting number of Runs using Polynomial Regression

<img src="/images/model6_accuracy.png" alt="Model6_accuracy" width="600"/>



### Conclusion

The random forest regression model performed the best in predicting runs scored in a baseball game, achieving an R-squared score of 0.47 on the test data. However, all the models except for the simple linear regression model achieved similar performance, with R-squared scores ranging from 0.43 to 0.47.

Overall, this report shows that a variety of regression techniques can be used to predict runs scored in a baseball game, and that the choice of technique may depend on the specific problem and data at hand.
