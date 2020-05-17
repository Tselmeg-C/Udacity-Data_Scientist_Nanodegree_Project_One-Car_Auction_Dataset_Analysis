# USA_Online_Car_Auction_Dataset_Analysis

## Project Overview

For this project, I picked a US online car auction dataset from Kaggle and exemplified exploratory data analysis following the CRISP-DM process. Three self-defined business-related questions were answered. This dataset included Information about 28 brands of used vehicles for online auction in the US. Twelve features including 'Unnamed: 0', 'price', 'brand', 'model', 'year', 'title_status', 'mileage', 'color', 'vin', 'lot', 'state', 'country', 'condition' were assembled for 2499 cars.",
The three questions are the following:

    1) Which brand has the largest number of cars for sale?
    2) How is the mileage related to the price?
    3) How does the color of the car affect the price?

## Data Preparation:

Data types, shape of data frame, categorical features, and "Null" values were checked and handled. 

## Data Analysis:

This part was done aligned with the order of the three questions.

### Question One: Which brand has the largest number of cars for sale?

The number of cars of each brand was calculated and visualized using boxplot. For additional information price of each brand was also analyzed and visualized using boxplot.

### Question Two: How is the mileage related to the price?

Pearson correlation coefficient was calculated between each numeric variable within this dataset and visualized using a heatmap. A scatter plot was used to visualize the change in price along with the mileage, and a curve was fitted to the dataset. Standard approaches including identifying outliers, determining appropriate treatment of missing values were involved in this part of the analysis.

### Question Three: How does the color of the car affect the price?

The number of cars and their prices were calculated for each color and visualized with a boxplot. 

## Modeling:

The goal of this part is to predict the auction price of cars, given certain features or characteristics. In reality, this might pose a great meaning to this online car auction business.

Five treatment was designed to find out the best fit model. 

   1) Model_one: Linear regression model, with ‘price’ as the response variable and ‘mileage’,’year’,’converted_condition’ as explanatory variables.

   2) Model_two: ElasticNet (linear regression considering regularization) with ‘price’ as response and ‘mileage’,’year’,’converted_condition’ as explanatory variables.

   3) Model_three: ElasticNet model with ‘price’ as the response variable and all the other numeric and categorical (numeric transferred) features as explanatory variables.

   4) Model_four: ElasticNet model with ‘price’ as the response variable and all the other numeric and categorical (One-Hot encoding) features as explanatory variables.

   5) Model_five: XGBoost with ‘price’ as the response variable and all the other numeric and categorical (One-Hot encoding) features as explanatory variables.

## Overall Findings

According to the result, models considering both numeric and categorical variables outperform models with only numeric variables. The performance of models introducing regularization into the linear regression (ElasticNet) is better than the linear regression model without regularization. And the performance of ElasticNet on a dataset where the categorical variables are encoded with One-Hot (Model_four) is better than using numeric encoding. XGboost outperforms linear regression models, gave the highest r2-score.

## Conclusion

Overall R2 score (using XGboost) indicates that ~ 73% of the variance in the response variable (the car price) in the test data set is explained by our feature(s) relative to our predictions.
