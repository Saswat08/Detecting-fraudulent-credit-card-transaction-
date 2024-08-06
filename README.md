# Detecting-fraudulent-credit-card-transaction-
INTRODUCTION

In the digital era, the rise of online financial transactions has introduced both convenience and challenges, especially regarding security. Detecting and preventing fraudulent credit card transactions is one of the significant issues faced by consumers and financial institutions. Traditional rule-based methods often fail against the sophisticated tactics employed by fraudsters.
It investigates the application of machine learning (ML) techniques to identify fraudulent transactions. Machine learning leverages algorithms and statistical models to analyze complex data patterns, adapting to new and unseen data, making it more effective than traditional methods in detecting fraud. The report evaluates various ML models for their efficacy in distinguishing between legitimate and fraudulent transactions, detailing the methodology of data preparation, algorithm selection and tuning, and performance assessment using relevant metrics. Challenges such as data imbalance, model interpretability, and the evolving nature of fraudulent activities are also discussed.

Algorithms Used
1. Logistic Regression
•	Description: Logistic regression is a statistical method for analyzing a dataset in which there are one or more independent variables that determine an outcome. The outcome is measured with a dichotomous variable (in which there are only two possible outcomes). In this context, it is used to classify transactions as either fraudulent or non-fraudulent.
•	Implementation:

from sklearn.linear_model import LogisticRegression
clf = LogisticRegression()
clf.fit(X_train, y_train)
y_pred = clf.predict(X_test)

3. Decision Tree Classifier
   
•	Description: Decision tree is a supervised learning algorithm that is mostly used for classification problems. It works for both categorical and continuous input and output variables. In this context, it is used to classify transactions based on a series of decision rules inferred from the data features.

•	Implementation

from sklearn.tree import DecisionTreeClassifier
clf = DecisionTreeClassifier()
clf.fit(X_train, y_train)
y_pred = clf.predict(X_test)

4. Handling Imbalanced Data
   
Imbalanced data is a common issue in fraud detection as fraudulent transactions are much rarer compared to non-fraudulent ones. Two techniques were used to address this issue:

a. Undersampling

•	Description: This technique involves balancing the dataset by reducing the number of non-fraudulent transactions to match the number of fraudulent ones.
•	Implementation:

normal = data[data['Class'] == 0]
fraud = data[data['Class'] == 1]
normal_sample = normal.sample(n=473)
new_data = pd.concat([normal_sample, fraud], ignore_index=True)

b. SMOTE (Synthetic Minority Over-sampling Technique)
•	Description: SMOTE is an oversampling technique used to generate synthetic samples for the minority class (fraudulent transactions) to balance the dataset.

from imblearn.over_sampling import SMOTE
X_res, y_res = SMOTE().fit_resample(X, y)

3. Evaluation Metrics
   
The models were evaluated using the following metrics:

•	Accuracy: The ratio of correctly predicted instances to the total instances.
•	Precision: The ratio of correctly predicted positive observations to the total predicted positives.
•	Recall: The ratio of correctly predicted positive observations to the all observations in actual class.
•	F1 Score: The weighted average of Precision and Recall.


