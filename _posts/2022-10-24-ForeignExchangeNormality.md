---
layout: post
title:  "Foreign Exchange Normality EDA and Modeling"
date:   2022-10-25
desc: "Overview of project with a link to the github repository"
keywords: "Jalpc,Jekyll,gh-pages,website,blog,easy"
categories: [HTML]
tags: [Jalpc,Jekyll]
icon: icon-html
---

[Foreign Exchange Normality Analysis and Modeling](https://github.com/jamiesolomon/ForeignExchangeNormality) <br>
[Full Report](/images/FullReport.pdf)
 + EDA
    - Mainly focused on the EDA of the foreign exchange pairing USD/CAD
    - Proof supporting the hypothosis: The USD/CAD foreign exchange rate follows a normal distribution when seperated into longterm periods of time.
    - These periods of time is what "Periodic Normality" refers to in the project report
        - The periods of normality indicated in this report are: [June 2006 - Nov 2014) amd [Nov 2014 - Dec 2021]
        - This notion helps machine learning algoriythms assess the risk associated with a specific rate extreamly efficently strictly using technical analysis.
    - 2006 to 2021 plot of USD/CAD foreign exchange rate
    <!-- ![Specified pdf plot](/images/USDCAD_FullPlot.png) -->
    <img src="/images/USDCAD_FullPlot.png" alt="usd/cad full plot" width="400"/>
    
    - First subset: June 2006 to November 2014
    <!-- ![Specified pdf plot](/images/USDCAD_2006-2014_Plot.png) -->
    <!-- ![Specified pdf plot](/images/2006-2014_CADUSD_Hist.png) -->
    <img src="/images/USDCAD_2006-2014_Plot.png" alt="2006-2014 plot" width="200"/>
    <img src="/images/2006-2014_CADUSD_Hist.png" alt="histogram" width="200"/>
    
    - Second subset: November 2014 to Devember 2021
    <!-- ![Specified pdf plot](/images/USDCAD_2014-2021_Plot.png) -->
    <!-- ![Specified pdf plot](/images/2014-2021_CADUSD_Hist.png) -->
    <img src="/images/USDCAD_2014-2021_Plot.png" alt="2014-2021 full plot" width="200"/>
    <img src="/images/2014-2021_CADUSD_Hist.png" alt="histogram" width="200"/>