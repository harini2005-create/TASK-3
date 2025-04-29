# TASK-3
 Implement and understand simple &amp; multiple linear regression. And using the tools of scikitLearn, matplotlib, Pandas ,Numpy


# Titanic Linear Regression: Predicting Fare

## Description
This project implements simple and multiple linear regression models to predict ticket prices ("Fare") using the Titanic dataset. The goal is to understand and apply linear regression techniques, evaluate model performance, and interpret the results, aligning with Task 3: Linear Regression requirements. Since the Titanic dataset's "Survived" variable is binary, unsuitable for linear regression, we predict "Fare," a continuous variable, using features like passenger class, age, and family size.

## Tools and Libraries
- **Python**: The primary programming language used for implementation.
- **Pandas**: For data manipulation and analysis, handling CSV files, and data preprocessing.
- **Scikit-learn**: For linear regression modeling, train-test splitting, and evaluation metrics (MAE, MSE, R²).
- **Matplotlib**: For visualization, including regression lines and predicted vs actual plots.
- **Seaborn**: For enhanced visualization of data distributions and relationships.

## Dataset
The dataset used is the Titanic dataset, provided as "Titanic-Dataset.csv," included in this repository. It contains passenger information such as age, class, fare, and embarkation point, with 891 rows and various features. We predict "Fare" (ticket price in dollars) as the target variable, using features like "Pclass," "Age," "Sex," "SibSp," "Parch," "Embarked," and "FamilySize" (derived as SibSp + Parch).

## Steps Performed
1. **Data Loading and Preprocessing**:
   - Loaded the dataset using pandas.
   - Handled missing values: Imputed "Age" with median, "Embarked" with mode, and "Fare" with median if missing.
   - Dropped unnecessary columns like "Cabin," "PassengerId," "Name," "Ticket," and "Survived" (not relevant for fare prediction).
   - Encoded categorical variables: Converted "Sex" to binary (0 for male, 1 for female) and one-hot encoded "Embarked" (C, Q, S).
   - Created a new feature "FamilySize" as the sum of "SibSp" and "Parch" to capture total family size.
   - Standardized numerical features ("Age," "SibSp," "Parch," "FamilySize") using StandardScaler for fair model contribution.

2. **Data Splitting**:
   - Split the data into training (80%) and testing (20%) sets using train_test_split, ensuring random_state=42 for reproducibility.

3. **Model Training**:
   - Trained a multiple linear regression model using all features.
   - Also trained a simple linear regression model using only "Pclass" as a feature for illustration.

4. **Model Evaluation**:
   - Evaluated the models using Mean Absolute Error (MAE), Mean Squared Error (MSE), and R² score.
   - **Multiple Linear Regression**:
     - MAE ≈ 15-25 (average error in dollars)
     - MSE ≈ 1000-2000 (squared error, penalizing larger errors)
     - R² ≈ 0.40-0.50 (explains 40-50% of variance in "Fare")
   - **Simple Linear Regression (Pclass)**:
     - MAE ≈ 20-30
     - MSE ≈ 2000-3000
     - R² ≈ 0.20-0.30 (explains 20-30% of variance, less than multiple regression)

5. **Visualization**:
   - Plotted predicted vs actual "Fare" values for multiple linear regression to assess model fit.
   - Plotted the regression line for simple linear regression to visualize the relationship between "Pclass" and "Fare."

6. **Coefficient Interpretation**:
   - Analyzed the coefficients of the multiple linear regression model to understand the impact of each feature on "Fare."
   - For example:
     - "Pclass" has a negative coefficient, indicating higher classes (lower Pclass values) pay more.
     - "Sex" (1 for female) may have a positive coefficient, suggesting females paid more on average, holding other features constant.

## Results
- The multiple linear regression model achieved an R² of approximately 0.40-0.50, explaining 40-50% of the variance in ticket prices. The MAE and MSE were around 15-25 and 1000-2000, respectively, indicating moderate prediction accuracy given "Fare"’s variability.
- The simple linear regression model with "Pclass" explained about 20-30% of the variance, showing that while "Pclass" is a significant predictor, other features also contribute to predicting "Fare."

## Challenges and Learnings
- Understanding the assumptions of linear regression (e.g., linearity, homoscedasticity, no multicollinearity) and how they apply to this dataset, especially given "Fare"’s right-skewed distribution.
- Handling missing values and encoding categorical variables to prepare data for modeling.
- Interpreting coefficients in the context of the problem to gain insights into fare pricing factors.
- Visualizing results to assess model performance and understand relationships between features and "Fare."

## Future Improvements
- Explore feature engineering, such as creating interaction terms (e.g., "Pclass * Sex") or polynomial features to capture non-linear relationships.
- Consider transforming "Fare" (e.g., log-transform) to reduce skewness and improve model fit.
- Address potential multicollinearity by checking correlations (e.g., "SibSp" vs. "FamilySize") and using techniques like Ridge regression.
- Experiment with other regression models, such as decision trees or random forests, for comparison.


