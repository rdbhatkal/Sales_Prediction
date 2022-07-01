# Big Mart Sales Prediction
## Subtitle describing the analysis 

**Reeva Bhatkal**: 

## Business problem:

Big Mart wants to understand the features that impact the sales of products across their 10 outlets. Using a prediction model, we will help Big Mart analyze the properties of products and outlets that play crucial roles in increasing sales. 


## Data:
The Big Mart Sales Analysis data set was collected from:
https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/
The dataset contains sales data for 1559 products across 10 stores of the Big Mart chain. 

Here is the Data Dictionary for this dataset:

## Tables

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

Describe your final model

Report the most important metrics

Refer to the metrics to describe how well the model would solve the business problem

## Recommendations:

More of your own text here


## Limitations & Next Steps

More of your own text here


### For further information


For any additional questions, please contact **email**
