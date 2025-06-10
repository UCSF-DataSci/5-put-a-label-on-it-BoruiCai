# Assignment 5: Health Data Classification Results

This file contains your manual interpretations and analysis of the model results from the different parts of the assignment.

## Part 1: Logistic Regression on Imbalanced Data

### Interpretation of Results

In this section, provide your interpretation of the Logistic Regression model's performance on the imbalanced dataset. Consider:

- Which metric performed best and why?
- Which metric performed worst and why?
- How much did the class imbalance affect the results?
- What does the confusion matrix tell you about the model's predictions?

The best performing metric is AUC(0.908), This shows the model is good at predicting between positive and negative cases.
The worst performing metric is Recall(0.301),could be the model missed many true disease cases.
The imbalance_impact_score: 0.56, which affects the results a lot, the low recall indicates the model is biased
The model rarely predicts false positives but frequently misses actual positive cases


## Part 2: Tree-Based Models with Time Series Features

### Comparison of Random Forest and XGBoost

In this section, compare the performance of the Random Forest and XGBoost models:

- Which model performed better according to AUC score?
- Why might one model outperform the other on this dataset?
- How did the addition of time-series features (rolling mean and standard deviation) affect model performance?

XGBoost performed better, with AUC of 0.9953, compared to 0.9735 for Random Forest.
XGBoost typically performs better on structured/tabular data because it uses gradient boosting
Incorporating rolling statistics of heart rate added valuable temporal context to the model. These features may have captured physiological variation patterns associated with the presence of disease.

## Part 3: Logistic Regression with Balanced Data

### Improvement Analysis

In this section, analyze the improvements gained by addressing class imbalance:

- Which metrics showed the most significant improvement?
- Which metrics showed the least improvement?
- Why might some metrics improve more than others?
- What does this tell you about the importance of addressing class imbalance?


The most notable improvement was in recall, which increased by 183.72%. This indicates that after balancing the dataset, the model became much better at identifying true positive cases.

However, precision dropped by 55.24%, and AUC slightly decreased by 3.30%. Accuracy also declined by 14.06%, likely because the balanced model increased false positives in order to achieve higher recall.

SMOTE generates synthetic samples for the minority class, allowing the model to learn more effectively how to detect positive cases, thus improving recall. However, this also leads to more false positives, which reduces both precision and overall accuracy.

In the healthcare domain, where missing positive cases can have serious consequences, addressing class imbalance is critical. Although metrics like precision and accuracy may decline, the gain in recall is often more meaningful, especially when it comes to early disease detection.

## Overall Conclusions

Summarize your key findings from all three parts of the assignment:

- What were the most important factors affecting model performance?
- Which techniques provided the most significant improvements?
- What would you recommend for future modeling of this dataset?

Class imbalance led to high initial accuracy but low recall in the logistic regression model.

Using SMOTE to balance the dataset significantly improved recall, enabling the model to identify disease cases more effectively.

It is essential to check for and address class imbalance before interpreting model performance.
