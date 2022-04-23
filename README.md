# Project 2 - Ames Housing Data and Kaggle Challenge
---
By: Darien Ang

# Problem Statement
---


Wether you are seller, buyer or real-estate agents, housing prices are dependent on so many factors. The question is how can we determine which factors (features) that have strong influence on the housing sale price. Using the Ames(IA) dataset, the goal of this project is to create a regression model that is able to predict accurately on the sale price of each house in Ames(IA).

# Executive Summary
---

### Contents:

- Importing the Libraries
- Importing Training and Testing dataset
- Data Cleaning
- Experimental Data Analysis (EDA)
- Feature Engineering
- Pre-processing and prediction of data
- Model selection and evaluation
- Conclusion

### Data:

- [Train](../datasets/train.csv)
- [Test](../datasets/test.csv)

# Data Dictionary
---

The data dictionary may be found [here](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt).

### Data Cleaning & EDA

1. New features were created for both Train and Test data set.
2. Generate correlation figures against saleprice and remove numerical columns with low correlation.
3. Plot heatmap to check for any multicollinearity and remove columns which has lower correlation against saleprice.
4. After removing all the selected numerical columns, i will tackle on the null values and errors.
5. Depending on my assumption, most of the null values, i will replace, 'none', '0', 'mean' or 'mode'.
6. Remove outliers and also check on the distributions using seaborn.
7. Anaylze on the categorical features and remove them accordingly.
8. Used one-hot encoded matrix for categorical features.

### Model Selection and Evaluation

1. Generate train-test split, instantiate and fit model.
2. Run different regression models, Linear, Ridge, Lasso and Baseline. <br>
3. RMSE: 19574.17 (LASSO), 19574.17 (RIDGE), 19909.82 (LINEAR), 77435.05 (Baseline)
4. Kaggle Score (LASSO): 20945.41 (Private), 21767.58 (Public)

# Conclusions

Althought RIDGE has the highest RMSE, i will choose LASSO as my model as the difference is insignificant. LASSO can set coefficients to zero for those variables that are irrelevant, this will make the model simpler. LASSO model will perform best when having to predict housing within the range of 100k to 300k. <p>To fetch a better sale price, we will need to maintain/improve features that have high positive and negative coefficients. <br> Hence here are the top 5 features with positive and negative coefficients.<br>
Top 5: Gr Liv Area, Overall Qual, Functional(Typical), BsmtFin SF 1, MS Zoning(RL)<br>
Bottom 5: Remodel Age, Exter Cond(Poor), KitchenQual(TA), Home Age, Kitchen Qual(Gd)

# Recommendations

We can collect more data that will affect the saleprice:

1. Distance to amenities.
2. Crime rate / accident around the neighbourhood.

### Given Source

[Data Dictionary](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt).
