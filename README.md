## Background

The code and process notebook for this analysis and predictive modeling approaches to understand the how likely a particular loan is to get repaid. In other words, it's tool to understand the credit risk of a borrower. The most important is that this project aims to pay attentiom to the selection of model algorithms. 

In this project, I used the real data from Lending Club. Lending Club is a peer-to-peer lending company that matches borrower with investors through an online platform. It services people that need personal loans between \$1,000 and \$40,000. Borrowers receive the full amount of the issued loan minus the origination fee, which is paid to the company. Investors purchase notes backed by the personal loans and pay Lending Club a service fee. The company shares data about all loans issued through its platform during certain time periods.

## Objective

There are a number of approaches to credit risk modeling and different approach work better in different lending scenarios. Credit risk modeling depends on how effectively you can utilize data about a borrower's basic information, financial history, income, and so on to arrive at an accurate credit score. At present, machine learning and big data analytics make credit risk modeling more scientific and effecient. Through the use of SVM, XGBoost,  LightGBM and other machine learning algorithms to select the best choice of an algorithm to increase the predictive power. However, **understanding the business logic of models is always the priority for risk modeling**. Insteading of these "black box" operation of ML algorithms, this project still chooses to use the traditional model, Logistic Regression, to establish a credit risk model. 

Also, **the optimization of an algorithm is still the key point of this study**. The major steps in the model includes sample selection, customer classification, variable screening, variable grouping, WOE transformation, modeling, and model evaluation. We focus of the part of variable grouping. **Considering ID3 algorithm to find the optimized spliting points of one variable, and then to maximize the WOE of variable**. 

The objective was to establish Logistic Regression for credit risk modeling with ID3 algorithm used in variable grouping. And Comparing preditive power with XGBoost, Random Forest. 

## Data Source

This analysis will focus on the Lending Club [Loan Data](https://www.lendingclub.com/info/download-data.action) from May-2018. This document is generated in Python. 



## Apply ID3 algorithm into variable binning

1. Why need variable binning?

   Binning is to discretize continuous variables or merge discrete variables with many states into fewer states. There are mainly 3 advantages for binning. 

   1. After binning, variable is not sensitive to outliers, such as age 300;
   2. Reduce the risk of model overfitting;
   3. Can you learn the nonlinear information of the sample? Some variables are non-linear. Binning into WOE value helps variables transform into linear. 

2. Ways to bin variables

   Discretization methods fall into 2 categories: **supervised and unsupervised**.

   1. **Unsupervised methods** *do not use any information, other than the variable distribution*, to create the contiguous bins in which the values will be placed.
   2. **Supervised methods** *typically use target information in order to create bins or intervals.*

3. How ID3 algorithm works in variable binning?

   In decision tree algorithm, ID3 uses Information Gain to find the best feature and the optimized splitting points for each feature. In this sitution, ID3 only calculate one varible. What important is that ID3 will create splitting nodes to maximize Information Gain, and it will no longer to split this variable. Therefore, when we use ID3 to find the optimized nodes, it generates B-tree.





## Files

[Model.ipynb](https://github.com/jerilyt/lending-club/blob/master/Model.ipynb) -- Final model for Logitic Regression, XGBoost, Random Forest that we used.

[LCDataDictionary.xlsx](https://github.com/jerilyt/lending-club/blob/master/LCDataDictionary.xlsx) -- Description about variable.

[Dataset_Address](https://github.com/jerilyt/lending-club/blob/master/Dataset_Address) -- Data sourse.

[Model_Prototype.Rmd](https://github.com/jerilyt/lending-club/blob/master/Model_Prototype.Rmd) -- Prototype modeling in R





## Official Data Description

Data is soursed from [Lending Club](https://www.lendingclub.com/info/demand-and-credit-profile.action) official website, 

LoanStats_securev1_2019Q1.csv - loan data from the first quarter in 2019. There are 115577 records in total. First number in each row is the transation id. Data for each row contain transation information such as loan amount, term, interest rate, information about borrower like employees title, employed years, purpose, non perform loan records. The descriptions about these variables is in LCDataDictionary.xlsx.

LoanStats_securev1_2018Q4.csv - loan data from the fourth quarter in 2018. There are 128288 records in total. 

LoanStats_securev1_2018Q3.csv - loan data from the third quarter in 2018. There are 128063 records in total. 

LoanStats_securev1_2018Q2.csv - loan data from the second quarter in 2018. There are 130637 records in total. 















