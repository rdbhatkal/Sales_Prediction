# Big Mart Sales Prediction
## Random Forest Regression 

**Reeva Bhatkal** 

## Business problem:

Big Mart wants to understand the features that impact the sales of products across their 10 outlets. Using a prediction model, we will help Big Mart analyze the properties of products and outlets that play crucial roles in increasing sales. 


## Data:
The Big Mart Sales Analysis data set was collected from:
https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/
The dataset contains sales data for 1559 products across 10 stores of the Big Mart chain. 

Here is the Data Dictionary for this dataset:


| Variable Name               | Description |
| ----------------------------|:-------------:|
| Item_Identifier             | Unique product ID     |
| Item_Weight                 | Weight of product     |
| Item_Fat_Content            | Whether the product is low fat or regular   |
| Item_Visibility             | The percentage of total display area of all products in a store allocated to the particular product     |
| Item_Type                   | The category to which the product belongs    |
| Item_MRP                    | Maximum Retail Price (list price) of the product     |
| Outlet_Identifier           | Unique store ID     |
| Outlet_Establishment_Year   | The year in which store was established     |
| Outlet_Size                 | The size of the store in terms of ground area covered     |
| Outlet_Location_Type        | The type of area in which the store is located     |
| Outlet_Type                 | Whether the outlet is a grocery store or some sort of supermarket     |
| Item_Outlet_Sales           | Sales of the product in the particular store. This is the target variable to be predicted.  |




*Note:  Please note that the data may have missing values as some stores might not report all the data. We will be required to treat missing values accordingly.

## Methodology
1. Use pandas library to perform data cleaning: 
    1. Deleting duplicate values
    1. Identifying and handling missing values by imputing its mean
    1. Replacing the miscoded information 
2. Create Exploratory Data Analysis on the data using pandas.
3. Create Explanatory visualization of feature distributions and correlation using matplotlib, seaborn and pandas
4. Build regression models on selected features and target variable  
    1. Identify three types of features (Numeric, Ordinal, Nominal)
    1. Transform each type of feature for machine learning
    1. Use ordinal encoding for ordinal categorical features.
    1. Use OneHotEncoder() to one-hot encode nominal categorical features.
    1. Use SimpleImputer to impute missing values 
    1. Use ColumnTransformer to perform different imputation strategies on different columns
    1. Combine pipelines and column transformers to perform multiple transformations on different subsets of data.
5. Evaluate the regression model using mean absolute error, mean squared error, root mean squared error and R-squared score in Python.
6. Choose the most important metric for the analysis


## Results


### UNDERSTANDING SALES AT DIFFERENT OUTLETS


<img src ="Images/Sales by Outlet.png">

This box plot shows us how each Outlet is performing with respect to its sales. We can see that outlet OUT027 is performing great in terms of Item_Outlet_Sales while OUT010 and OUT019 are performing poorly

### ANALYZING AVAERAGE SALES BY ITEM TYPE AT DIFFERENT OUTLETS 

<img src ="Images/Avg Sales by Item Type.png">

The above vizualization shows us the Sales of items by its Item_Type

* In Supermarket Type 1 Seafood and Starchy Food have highest sales

* In Supermarket Type 2 Seafood and Hard Drinks have highest sales

* Grocery Stores Breakfast and Meat item types have the hieghest sales

* In Supermarket Type 3 Breakfast and Fruits and Vegetables have highest sales

### ITEM_MRP of TOP 3 ITEM TYPES (ie. Baking Goods, Breads & Breakfast) FOR EACH OUTLET TYPE
<img src ="Images/MRP at Outlet.png">

From the above visualization, we can see that, For Baking Goods:

#### For Baking Goods:
   * The median price is the almost the same for Supermarket Type2, Supermaket Type 3 and Grocey Store
   * The median price for Supermarket Type 1 is slightly lower than
   * The mean price for Baking Goods across the different outlets is almost the same
   * The mean price is higher than the median price for all outlet Types
#### For Breakfast Items:
   * The median Breakfast item price Supermarket Type2 is much lower than the other outlets
   * The median Breakfast item price for Supermarket Type 3 is higher than all other outlet types
   * Supermarket Type 2 has the lowest mean price for Breakfast items while Supermarket Type3, Supermaket Type 1 and Grocey Store have similar mean price
#### For Bread Items:
   * The median price for Bread across the different outlets is almost the same
   * The mean Bread price for Supermarket Type 3 and Grocery store are similar and is higher than all other outlet types

## Model

We build a Linear Regression model and a  Random Forest Regression to understand which is more reliable for prediction of the Item_Outlet Sales. 
#### Linear Regression gives the following metrics:
Train Evaluation
MAE 846.9176886107637,
 MSE 1301889.0402027466,
 RMSE: 1141.0035233086471,
 R^2: 0.5600917296341095 

Test Evaluation
MAE 805.754926513374,
 MSE 1201631.7387397676,
 RMSE: 1096.1896454262683,
 R^2: 0.5644647949621047
 
 We can see that the RMSE value of the test data is approximatley 1096. The RMSE value tells us that the average deviation between the predicted Item_Outlet_Sales made by the model and the actual Item_Outlet_Sales is approximatley $1,096.
 The R^2 value tells us that the variables in the ML model we created are able to explain 56.4% of the variation in the Item_Outlet_Sales.
 
 
 Next we apply Ridge regression to see if we can Regularize our Linear regression model 
 #### Ridge Regression gives the following metrics:
 Train Evaluation
MAE 847.5487817352333,
 MSE 1300951.191335338,
 RMSE: 1140.5924738202239,
 R^2: 0.5604086287402438 

Test Evaluation
MAE 804.5781615636313,
 MSE 1196906.3290611205,
 RMSE: 1094.0321426087628,
 R^2: 0.5661775345701946 

We see that there no improvement in our metrics by normalizing our Regression model so we try a different model 

#### Random Forest Regression gives us an initial test and train score of 

Train Evaluation
MAE 305.88789018102386,
 MSE 199838.11596472378,
 RMSE: 447.03256700683875,
 R^2: 0.932474706190376 

Test Evaluation
MAE 807.2115214143415,
 MSE 1358856.6603631238,
 RMSE: 1165.7000730733114,
 R^2: 0.5074781273595064 

We see that the R^2 value is just 50.7%. The random forest model currently has a high variance. Lets try to tune our model to see if we can get a balanced model by tuning the parameters

We will look at 4 Random Forest hyperparameters and understand how to tune and optimize them to get a better R^2 score

max_depth
n_estimators
min_sample_split
min_samples_leaf

After tuning we see that the new metrics for the model are as below: 
Train Evaluation
MAE 755.8202036144247,
 MSE 1153575.761980628,
 RMSE: 1074.0464431208866,
 R^2: 0.6102067822078885 

Test Evaluation
MAE 728.6857362036918,
 MSE 1097898.9198369163,
 RMSE: 1047.8067187401102,
 R^2: 0.6020630816030641 
 
 RMSE
We can see that the RMSE value of the test data is approximatley 1047. The RMSE value tells us that the average deviation between the predicted Item_Outlet_Sales made by the model and the actual Item_Outlet_Sales is approximatley $1,047.

Using Linear Regression our RMSE value was 1096. Even though our model is improved a little, it is not significant

R^2
The R^2 value tells us that the variables in the ML model we created are able to explain 60.2% of the variation in the Item_Outlet_Sales.

Using Linear Regression our R^2 value was 56.4%. Our model has improved by manupilating the hyperparameters in the Random Forest Regression

## Recommendations:

We Recommend using Random Forest Regression for prediction of the Item_Outlet Sales. 

Through our analysis we found that even though Linear regression had a balance model, there were very miniscual changes to the R^2 score when we regulized the regression model . 

The Random Forest Regression tree had a very high variance in the inital model, but we were able to use hyperparameters to reduce the variance and produce a R^2 score of 60.2 % compared to 56.4% from the Linear regression model 


## Limitations & Next Steps

Since Big Mart chain will continue to collect data, we will also be able to create a more powerful model in future as the model will keep learning as we add more data points. Given that Random Forest has numerous hyperparameters, we can always use these to understand and optimize our model  



