The House Price Prediction Model is a machine learning-based approach designed to estimate real estate values using structured property data. Traditional valuation methods, such as comparative market analysis, rely on subjective assessments and limited data. In contrast, this project employs HistGradientBoostingRegressor, a state-of-the-art gradient boosting technique, to enhance prediction accuracy. The model is trained on the House Prices: Advanced Regression Techniques dataset, which includes a mix of numerical and categorical features influencing house prices. A structured data preprocessing pipeline was implemented, including missing value imputation, feature selection, categorical encoding, and outlier removal, ensuring the dataset was optimized for machine learning. HistGradientBoostingRegressor was selected for its speed, efficiency, and ability to handle missing values. The model was evaluated using Root Mean Squared Error (RMSE) and R² Score, demonstrating its predictive strength in estimating house prices. Cross-validation further ensured the model’s robustness and reliability.The results indicate that gradient boosting effectively captures complex feature interactions in real estate pricing. This project contributes to automated property valuation, providing a data-driven alternative to traditional appraisal methods. Future improvements include hyperparameter tuning, integration of economic indicators, and deployment as a web-based tool for real-world applications.

1.1 Objective of the Project
The real estate market is complex and dynamic, with house prices being influenced by multiple factors such as location, house size, year built, quality of materials, and neighborhood trends. Traditional methods for estimating house prices rely on manual assessments by real estate agents, which can be subjective and inconsistent.
The objective of this project is to develop a data-driven machine learning model using HistGradientBoostingRegressor, which can:
   1. Predict house prices based on given property features.
   2. Reduce manual errors in property valuation.
   3. Help buyers and sellers make informed decisions.
   4. Analyze market trends based on historical data.
      
1.2 Importance of House Price Prediction
A reliable house price prediction system has several real-world applications:
  1. For Home Buyers: Helps in determining whether a property is fairly priced.
  2. For Home Sellers: Assists in setting an optimal selling price.
  3. For Real Estate Investors: Aids in making profitable investment decisions.
  4. For Banks & Mortgage Lenders: Supports risk assessment for home loans.
     
1.3 Machine Learning in Real Estate
Traditional valuation models depend on comparative market analysis (CMA), which involves comparing a property to similar recently sold homes. However, this approach has limitations:
  1. Limited Data Scope: CMA considers only a few nearby properties.
  2. Human Bias: Agents may overvalue/undervalue homes.
  3. Market Fluctuations: Cannot adapt to rapid price changes.
  4. Machine learning models, on the other hand, analyze thousands of data points, learn patterns from past sales, and predict future prices more accurately.

2. Dataset Overview
2.1 Data Source and Description
The dataset used in this project is from Kaggle's House Prices: Advanced Regression Techniques competition. It consists of numerical and categorical variables that describe a property’s characteristics and its final sale price.

2.2 Features of the Dataset
The dataset includes 79 explanatory variables, which can be grouped as:
2.2.1 Numerical Features (Continuous Variables)
These are measurable quantities that directly impact house prices:
  1. LotArea: Total land area of the property (square feet).
  2. YearBuilt: Construction year of the house.
  3. GrLivArea: Above-ground living area in square feet.
  4. TotalBsmtSF: Basement area in square feet.
  5. OverallQual: Overall material and finish quality (Scale 1-10).

2.2.2 Categorical Features (Discrete Variables)
These are non-numeric attributes describing house characteristics:
  1. Neighborhood: The location of the house (e.g., Downtown, Suburban).
  2. HouseStyle: Architectural style (e.g., 1-story, 2-story).
  3. RoofStyle: Type of roof (e.g., Gable, Hip).
  4. Heating: Type of heating system (e.g., Gas, Electric).
     
2.2.3 Target Variable (Dependent Variable)
The feature that we are trying to predict:
SalePrice – The final selling price of the house (USD).

3. Data Preprocessing
Before training the machine learning model, data preprocessing is necessary to clean and transform the dataset.
3.1 Handling Missing Values
Missing values can cause errors during training. Our approach to handle them:
  1. Drop columns with more than 20% missing values.
  2. Mean Imputation for numerical features (replacing missing values with the column mean).
  3. Mode Imputation for categorical features (replacing missing values with the most common category).

3.2 Feature Selection
Feature selection helps improve model efficiency by removing irrelevant variables.
We used correlation analysis to select features with a correlation of ≥ 0.5 or ≤ 0.5 with SalePrice.

3.3 Encoding Categorical Variables
Machine learning models cannot work directly with text-based categorical data.
We used One-Hot Encoding to convert categorical features into numerical form.

3.4 Outlier Detection and Removal
Outliers were detected using boxplots and removed to prevent bias in predictions.


4. Model Selection and Justification
4.1 What is Gradient Boosting?
Gradient Boosting is a powerful ensemble learning technique that combines multiple weak models (decision trees) into a strong predictive model.

4.2 Why Use HistGradientBoostingRegressor?
  1. Optimized for Speed: Faster than traditional Gradient Boosting methods.
  2. Handles Missing Values: Works even when some data is missing.
  3. Better Generalization: Reduces overfitting compared to regular Gradient Boosting.

4.3 Model Implementation
  1. Splitting Data:
      a. 80% Training Set
      b. 20% Test Set
  2. Feature Imputation: Missing values were filled with SimpleImputer(strategy='mean').
  3. Mode Initialization: HistGradientBoostingRegressor(random_state=42) was chosen.
  4. Training: The model was trained using X_train_imputed and y_train.

5. Results and Discussion
  1. The model performed well on training data, achieving a low RMSE and a high R² score.
  2. Feature selection improved model accuracy by removing irrelevant attributes.
  3. Gradient boosting helped capture complex relationships between house features and price.

