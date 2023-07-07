# Prediction of Product Sales

## Understanding Properties of Items and Outlets that Generate Sales

Author: Kris Barbier

### Business Problem:

What kinds of items and outlets generate the most sales?

### Data:

Data Source: https://drive.google.com/file/d/1syH81TVrbBsdymLT_jl2JIf6IjPXtSQw/view

Data Dictionary:

<img width="630" alt="Screen Shot 2023-07-06 at 8 53 32 AM" src="https://github.com/krisbarbier/Prediction-of-Product-Sales/assets/134635095/db0670b2-55c2-4b0a-af23-168b8d94f598">

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

![Unknown-2](https://github.com/krisbarbier/Prediction-of-Product-Sales/assets/134635095/f94f35a7-e571-4faf-9904-00e3bd90dd41)

- In this visual, we can see that there is a positive correlation between an item's maximum retail price and the overall sales. This means that as the item's prices increase, so do overall sales. If outlets carry higher priced items, their overall sales will increase.
  
**Visual 2: Item Type and Sales**

![Unknown-3](https://github.com/krisbarbier/Prediction-of-Product-Sales/assets/134635095/514e9e45-321d-4550-a2ce-97dc3eb1ea3d)

- Here, we can see that the type of item also impacts overall sales. Depending on what type the item is, it could generate more sales for the company. The types of items sold should be considered in order to improve sales.
  
**Visual 3: Outlet Type and Sales**

![Unknown-4](https://github.com/krisbarbier/Prediction-of-Product-Sales/assets/134635095/191c3ca7-2505-4cb7-906f-b3cb47138875)

- Finally, this visual shows that 'Supermarket Type 3' outlets generate the most sales overall. In order to keep increasing sales, the company should utilize this type of outlet more.

## Models

The results of the machine learning models were as follows:

**Linear Regression:**

<img width="526" alt="Screen Shot 2023-07-06 at 9 37 03 AM" src="https://github.com/krisbarbier/Prediction-of-Product-Sales/assets/134635095/c9086160-74cf-41f4-bf3f-e99440a7b007">

**Random Forest:**

<img width="526" alt="Screen Shot 2023-07-06 at 9 37 17 AM" src="https://github.com/krisbarbier/Prediction-of-Product-Sales/assets/134635095/6718fa03-cf65-40d0-a936-d9cd49eb4a41">

**Tuned Random Forest:**

<img width="526" alt="Screen Shot 2023-07-06 at 9 37 27 AM" src="https://github.com/krisbarbier/Prediction-of-Product-Sales/assets/134635095/166cc028-43cc-403e-99e4-9aadc9eecd4f">

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
