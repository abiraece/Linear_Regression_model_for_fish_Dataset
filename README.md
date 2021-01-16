Fish Weight Prediction

Table of content
1. Introduction
2. Data Description
3. Data Preprocessing and Visualization
4. Modeling Phase
5. Evalution Metrics
6. Conclusion

Introduction:  
This dataset is a record of 7 common different fish species in fish market sales. With this dataset, a predictive model can be performed using machine friendly data and estimate the weight of fish can be predicted.

Data Description:

    Species: Species name of fish
    Weight: Weight of fish in gram
    Length1: Vertical length in cm
    Length2: Diagonal length in cm
    Length3: Cross length in cm
    Height: Height in cm
    Width: Diagonal width in cm
   
Data Preprocessing and Visualization:

    1. Null Values are computed. only one row of weight has null value. missing value is less than 1%. so dropped that row alone to build model further.
    2. Seperating numerical and categorical features and perform statistical description.
    3. Species feature are in categorical nature. So it is frequency encoded.
    4. To avoid outlier affecting the model performance, outlier are treated by capping.

4. Modeling Phase:

    1. Basic Least square model was built based on input features for predicting weight of the fish
    2. To check for 5 assumption to build Linear Regression model further.
        a. Height, Length1,Species statifying Multicollinearity effect
        b. Normality test is statisfied with skewness of 0.4
        c. Linearity test is not statisfied intially, after transforming input and output features model statisfied Linearity test.
        d. Autocorrelation test is statisfied
        e. Homoscadacity test is also statisfied
    3. Different Feature selection algorithm are performed

5. Evalution Metrics:
    
     1. R-square value of the model is 84.4, Bias error of nearly 16% and variance error of 11%.
     2. From variance error we can conclude that there exist the over fitting problem.
     3. To avoid Overfitting problem, Regularization is used by GridSearchCV method to find the parameter on three different method Ridge, Lasso,ElasticNet
     4. Comparing three method Ridge give good performance of r-square.
     5. Final model was built.
     
6. Conclusion: 

     Overall OLS model performance is 97.1% with the input features of Species, Length1, Height for the dependent variable "Weight"
     For every one unit increase in Length of the fish weight is increase by 0.6548 units provided all other inputs are constant.
     similary for every one unit increase in height of the fish, weight is increased by 0.7630 units provided all other inputs are constant.
     Depending on Species also Weight of fish varies by 4.3232 units for every Species.
