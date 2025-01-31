# Online Payment Fraud Detection

This project focuses on detecting fraudulent online payment transactions using machine learning techniques. The dataset used in this project contains various features related to transactions, such as transaction type, amount, old balance, and new balance. The goal is to build a model that can accurately classify transactions as either "Fraud" or "No Fraud."

## Table of Contents
- [Introduction](#Introduction)
- [Dataset](#Dataset)
- [Data Exploration](#Data-Exploration)
- [Features Selection](#Features-Selection)
- [Model Training](#Model-Training)
- [Results](#Results)

## Introduction
Online payment fraud is a significant issue in the digital age. Detecting fraudulent transactions in real-time can help prevent financial losses and protect users. This project uses machine learning models to classify transactions as fraudulent or legitimate based on various transaction features. The dataset contains transaction details, and the goal is to identify patterns that distinguish fraudulent transactions from legitimate ones.

## Dataset
The dataset used in this project contains the following columns:
- `step`: Represents a unit of time (1 step = 1 hour).
- `type`: Type of transaction (e.g., CASH_OUT, PAYMENT, CASH_IN, TRANSFER, DEBIT).
- `amount`: The amount of the transaction.
- `nameOrig`: The name of the origin account.
- `oldbalanceOrg`: The balance of the origin account before the transaction.
- `newbalanceOrig`: The balance of the origin account after the transaction.
- `nameDest`: The name of the destination account.
- `oldbalanceDest`: The balance of the destination account before the transaction.
- `newbalanceDest`: The balance of the destination account after the transaction.
- `isFraud`: Indicates whether the transaction is fraudulent (1) or not (0).
- `isFlaggedFraud`: Indicates whether the transaction was flagged as fraud by the system.

## Data Exploration
Before training the models, we performed exploratory data analysis (EDA) to understand the dataset better. Key observations include:

- **Imbalanced Dataset:** The dataset is highly imbalanced, with only 0.13% of transactions being fraudulent. This imbalance required careful handling during model training.
- **Transaction Types:** The dataset includes five types of transactions: *CASH_OUT*, *PAYMENT*, *CASH_IN*, *TRANSFER*, and *DEBIT*. Fraudulent transactions are primarily associated with CASH_OUT and TRANSFER types.
- **Correlation Analysis:** We analyzed the correlation between features and the target variable (`isFraud`). Features like `amount`, `oldbalanceOrg`, and `newbalanceOrig` showed higher correlation with fraud compared to others.

## Feature Selection
We selected the following features for training the models:

- `type`: The type of transaction (e.g., CASH_OUT, TRANSFER) is a critical feature because fraudulent activities are often concentrated in specific transaction types.
- `amount`: The transaction amount is a strong indicator of fraud, as fraudulent transactions often involve large amounts.
- `oldbalanceOrg`: The balance of the origin account before the transaction can help identify unusual activity, such as sudden large withdrawals.
- `newbalanceOrig`: The balance of the origin account after the transaction provides additional context about the transaction's impact on the account.

These features were chosen because they directly relate to the transaction's nature and are likely to influence whether a transaction is fraudulent or not. Other features, such as nameOrig and nameDest, were excluded because they are unique identifiers and do not contribute meaningfully to the model.

## Model Selection
We evaluated four machine learning models for this project:

1. **Logistic Regression:**
- A simple and interpretable model that works well for binary classification tasks.
- Chosen as a baseline model to compare against more complex models.

2. **K-Nearest Neighbors (KNN):**
- A non-parametric model that classifies transactions based on similarity to neighboring data points.
- Useful for capturing local patterns in the data.

3. **Support Vector Machine (SVM):**
- A powerful model for classification tasks, especially when the data is not linearly separable.
- Chosen to explore its performance on imbalanced datasets.

4. **Decision Tree:**
- A tree-based model that splits the data based on feature values to make predictions.
- Chosen because it can handle imbalanced data and capture non-linear relationships.

These models were selected to provide a diverse range of approaches to the problem, from simple linear models to more complex, non-linear models.

## Results

The accuracy of the models on the test set is as follows:

-**Logistic Regression:** 98.3%
-**K-Nearest Neighbors:** 98.8%
-**Support Vector Machine:** 97.6%
-**Decision Tree:** 99.4%

The Decision Tree model achieved the highest accuracy, making it the most effective model for this dataset. However, it's important to note that accuracy alone may not be the best metric for imbalanced datasets. Future work could include evaluating models using precision, recall, and F1-score to better assess their performance on fraud detection.
