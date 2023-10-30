# **Industrial Copper Modeling**

## **Problem Statement:**
The copper industry seeks to enhance pricing accuracy and lead evaluation. We aim to achieve this by:

- 1.Implementing machine learning regression models to improve pricing decisions.

- 2.Developing a lead classification model for evaluating potential customers using "WON" and "LOST" statuses.

## **Approach**

**1) Data Understanding:** 
- Identify the types of variables (continuous and categorical) and examine their distributions. Remove "Material_Reference" values starting with '00000' and treat reference columns as categorical variables, while the "INDEX" column may not be useful.

**2) Data Preprocessing:**
  -  During data preprocessing, we initially address the issue of missing values and treat '00000' values in the 'Material_Reference' column by converting them to null. Furthermore, we categorize reference columns while considering the potential removal of the 'INDEX' column, which may lack informativeness.
  - In the second step of data preprocessing, we focus on handling outliers, primarily using methods like IQR or Isolation Forest. We also address skewed data by applying appropriate transformations, such as log transformation, and encode categorical variables to prepare the dataset for analysis.
**3) EDA:**
 
 - Visualize outliers and skewness (both before and after treatment) using Seaborn's boxplot, distplot, and violinplot.

**4) Feature Engineering:**
  - Create new features through aggregation or transformation to provide more informative representations of the data. Eliminate highly correlated columns using a heatmap.

**5) Model Building and Evaluation:**

- Split the dataset into training and testing/validation sets.

- Train and evaluate different classification models (e.g., ExtraTreesClassifier, XGBClassifier, Logistic Regression) using metrics such as accuracy, precision, recall, F1 score, and AUC.

- Optimize model hyperparameters through techniques like cross-validation and grid search to identify the best-performing model.

- nterpret model results and assess performance based on the defined problem statement.


**6) Model GUI:** 

Create an interactive page using Streamlit with the following components:
  - (1) Task input (Regression or Classification).
  - (2) Input fields for each column value, except "Selling_Price" for regression models or "Status" for classification models.
  - (3) Implement feature engineering, scaling, and transformation steps used during model training. Predict new data in Streamlit and display the output.
