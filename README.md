# Predictive-Modeling-of-Social-Demographics-and-Birth-Outcomes
This project explores predictive modeling using regression techniques. It applies OLS, Poisson regression, and multinomial logistic regression to predict outcomes such as birth date, number of children, and marital status. Using data from the NSFG dataset, models are built to estimate the likelihood of various demographic outcomes.

This repository explores various predictive modeling techniques including Ordinary Least Squares (OLS) regression, Poisson regression, and Multinomial Logistic Regression. The project uses the National Survey of Family Growth (NSFG) dataset to predict outcomes such as birth dates, number of children, and marital status.

Key Features
OLS Regression: Used for predicting continuous variables (e.g., predicting the date of birth based on certain factors like pregnancy week).
Poisson Regression: Applied to predict count data, such as the number of children a woman has based on demographic factors like age, race, education, and income.
Multinomial Logistic Regression: Applied to categorical data, used to predict the marital status of women based on demographic features.
Installation
To run the code in this repository, you need the following Python packages:

pandas
statsmodels
matplotlib
seaborn
To install the required libraries, you can run:

bash
Copy code
pip install -r requirements.txt
Usage
OLS Regression (Birth Prediction)
Predict the date of birth for a baby based on certain variables such as the pregnancy week, the mother's age, and other known factors at the time of pregnancy. Use OLS regression to determine the relationship between these variables.

Poisson Regression (Children Prediction)
Use Poisson regression to predict the number of children a woman might have, based on demographic information such as age, race, income, and education. The model will estimate the number of children for a given set of input variables.

Multinomial Logistic Regression (Marital Status Prediction)
Use multinomial logistic regression to predict marital status (e.g., married, cohabitating, divorced) based on variables like age, race, education, and income. The model outputs the predicted probabilities of various marital statuses.

Example
python
Copy code
import statsmodels.api as sm

# Load your dataset
data = pd.read_csv('NSFG_data.csv')

# Prepare the variables for Poisson regression
X = data[['age', 'education', 'income']]  # Example predictors
y = data['numbabes']  # Dependent variable

# Fit the Poisson regression model
poisson_model = sm.GLM(y, X, family=sm.families.Poisson()).fit()

# Make predictions
predictions = poisson_model.predict(X)
print(predictions)
Results
The models provide predictions on:

Birth Date: A regression model predicting the likely birth date of a baby based on pregnancy data.
Number of Children: Poisson regression is used to predict the number of children a woman will likely have, based on demographic features.
Marital Status: Multinomial logistic regression estimates the likelihood of a woman's marital status based on her age, income, and other personal factors.
Conclusion
This project demonstrates how to apply different regression models to make predictions based on demographic and personal information. It helps to predict continuous, count, and categorical outcomes, providing valuable insights into predictive analytics using real-world data.

License
This project is licensed under the MIT License - see the LICENSE file for details.
