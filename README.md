# Credit Card Fraud Detection

## Project Overview

This project evaluates machine-learning models for identifying fraudulent credit-card transactions. The analysis compares Logistic Regression and Decision Tree classifiers, with particular attention to fraud-class precision, recall, and F1-score.

Credit-card fraud detection is an imbalanced-classification problem. In the test set, only 123 of 71,202 transactions were fraudulent. Therefore, accuracy alone is not an appropriate measure of model quality.

## Business Problem

Financial institutions need to identify fraudulent transactions while minimizing disruption to legitimate customers. Two types of model error are especially important:

- **False negative:** A fraudulent transaction is classified as legitimate, potentially causing financial loss.
- **False positive:** A legitimate transaction is flagged as fraud, potentially creating customer friction and investigation costs.

The preferred model depends on the relative business cost of these errors.

## Models Evaluated

- Logistic Regression
- Decision Tree

## Model Performance

| Model | Accuracy | Fraud Precision | Fraud Recall | Fraud F1-score |
|---|---:|---:|---:|---:|
| Logistic Regression | 99.92% | 84.78% | 63.41% | 72.56% |
| Decision Tree | 99.93% | 71.09% | 73.98% | 72.51% |

## Results and Interpretation

Both models achieved accuracy above 99.9%. However, this result is largely influenced by the high number of legitimate transactions and should not be interpreted independently.

### Logistic Regression

Logistic Regression achieved fraud-class precision of 84.78% and recall of 63.41%. Its higher precision indicates that a larger proportion of the transactions it flagged as fraud were actually fraudulent. It is the stronger option when reducing false alerts is the main priority.

### Decision Tree

The Decision Tree achieved fraud-class precision of 71.09% and recall of 73.98%. Its higher recall indicates that it detected a larger proportion of the fraudulent transactions. It is the stronger option when reducing undetected fraud is the main priority.

### Model Comparison

The two models produced almost identical fraud-class F1-scores:

- Logistic Regression: 72.56%
- Decision Tree: 72.51%

The primary tradeoff is therefore between precision and recall. Logistic Regression generated more reliable fraud alerts, while the Decision Tree detected more of the actual fraud cases.

Based on the reported recall values, Logistic Regression detected approximately 78 of the 123 fraud cases, while the Decision Tree detected approximately 91. The Decision Tree therefore identified approximately 13 additional fraudulent transactions, although it also produced more false-positive alerts.

## Model Selection

The Decision Tree is the preferred recall-oriented model because it detected a greater proportion of fraudulent transactions. This choice is appropriate when the cost of missing fraud is greater than the cost of investigating additional alerts.

Logistic Regression remains the preferred precision-oriented model when minimizing false alerts and customer disruption is more important.

Accordingly, the final production decision should be based on the organization's fraud-loss tolerance, investigation capacity, and customer-experience requirements.

## Key Takeaways

- The test data is highly imbalanced, with only 123 fraud cases among 71,202 transactions.
- Accuracy above 99.9% does not, by itself, demonstrate strong fraud detection.
- Logistic Regression provides higher fraud precision.
- The Decision Tree provides higher fraud recall.
- The models have nearly identical fraud F1-scores.
- Selecting a model requires balancing undetected fraud against false alerts.

## Future Improvements

Future evaluation could include:

- Confusion matrices
- Precision-recall curves
- PR-AUC and ROC-AUC
- Cross-validation
- Probability-threshold optimization
- Decision-tree pruning and overfitting analysis
- Cost-sensitive model evaluation
ls are available.
