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

**Imbalanced Dataset:** The dataset is highly imbalanced, with only 0.13% of transactions being fraudulent. This imbalance required careful handling during model training.

**Transaction Types:** The dataset includes five types of transactions: *CASH_OUT*, *PAYMENT*, *CASH_IN*, *TRANSFER*, and *DEBIT*. Fraudulent transactions are primarily associated with CASH_OUT and TRANSFER types.

**Correlation Analysis:** We analyzed the correlation between features and the target variable (isFraud). Features like `amount`, `oldbalanceOrg`, and `newbalanceOrig` showed higher correlation with fraud compared to others.




