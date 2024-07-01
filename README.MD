# Machine Learning Exploration for Insurance Company

## Description

The Sure Tomorrow insurance company wants to solve several tasks with the help of Machine Learning. This project will evaluate that possibility by completing four tasks.

Task 1: Find customers who are similar to a given customer. This will help the company's agents with marketing.
Task 2: Predict whether a new customer is likely to receive an insurance benefit. Can a trained prediction model do better than an untrained dummy model?
Task 3: Predict the number of insurance benefits a new customer is likely to receive using a linear regression model.
Task 4: Protect clients' personal data without breaking the model from the previous task.

## Dataset Description

The dataset used in this project is `insurance_us.csv`, which contains information about insured individuals and their insurance benefits over the last five years. The table consists of the following columns:

- `Gender`: The gender of the insured person (1 for male, 0 for female).
- `Age`: The age of the insured person.
- `Salary`: The annual salary of the insured person.
- `Family members`: The number of family members of the insured person.
- `Insurance benefits`: The number of insurance benefits received by the insured person over the last five years.

### Sample Data

Here is a preview of the dataset:

| Gender | Age | Salary  | Family members | Insurance benefits |
|--------|-----|---------|----------------|--------------------|
| 1      | 41  | 49600.0 | 1              | 0                  |
| 0      | 46  | 38000.0 | 1              | 1                  |
| 0      | 29  | 21000.0 | 0              | 0                  |
| 0      | 21  | 41700.0 | 2              | 0                  |
| 1      | 28  | 26100.0 | 0              | 0                  |

## Objectives

Task 1: Customer Profiling

- Utilize k-Nearest Neighbors (kNN) algorithm to find similar customers.
- Evaluate the impact of scaling (MaxAbsScaler) and different distance metrics (Euclidean, Manhattan) on the kNN algorithm.
- Assess how unscaled data affects kNN and the similarity of results using Manhattan distance metric.

Task 2: Benefit Prediction

- Develop a kNN-based classification algorithm to predict the likelihood of receiving insurance benefits.
- Compare the kNN model's performance with a dummy model using the F1 metric.
- Split the data into training (70%) and testing (30%) sets.

Task 3: Benefit Magnitude Forecasting

- Build a Linear Regression (LR) model to predict the number of insurance benefits.
- Implement a custom LR algorithm and compare RMSE for original and scaled data.
- Evaluate the consistency of RMSE between scaled and unscaled data.

Task 4: Data Obfuscation

- Implement data obfuscation by multiplying the feature matrix with an invertible matrix.
- Verify the invertibility of the matrix and recover original data.
- Test LR with obfuscated data and compare RMSE and R2 metrics with the original data.

## Conclusions

Task 1 - Find Similar Customers

Scaling the data has a positive impact on the Nearest Neighbors algorithm in terms of predicting the target value, while the use of Euclidean vs Manhattan distance has a negligible impact.

Task 2 - (Binary Classification) Likelihood of Receiving Benefit(s)

For scaled and unscaled data, the kNN classifier performs best when only considering the first nearest neighbor. The classifier performs significantly better with scaled data - an F1 score of .97 compared to the unscaled F1 score of .61. The kNN classifier performs well above the dummy regressor for any of tested probabilities as well.

Task 3 - (Linear Regression) Predict Number of Benefits

The RMSE and R2 values are consistent between the scaled and unscaled data. The Linear Regression model achieved an RMSE of 0.34, indicating high predictive accuracy with small average errors, and an R2 of 0.66, signifying that 66% of the variance in the number of claims is explained by the model, demonstrating a good but improvable fit.

Task 4 - Obfuscating Data

The evaluation metrics of the model remained the same between the original dataset and obfuscated dataset, demonstrating that the model works with protected user data.

## Recommendations

Based on these findings, the Sure Tomorrow insurance company can reliably employ a linear regression model to predict the number of insurance benefits with high accuracy, as evidenced by an RMSE of 0.34 and an R2 of 0.66. Additionally, the kNN classifier, particularly with scaled data, proves to be an effective tool for determining the likelihood of a customer receiving benefits, achieving an F1 score of .97. The company's data protection measures, through obfuscation, do not affect the model's performance, ensuring both security and accuracy in their predictive analytics.
