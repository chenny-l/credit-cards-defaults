# Credit Card Defaults Prediction

This project explores a dataset of 30,000 credit card clients from a retail bank in Taiwan, combining customer profiles, credit limits, and detailed repayment behavior in a span of 6 months. Using 23 features, including demographics, payment history, bill statements, and prior repayments, we model the probability of default for the next month. 

Building on prior research focused on predictive accuracy (link [here](https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients)), this project compares **Logistic Regression**, **Decision Tree**, and **XGBoost** using **AUC** and **confusion matrices** to evaluate how well each model distinguishes between good and bad customers, with particular attention to false negatives (missed defaulters).

Based on model performance and interpretability, a Decision Tree is selected to drive business decisions. The model outputs are then translated into a practical credit strategy, including risk-based approval thresholds, quantification of value at risk, and assessment of lost opportunity from declined but creditworthy applicants.


## Overview

This dataset contains 23 features and 1 target. 


| Name | Role | Type | Units | Description |
| --- | --- | --- | --- | --- |
| **ID** | Identifier | Integer | - | Unique ID for each customer. No inherent meaning beyond identification. |
| **LIMIT_BAL (X1)** | Feature | Integer | NT dollars | Credit limit of the customer’s card. Higher value → bigger credit line. |
| **SEX (X2)** | Feature | Integer | - | Gender of the customer: `1 = male`, `2 = female`. |
| **EDUCATION (X3)** | Feature | Integer | - | Education level: typically `1 = graduate school`, `2 = university`, `3 = high school`, `4 = others`. |
| **MARRIAGE (X4)** | Feature | Integer | - | Marital status: `1 = married`, `2 = single`, `3 = others`. |
| **AGE (X5)** | Feature | Integer | years | Age of the customer. |
| **PAY_0 (X6)** | Feature | Integer | - | Repayment status for **September** (latest month). Codes: `-1 = pay duly`, `0 = use revolving credit, paid in full`, `1 = payment delay 1 month`, `2 = payment delay 2 months`, etc. |
| **PAY_2 (X7)** | Feature | Integer | - | Repayment status for **August** (one month earlier). Same coding as PAY_0. |
| **PAY_3 (X8)** | Feature | Integer | - | Repayment status for **July**. |
| **PAY_4 (X9)** | Feature | Integer | - | Repayment status for **June**. |
| **PAY_5 (X10)** | Feature | Integer | - | Repayment status for **May**. |
| **PAY_6 (X11)** | Feature | Integer | - | Repayment status for **April**. |
| **BILL_AMT1 (X12)** | Feature | Integer | NT dollars | Amount of bill statement in **September**. Shows outstanding balance. |
| **BILL_AMT2 (X13)** | Feature | Integer | NT dollars | Bill amount for **August**. |
| **BILL_AMT3 (X14)** | Feature | Integer | NT dollars | Bill amount for **July**. |
| **BILL_AMT4 (X15)** | Feature | Integer | NT dollars | Bill amount for **June**. |
| **BILL_AMT5 (X16)** | Feature | Integer | NT dollars | Bill amount for **May**. |
| **BILL_AMT6 (X17)** | Feature | Integer | NT dollars | Bill amount for **April**. |
| **PAY_AMT1 (X18)** | Feature | Integer | NT dollars | Amount paid in **September**. Shows repayment value. |
| **PAY_AMT2 (X19)** | Feature | Integer | NT dollars | Amount paid in **August**. |
| **PAY_AMT3 (X20)** | Feature | Integer | NT dollars | Amount paid in **July**. |
| **PAY_AMT4 (X21)** | Feature | Integer | NT dollars | Amount paid in **June**. |
| **PAY_AMT5 (X22)** | Feature | Integer | NT dollars | Amount paid in **May**. |
| **PAY_AMT6 (X23)** | Feature | Integer | NT dollars | Amount paid in **April**. |
| **Y** | Target | Binary | NT dollars | Default payment next month. 0 = No, 1 = yes |

## Data Set

The data set for this project is available in [.csv file](https://github.com/chenny-l/credit-cards-defaults/blob/main/datasets/credit_default_clients.csv). 
The full detailed analysis is available in [jupyter notebook](https://github.com/chenny-l/credit-cards-defaults/blob/main/notebooks/credit_card_default_prediction.ipynb).

## Preliminary Analysis

We noticed that the data is imbalanced at the first glance. The amount of non-defaulters is way 



