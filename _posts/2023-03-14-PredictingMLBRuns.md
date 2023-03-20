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

[Baseball Modeling (Code)](https://github.com/jamiesolomon/ModelingMLBTeams)
 <br>

This project iterates through various regression models for predicting the outcome of an MLB season. Finally, this project uses the most successful models to rank the importance of the analyzed features. The dataset used in this project contains batting statistics from Major League Baseball teams from 1951 to 2021.

### Models and their corresponding R-Squared Score:
1. Predicting Season Rank using Ordinary Least Squares - 0.68
2. Predicting Number of Wins using Ordinary Least Squares - 0.52
3. Predicting Number of Wins using Random Forest - 0.48
4. Predicting Number of Runs using Ordinary Least Squares - 0.93
5. Predicting number of Runs using Random Forrest - 0.86
6. Predicting number of Runs using Polynomial Regression - 0.92

<br>

---

### Data Preprocessing

Before training the models, the data was preprocessed to remove time periods with missing values. The data was scaled using a Min/Max scaler for all models except the random forests. Lastly, extra batting statistics including On-Base percentage and OPS was scraped from MLB.com using the python library beautiful soup. <br>

---

### Model 1: Predicting Season Rank using Ordinary Least Squares - 0.68

The first model this report chooses to use is Ordinary Least Squares, from the statsmodels library. Reason being it has a great summarization method that can be used to filter out any insignificant features due to a low p-value, as well as track the initial success of the model quickly. The final model after filtering out low p-value features resulted in an average R-Squared value of 0.68. Concluding that the following features (and their corresponding importance values) can predict a teams finishing rank with 68% accuracy. The following image represents predicted values plotted against their respective true values. In a model with an r-squared value of 1 (100% accuracy), the points would all be plotted on the diagonal red line. <br>

<img src="/images/model1_accuracy.png" alt="Model1_accuracy" width="600"/>
<img src="/images/model1_coefs.png" alt="Model1_coefs" width="600"/>
<br>

---

### Model 2: Predicting Number of Wins using Ordinary Least Squares - 0.52

The second model this project chooses is to predict Wins, another outcome that contributes to rank but is possibly more linear and universal. By employing four models to iterate through low p-value features, the resulting r-squared value was 0.53, indicating that the linear model found it more challenging to predict wins compared to rank. This suggests that the relationship between the features and wins is not as strong as the relationship between the features and rank.
<br>

---

### Model 3: Predicting Number of Wins using Random Forest - 0.48

Since wins can not be modeled very well linearly, this project decides to try a nonlinear predictive model... a Random Forest, using the already curated features from the previous linear models with low p-values. After running a Bayesian Search for optimal number of estimator, minimum samples per leaf, and max depth, the resulting r-squared value is 0.49... pointing to the fact that the chosen features are not great as stand alone predictors for wins. The model needs more effective features to accurately predict wins, therefore this project will try to predict another variable that directly contributes to wins... Runs. <br>

---

### Model 4: Predicting Number of Runs using Ordinary Least Squares - 0.93

From this moment on, this report will only be using what will be referred to <i>atomic batting statistics</i>. These are the statistics that strictly contribute to offense (runs) without over lapping with each other (eg: OPS and OBP).
The atomic batting statistics chosen are:
 + Singles
 + Doubles
 + Triples
 + Homeruns
 + Walks

The following heatmap displays the correlation between all features being used in the model:
<br>
<img src="/images/corr_heatmap.png" alt="Correlation_Heatmap" width="900"/>
<br>
The first model this report chooses to run on the <i>atomic features</i> is (of course) an Ordinary Least Squares regression, due to its summarization method and quick p-value checking. The model runs incredibly well, boasting the best r-squared value in the entire project of 0.93. This means the current model can predict the number of runs a team gets in one season with a high degree of accuracy using the aforementioned features... now the question begs: Which features contributes the most to runs? and which features should a team focus less on investing in. The following bar graph ranks the coefficient values in which the linear model assigned to each feature. <br>
<img src="/images/model4_coefs.png" alt="Model4_Coefficients" width="600"/>

---

### Model 5: Predicting number of Runs using Random Forest - 0.86

Model 5 employs a Random Forest algorithm. A grid search was performed to find the optimal hyperparameters for the model. With an R-squared value of 0.86, Model 5 indicates a strong correlation between the selected features (Homeruns, Singles, Doubles, Triples, and Walks) and the number of runs scored. This model provides valuable insights into the relationship between various baseball statistics and team performance.

---

### Model 6: Predicting number of Runs using Polynomial Regression - 0.92

The final model this report uses a Polynomial Regression algorithm. Before modeling, the data was scaled, and a grid search was conducted to find the optimal hyperparameters. Model 6 achieved an impressive R-squared value of 0.92, suggesting a stronger relationship between the predictor variables (Homeruns, Singles, Doubles, Triples, and Walks) and the outcome compared to Model 5. The results from Model 6 further advance our understanding of the relationship between various baseball statistics and team performance.

<img src="/images/sumCoefs_model6.png" alt="Model6_coefs" width="600"/>

<img src="/images/model6_accuracy.png" alt="Model6_accuracy" width="500"/>


---

### Conclusion

This project explored various regression techniques to predict MLB season outcomes and identify the most significant baseball statistics contributing to runs scored. This statistic was chosen since it was much more susceptible to a linear regression than Wins or Rank (the initial goal of this project).

Six models were employed, with Model 4 (Ordinary Least Squares), Model 5 (Random Forest), and Model 6 (Polynomial Regression) achieving the highest R-squared values when predicting the number of runs scored <i> using atomic batting statistics </i>(Homeruns, Singles, Doubles, Triples, and Walks).

The results indicate that these atomic batting statistics play a crucial role in determining the number of runs scored. Model 4 (Ordinary Least Squares) demonstrated the strongest relationship between predictor variables and outcomes, with an R-squared value of 0.93, followed closely by Model 6 (Polynomial Regression) with an R-squared value of 0.92. The feature importance rankings derived from these models can help guide team management strategies, as they offer insights into which baseball statistics have the most significant impact on runs scored and, ultimately, team performance.

Future work could include incorporating additional features such as defensive statistics, exploring different machine learning techniques, or analyzing player-level data to refine the models further and gain a deeper understanding of the factors contributing to a successful MLB season.

