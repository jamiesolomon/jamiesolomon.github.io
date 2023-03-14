---
layout: post
title:  "Foreign Exchange Normality EDA and Modeling"
date:   2022-10-25
desc: "Overview of project with a link to the github repository"
keywords: "foreign exchange, EDA, modeling, normal distribution"
categories: [EDA]
tags: [Foreign Exchange, EDA, Modeling, Normal Distribution]
icon: icon-cogs
---

## Project Overview

This report explores the hypothesis that the USD/CAD foreign exchange rate follows a normal distribution when separated into long-term periods of time. This notion helps machine learning algorithms assess the risk associated with a specific rate extremely efficiently strictly using technical analysis. The data used in this project spans from June 2006 to December 2021. 

### Code

The code for this project can be found in the following [Github repository](https://github.com/jamiesolomon/ForeignExchangeNormality). 

### Full Report

The full report can be found in the following [PDF file](/images/FullReport.pdf).

## Exploratory Data Analysis

#### The main focus of the exploratory data analysis is the USD/CAD foreign exchange pairing. This report begins by plotting the entire dataset from June 2006 to December 2021:

<img src="/images/USDCAD_FullPlot.png" alt="USD/CAD full plot" width="600"/>

#### Next, it will break the data into two subsets based on the above hypothesis:

1. June 2006 to November 2014
2. November 2014 to December 2021

### Subset 1: June 2006 to November 2014

#### The plot of the first subset is as follows:

<img src="/images/USDCAD_2006-2014_Plot.png" alt="USD/CAD plot 2006-2014" width="400"/>

#### The corresponding histogram for this subset is shown below:

<img src="/images/2006-2014_CADUSD_Hist.png" alt="Histogram 2006-2014" width="400"/>

### Subset 2: November 2014 to December 2021

#### The plot of the second subset is as follows:

<img src="/images/USDCAD_2014-2021_Plot.png" alt="USD/CAD plot 2014-2021" width="400"/>

#### The corresponding histogram for this subset is shown below:

<img src="/images/2014-2021_CADUSD_Hist.png" alt="Histogram 2014-2021" width="400"/>

### Conclusion

<h4>The exploratory data analysis supports the hypothesis that the USD/CAD foreign exchange rate follows a normal distribution when separated into long-term periods of time. The periods of normality indicated in this report are: [June 2006 - Nov 2014) and [Nov 2014 - Dec 2021]. This notion helps machine learning algorithms assess the risk associated with a specific rate extremely efficiently strictly using technical analysis.</h4>
