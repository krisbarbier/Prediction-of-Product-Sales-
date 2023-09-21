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

## Regression Model Insights:

**Linear Regression Coefficients:**

![Coefficients](https://github.com/krisbarbier/Prediction-of-Product-Sales-/blob/main/LinReg%20Coefficients.png)

- **The top three positive coefficients pertain to: Outlet Identifier 27, Supermarket Type 3, and Outlet Size Medium.**
  - If your store is identified by OUT027, your item sales will increase by 675.696 dollars.
  - If your store is a type 3 supermarket, your item sales will increase by 675.696 dollars.
  - If your store is medium sized, your item sales will increase by 390.934 dollars.

- **The top 3 negative coefficients pertain to item visibility, outlet identifier 10, and outlet type grocery store.**
  - If your store increases item visibility by 1, sales will decrease by 423.390 dollars.
  - If your store is identified by OUT010, your sales will decrease by 470.982 dollars.
  - If your store is a grocery store type, your sales will decrease by 856.518 dollars.

**Random Forest Feature Importances:**

![Importances](https://github.com/krisbarbier/Prediction-of-Product-Sales-/blob/main/Feature%20Importances.png)

- **The top 5 important features are: Item_MRP, Outlet_Type_Grocery Store, Item_Visibility, Item_Weight, and Outlet_Type_Supermarket Type3.**
  - This means that the random forest model used these 5 features the most when making predictions.

### Global SHAP Plot Interpretations:

**SHAP Bar Plot**

![Bar SHAP](https://github.com/krisbarbier/Prediction-of-Product-Sales-/blob/main/images/summary_plot_1.png)

- In both the SHAP plot and the original feature importancs, we see some commonalities. In both plots, Item_MRP is the top feature used, followed by Outlet_Type_Grocery Store. The SHAP plot has Item_Visibility and Item_Weight as the next features, whereas in the original feature importances plot, these two are a little further down. The other two features that round out the top 6 are Outlet_Type_Supermarket 3, and Outlet_Identifier_OUT027. Both plots show that these are the top 6 features used.

**SHAP Dot Plot**

![SHAP Dot](https://github.com/krisbarbier/Prediction-of-Product-Sales-/blob/main/images/summary_plot_2.png)

- The top three features are: Item_MRP, Outlet_Type_Grocery Store, and Outlet_Type_Supermarket 3.
  - Item_MRP: The SHAP plot shows a higher concentration of red values toward the right side of the plot. This means that higher values in this feature will increase and item's sales.
  - Outlet_Type_Grocery Store: For this feature, the red values are most concentrated to the left of 0. This means that if an outlet is identified as a grocery store, then an item will sell for less.
  - Outlet_Type_Supermarket 3: This feature has higher concentrations of red values greater than 0. This means that outlets that are this type will result in greater sales.

### Local Explanations:

#### Item 1: The first local explanation is for an item with high mrp sold at a gorcery store.

**SHAP Plot**

![SHAP 1](https://github.com/krisbarbier/Prediction-of-Product-Sales-/blob/main/images/SHAP%201.png)

- SHAP Force Plot:
  - For this first item, the most influential feature toward a low sale prediction is that this item is sold in a grocery store. The high item price point tries to push for a higher price, but is not able to due to the store being a grocery store and not a supermarket.

**LIME Plot**

![LIME 1](https://github.com/krisbarbier/Prediction-of-Product-Sales-/blob/main/images/LIME%201.png)

- LIME Plot:
  - In this plot, we also see a low predicted value for this item. The three features that could lead to a higher sale is the high mrp, that it is not sold in a supermarket type 2, and that it is a household item. The store type being grocery store is still the most influential factor for the low prediction value of this item.
 
#### Item 2: The second local explanation is for an item with high mrp sold at a supermarket type 3.

**SHAP Plot**

![SHAP 2](https://github.com/krisbarbier/Prediction-of-Product-Sales-/blob/main/images/SHAP%202.png)

- SHAP Force Plot:
  - For item 2, we can see that the outlet type pushes the prediction to the right, while the item's sale price is actually not as high as it could be, and pushes back toward a lower prediction. In the future, this could be resolved by choosing a higher filter point for Item_MRP. For this item, the type of outlet plays the biggest role in getting a higher prediction sale value.

**LIME Plot**

![LIME 2](https://github.com/krisbarbier/Prediction-of-Product-Sales-/blob/main/images/LIME%202.png)

- LIME Plot:
  - In the LIME plot for this item, we see the same type of result. The type of outlet plays a much larger role in determining the sale value of this item. The item's price and type of item that it is push toward lower prediction values, while the outlet type(s) push toward higher values.

## Recommendations:

Based on the analysis of this data, I would recommend the following:

- In order to increase sales, the company should continue to carry items with higher prices and items of certain types that sell the most.
- The company should also utlitize Supermarket Type 3 outlets in order to increase sales further.

## Limitations and Next Steps:

In this project, some limitations included not focusing on removing outliers from the data that may have impacted the overall performance of the machine learning models. In future, I would look to remove outliers and also try different tuning methods for the models in order to further increase performance to a more desired level.

### For Further Information:

For any additional questions, please contact:

- Kris Barbier: krisbarbier02@gmail.com
