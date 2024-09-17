# Diabetes Diagnosis using Logistic Regression

## Author

Aleksandra Kalisz  
Postgraduate Diploma in Science in Data Analytics  
National College of Ireland, Dublin, Ireland  
Email: alexkalisz@gmail.com

## Project Overview

The aim of this project is to estimate a binary logistic regression model to facilitate diabetes diagnosis based on blood test results. The dataset used in this project consists of various blood sample details collected from diabetic patients in an Iraqi University Hospital in 2020.

The project involves:
- Exploratory Data Analysis (EDA)
- Data cleaning and preprocessing
- Splitting the data into training and test datasets
- Training a logistic regression model
- Evaluating model performance using metrics such as accuracy, precision, recall, and the confusion matrix
- Testing the final model on prediabetic cases to estimate the probability of diabetes diagnosis

## Dataset

The dataset contains blood sample details of diabetic patients and includes the following 12 variables:
- **Gender**: Male/Female
- **AGE**: Patient's age
- **Urea**: A diamine, the chief nitrogenous waste product in humans
- **Cr**: Creatinine Ratio, a parameter to assess kidney function
- **HbA1c**: Average blood glucose levels
- **Chol**: Cholesterol, a parameter to assess liver function
- **TG**: Triglycerides, a type of fat in the blood used to transport energy
- **HDL**: High-density lipoprotein, the "good" cholesterol
- **LDL**: Low-density lipoprotein, the "bad" cholesterol
- **VLDL**: Very-low-density lipoprotein cholesterol
- **BMI**: Body-Mass-Index
- **CLASS**: N/Y/P – diabetes class (non-diabetic, diabetic, prediabetic)

## Data Preprocessing

The dataset was cleaned and transformed to prepare it for logistic regression modeling:
- Removed entries with the "P" class (prediabetic patients) as the objective is to predict whether prediabetic patients will develop diabetes.
- Removed unnecessary variables (e.g., ID and No_Pation).
- Converted categorical variables (Gender and CLASS) into binary variables for modeling.
- Transformed the AGE and Cr variables from character strings to numeric values.
- Checked for missing values and handled them accordingly.
- Created histograms to check data normality and applied transformations to improve normality where needed.

## Exploratory Data Analysis

Several visualization techniques (histograms, scatterplots, and correlation matrices) were used to understand the relationships between variables and identify important features. The EDA findings suggested:
- Age is a significant factor in the prevalence of diabetes.
- BMI and blood sugar levels (HbA1c) are critical indicators for diabetes.
- Some variables, such as Urea, may not be effective predictors due to similar distributions in both diabetic and non-diabetic groups.

## Model Building

A binary logistic regression model was fitted using the training data. The final model used significant predictors like HbA1c, BMI, Chol, and TG to predict the presence of diabetes. The model's performance was evaluated using:
- **Accuracy**: 96.8%
- **Precision**, **Recall**, and **F1 Score** for classification performance

### Model Evaluation

- **Confusion Matrix**: Evaluated the model on the test dataset, showing a high classification accuracy.
- **Multicollinearity Check**: Verified using the Variance Inflation Factor (VIF) values; no significant multicollinearity was found.
- **Linearity Assumptions**: Checked to ensure the relationship between predictor variables and the outcome variable was approximately linear.

## Testing the Model

The final model was tested on prediabetic cases (`CLASS == 'P'`) to estimate the probability of these patients developing diabetes. The probability was calculated to be approximately **10.3%**.

## Conclusion

- **Significant Predictors**: HbA1c, BMI, Chol, and TG were identified as significant predictors of diabetes.
- **Age Factor**: Age was found to play an essential role in diabetes prevalence, with a higher risk for individuals aged 45 and above.
- **Intervention**: The results emphasize the importance of monitoring BMI and blood sugar levels for early intervention in patients at risk of developing diabetes.

## Dependencies

The project was developed using the following libraries in R:
- `ggplot2` for data visualization
- `caret` for data splitting and modeling
- `glm` for logistic regression modeling

## How to Run the Code

1. Load the dataset into the R environment.
2. Run the data cleaning and preprocessing code to prepare the data.
3. Perform exploratory data analysis to visualize relationships between variables.
4. Fit the logistic regression model using the training dataset.
5. Evaluate the model using the test dataset and generate a confusion matrix.
6. Test the final model on prediabetic cases to estimate the probability of diabetes.

