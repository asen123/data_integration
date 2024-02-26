This repository contains code describing the methodology in the paper "Estimation of finite population proportions for small areas – a statistical data integration approach". The arXiv version of the paper is available at the following link: 
https://arxiv.org/abs/2305.12336

The cleaned up datasets used for this analysis are available at the following website: 
https://github.com/rdrivers/mrp-aapor/tree/master

The original PEW survey data is available at the following link: 
https://www.pewresearch.org/politics/dataset/october-2016-political-survey/

The file "Method_code.Rmd" contains the R code. Following is a description of the major steps in the code:

The R code first loads the data (2 survey data and one file with actual election results), then fits a mixed effects model using lme4 package and computes predicted values for small areas. In the next step we write a user defined function which computes parameter estimates using EM algorithm. This is the main methodology of the paper, for computing area level estimates using adjusted likelihood. This can be used on simulated datasets with the required columns names, i.e. with minor edits like changing the column names etc. This function/algorithm is then run on the small survey (PEW data) to get parameter estimates. Using the big survey (CPS) we then calculate EBP at state level which are then compared with direct estimates, through graphs and US maps. Summary measures (like RASD, AAD) are also computed at national level. In the final step, we write bootstrap function for calculating MSPE. MSPE values are obtained at state level.
