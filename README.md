# Big Mart Sales Prediction
## Subtitle describing the analysis 

**Reeva Bhatkal**: 

### Business problem:

Big Mart wants to understand the features that impact the sales of products across their 10 outlets. Using a prediction model, we will help Big Mart analyze the properties of products and outlets that play crucial roles in increasing sales. 


### Data:
The Big Mart Sales Analysis data set was collected from:
https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/
The dataset contains sales data for 1559 products across 10 stores of the Big Mart chain. 

Here is the Data Dictionary for this dataset:

## Tables

| Variable Name        | Description |
| -------------        |:-------------:|
| Item_Identifier      | right foo     |
| Item_Weight          | right bar     |
| left baz             | right baz     |

*Note:  Please note that the data may have missing values as some stores might not report all the data. We will be required to treat missing values accordingly.

## Methods
1. Use pandas library to perform data cleaning: 
    1. Deleting duplicate values
    1. Identifying and handling missing values by imputing its mean
    1. Replacing the miscoded information 
2. Create Exploratory Data Analysis on the data using pandas.
3. Create Explanatory visualization of feature distributions and correlation using matplotlib, seaborn and pandas
4. Build regression models on selected features and target variable  
    4. Identify three types of features (Numeric, Ordinal, Nominal)
    4. Transform each type of feature for machine learning
    4. Use ordinal encoding for ordinal categorical features.
    4. Use OneHotEncoder() to one-hot encode nominal categorical features.
    4. Use SimpleImputer to impute missing values 
    4. Use ColumnTransformer to perform different imputation strategies on different columns
    4. Combine pipelines and column transformers to perform multiple transformations on different subsets of data.
5. Evaluate the regression model using mean absolute error, mean squared error, root mean squared error and R-squared score in Python.
6. Choose the most important metric for the analysis


## Results

### Here are examples of how to embed images from your sub-folder


#### Visual 1 Title
![sample image](project1_sample_image.png)

> Sentence about visualization.

#### Visual 2 Title

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
