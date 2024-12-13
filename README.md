# **Fraud Transaction Detection Using Random Forest Classifier**
Project Overview
This project aims to build a predictive model for detecting fraudulent transactions using the Random Forest classifier. The dataset contains transaction details, with the goal of classifying each transaction as either fraudulent or legitimate. The model's purpose is to identify patterns and detect anomalies in financial transactions, ensuring reliable fraud detection in real-world scenarios.

Dataset Overview
The dataset includes transaction records with the following key features:

step: The step in the transaction process (e.g., 1, 2, etc.)
type: The type of transaction (e.g., PAYMENT, TRANSFER, CASH_OUT, etc.)
amount: The transaction amount.
nameOrig: The name of the original account.
oldbalanceOrg: The balance of the original account before the transaction.
newbalanceOrig: The balance of the original account after the transaction.
nameDest: The name of the destination account.
oldbalanceDest: The balance of the destination account before the transaction.
newbalanceDest: The balance of the destination account after the transaction.
isFraud: The target variable indicating if the transaction is fraudulent (1) or not (0).
isFlaggedFraud: A flag indicating if the transaction is suspicious.
Data Cleaning and Preprocessing
The following steps were taken to prepare the dataset for modeling:

Missing Values: The dataset did not have any missing values, ensuring the data was complete for analysis.
Removing Merchant Transactions: Transactions related to merchants (denoted by account names starting with 'M') were removed as they were irrelevant to the fraud detection task.
Balancing the Dataset: Due to the class imbalance (fraudulent transactions being rare), random sampling was performed to balance the dataset, ensuring an equal number of fraudulent and non-fraudulent transactions.
Feature Engineering: A new feature, type_numeric, was created to convert the categorical transaction type into numerical form for use in the model.
Feature Analysis
To understand the relationships between the features and the target variable (isFraud), a series of analyses were conducted:

Correlation Analysis: Identified key features that were positively or negatively correlated with fraud. Features such as step and amount showed moderate positive correlations with fraud occurrence.
Variance Inflation Factor (VIF): Checked for multicollinearity between features. High multicollinearity was observed between variables like oldbalanceOrg and newbalanceOrig, suggesting that some features might need transformation or removal to improve model performance.
Model Building
The model uses the Random Forest classifier to predict fraudulent transactions. Random Forest was chosen due to its ability to handle large datasets and its robustness in classification tasks. The model was trained using a balanced dataset to reduce bias towards the majority class (non-fraudulent transactions).

Evaluation Metrics
The model's performance was evaluated using the following metrics:

Accuracy: Measures the overall percentage of correct predictions.
Precision: The proportion of true positive predictions (fraudulent transactions) out of all positive predictions.
Recall: The proportion of true positive predictions out of all actual fraudulent transactions.
F1-Score: The harmonic mean of precision and recall, providing a balanced measure of model performance.
Conclusion
This project demonstrates the application of Random Forest for detecting fraudulent transactions. Despite the challenges posed by class imbalance, the model effectively identifies fraudulent transactions, which is crucial for preventing financial fraud. Further improvements could include exploring other machine learning models, optimizing hyperparameters, and addressing the identified multicollinearity.

Requirements
Python 3.x
pandas
numpy
matplotlib
seaborn
scikit-learn
statsmodels
Future Work
Explore other algorithms such as XGBoost or neural networks to compare performance.
Further fine-tuning of hyperparameters for better model accuracy.
Implement real-time fraud detection in financial applications.
