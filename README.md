# Prediction of Product Sales

## Understanding Properties of Items and Outlets that Generate Sales

Author: Kris Barbier

### Business Problem:

What kinds of items and outlets generate the most sales?

### Data:

Data Source: https://drive.google.com/file/d/1syH81TVrbBsdymLT_jl2JIf6IjPXtSQw/view

Data Dictionary:

![Data Dictionary](https://github.com/krisbarbier/Prediction-of-Product-Sales-/assets/134635095/d961aa38-a6de-4f16-aa57-957ae7727244)


## Methods:

- The following methods were used to clean and prepare the data for machine learning:
  - Data Cleaning: The data was cleaned by looking for and removing duplicates, identifying null values and filling them with placeholders for EDA, and fixing inconsistencies in categorical columns.
  - EDA: Exploratory Data Analysis was conducted and including visualizing distributions with histograms and boxplots, counts for categorical columns, and a correlation heatmap to show variable relationships.
  - Feature Inspection: Feature inspection was completed on all features, and included univariate and multivariate visualizations to show important factors that impact sales.
  - Machine Learning Pre-Processing: Pre-processing was completed on the data to prepare it for machine learning and inlcuded imputing the mean for numeric null values, imputing a placeholder value of "Missing" for categorical null values, OneHot and Ordinal encoding of categorical features, and scaling of numeric and ordinal features after encoding.
  - Modeling: The following models were used to predict sales:
    - Linear Regression
    - Random Forest
    - Tuned Random Forest

## Results

From our analysis, we can see that certain items being sold and certain outlets do play a role in generating sales for the company. The most important factors for generating sales include the item's maximum retail price, the type of item, and the outlet type. The following visuals will recap these findings:

**Visual 1: Item Maximum Retail Price and Sales**

![Item MRP Viz](https://github.com/krisbarbier/Prediction-of-Product-Sales-/assets/134635095/dce84c0c-1fef-429b-9d0f-0b3de0669dcf)

- In this visual, we can see that there is a positive correlation between an item's maximum retail price and the overall sales. This means that as the item's prices increase, so do overall sales. If outlets carry higher priced items, their overall sales will increase.
  
**Visual 2: Item Type and Sales**

![Item Type Viz](https://github.com/krisbarbier/Prediction-of-Product-Sales-/assets/134635095/b6e39fed-c804-485a-ad8c-a96bb543def5)


- Here, we can see that the type of item also impacts overall sales. Depending on what type the item is, it could generate more sales for the company. The types of items sold should be considered in order to improve sales.
  
**Visual 3: Outlet Type and Sales**

![Outlet Type Viz](https://github.com/krisbarbier/Prediction-of-Product-Sales-/assets/134635095/77b686c0-2459-4a10-9d6e-c3beb6ddefdc)


- Finally, this visual shows that 'Supermarket Type 3' outlets generate the most sales overall. In order to keep increasing sales, the company should utilize this type of outlet more.

## Models

The results of the machine learning models were as follows:

**Linear Regression:**

![Linear Regression](https://github.com/krisbarbier/Prediction-of-Product-Sales-/assets/134635095/6efd082c-d665-4db2-a845-33a23fef91c9)

**Random Forest:**

![Random Forest](https://github.com/krisbarbier/Prediction-of-Product-Sales-/assets/134635095/4c35c2ae-4860-411a-8442-094c83b445e2)

**Tuned Random Forest:**

![Tuned Random Forest](https://github.com/krisbarbier/Prediction-of-Product-Sales-/assets/134635095/b1e64bed-5b39-47e6-85d1-9e34003ec096)

- The best performing model was the Tuned Random Forest.
- The R2 score of 0.590 shows that the model still did not fit the data very well, but it was better than the default random forest and the linear regression model.
- The tuned random forest has an MAE of 739.126, which means the error averaged about $739.
- The RMSE of the tuned random forest was 1064.156, which means this error was about $1064. This metric also penalizes larger errors more than MAE.

## Recommendations:

Based on the analysis of this data, I would recommend the following:

- In order to increase sales, the company should continue to carry items with higher prices and items of certain types that sell the most.
- The company should also utlitize Supermarket Type 3 outlets in order to increase sales further.

## Limitations and Next Steps:

In this project, some limitations included not focusing on removing outliers from the data that may have impacted the overall performance of the machine learning models. In future, I would look to remove outliers and also try different tuning methods for the models in order to further increase performance to a more desired level.

### For Further Information:

For any additional questions, please contact:

- Kris Barbier: krisbarbier02@gmail.com
