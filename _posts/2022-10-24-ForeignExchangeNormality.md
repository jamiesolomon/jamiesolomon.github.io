---
layout: post
title: "Foreign Exchange Normality EDA and Modeling"
date: 2022-10-25
desc: "Exploratory data analysis and modeling of the USD/CAD foreign exchange rate"
categories: [Data Science]
tags: [EDA, Modeling, Machine Learning]
icon: icon-data-science
---

## Introduction

This report presents an exploratory data analysis and modeling of the USD/CAD foreign exchange rate. The goal of this analysis is to determine if the USD/CAD rate follows a normal distribution and if it can be predicted using machine learning algorithms. The report is structured as follows:

1. Exploratory Data Analysis
2. Modeling
3. Conclusion

## 1. Exploratory Data Analysis

The main focus of the exploratory data analysis is on the USD/CAD foreign exchange rate. The data spans from January 2006 to December 2021 and is obtained from the Federal Reserve Economic Data (FRED) database. The analysis is divided into the following sections:

- Overall plot of USD/CAD foreign exchange rate
- Long-term periods of normality
- Subset 1: June 2006 to November 2014
- Subset 2: November 2014 to December 2021

### 1.1 Overall plot of USD/CAD foreign exchange rate

The plot below shows the USD/CAD foreign exchange rate from January 2006 to December 2021.

<img src="/images/USDCAD_2006-2014_Plot.png" alt="2006-2014 plot" width="600"/>


### 1.2 Long-term periods of normality

The hypothesis is that the USD/CAD foreign exchange rate follows a normal distribution when separated into long-term periods of time. The periods of normality indicated in this report are:

- [June 2006 - Nov 2014)
- [Nov 2014 - Dec 2021]

This notion helps machine learning algorithms assess the risk associated with a specific rate extremely efficiently strictly using technical analysis.

### 1.3 Subset 1: June 2006 to November 2014

The plot below shows the USD/CAD foreign exchange rate from June 2006 to November 2014.

<img src="/images/USDCAD_2006-2014_Plot.png" alt="2006-2014 plot" width="600"/>

The histogram below shows the distribution of the USD/CAD foreign exchange rate from June 2006 to November 2014.

<img src="/images/2006-2014_CADUSD_Hist.png" alt="histogram" width="600"/>


### 1.4 Subset 2: November 2014 to December 2021

The plot below shows the USD/CAD foreign exchange rate from November 2014 to December 2021.

<img src="/images/USDCAD_2014-2021_Plot.png" alt="2014-2021 plot" width="600"/>

The histogram below shows the distribution of the USD/CAD foreign exchange rate from November 2014 to December 2021.

<img src="/images/2014-2021_CADUSD_Hist.png" alt="histogram" width="600"/>


## 2. Modeling

The modeling section focuses on using machine learning algorithms to predict the USD/CAD foreign exchange rate. The algorithms used in this report are:

- Linear Regression
- Ridge Regression
- Lasso Regression
- Random Forest Regression

The models are evaluated using root mean squared
