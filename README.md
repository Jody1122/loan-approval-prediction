# Loan Approval Prediction using R

## Introduction

Building accurate prediction models for loan approval and default risk are crucial for minimizing financial loss and optimizing customer experience.  These models are often built using statistical methods such as regression analysis and specific market variables to access credit risk. This study aims to build and evaluate predictive models using machine learning techniques to determine the likelihood of loan approval and the risk of loan default. 

## Objectives

The objective of this study is to carry out Logistic Regression & Linear Discriminant modelling to predict whether a loan is likely defaulted or not based on applicants' profiles. The dataset for this study is sourced from Kaggle, an open-source database. The original data contains 111 columns and 39717 rows which have been trimmed to retain only relevant information to answer the guiding questions. The variables of interest include:
* loan_status
* loan_amnt
* annual_inc
* revol_util
* Grade
* Term
* Int_rate
* Installment
* Emp_length
* Dti
* Home_ownership

## Methods

Firstly, I performed data cleaning and wrangling to ensure the dataset is fit for analysis, dealing with missing values, outliers and handling irrelevant columns. The categorical variable such as loan_status was encoded into another column named loan_class, with 0 indicating no loan default and 1 indicating a default. 
Secondly, I performed EDA to understand the data before building predictive models. 
Next, Logistic Regression analysis is used to uncover the relationships between the dependent variables and the reponse which is loan_class; Starting with the full model containing all predictors, removed insignificant variables and perform VIF score to check for multicollinatiry between variables.
After that, I conducted several sampling method to check for their misclassification rates. These are 3 sampling methods used in this study 
* Simple random sampling: The training set is splited from the first 31773 rows from the full dataset, containing 80% of the data. The rest 7943 rows representing 20% of the data are for the testing set. This method randomly selects a subset of the data without considering the distribution of the outcome variable
* Stratified sampling: The training set is randomly splited from the full dataset, containing 80% of the data. The rest 20% of the data is for the testing set. The proportion of categories in your outcome variable is about the same in the training and testing datasets.
* Cluster sampling: Since this dataset includes loans from different states, each state could serve as a cluster. The training set includes 40 states. The rest 10 clusters will be in the testing set.

Lastly, I performed Linear Discriminant Analysis as an alternative methods to compare its performance with Logistic Regression Models.


## Conclusion

Different sets of variables are examined in our models due to the simplifying processes to make our models significant. The LDA model, despite high overall accuracy, got balanced accuracy at 51.07% indicating a model skewed towards predicting positives. This suggests it might be overfitting to the majority class. The logistic regression models, depending on their misclassification rates, offer a more balanced approach between identifying both classes. Although simple random sampling might not ensure proportional representation of all groups within the data, it shows the lowest misclassification rate at 13% among the three methods, potentially due to a sufficiently large and well-distributed dataset.

## Tech stacks
* R


## License

This project is licensed under the MIT License.

## References
1. Loan Classification Dataset. (2022b, April 5). Kaggle. Retrieved June 15, 2024, from https://www.kaggle.com/datasets/abhishek14398/loan-dataset
