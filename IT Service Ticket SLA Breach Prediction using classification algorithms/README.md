# IT Service Ticket SLA Breach Prediction

## Project Overview

This project uses Machine Learning to predict whether an IT service ticket will breach its SLA (Service Level Agreement).

The target column is:

- 0 = SLA was not breached
- 1 = SLA was breached

The goal is to identify tickets that are more likely to breach their SLA so they can be handled earlier.

## Models Used

We tested three classification models:

1. Decision Tree
2. Random Forest
3. AdaBoost

## Data Preparation

The data was prepared before model training.

A Scikit-learn pipeline was used so that preprocessing and the machine learning model stay together.

This also helps ensure that the same preprocessing is applied to training and test data.

## Model Tuning

We used 'GridSearchCV' with 5-fold cross-validation to tune the models.

F1-score was used for tuning because identifying SLA breaches (Class 1) is important.

### Decision Tree

The following parameters were tuned:

- Criterion
- Maximum depth
- Minimum samples required for splitting
- Minimum samples in a leaf
- Criteria

### Random Forest

The following parameters were tuned:

- Number of trees
- Maximum depth
- Maximum features
- Criterion

### AdaBoost

The following parameters were tuned:

- Number of estimators
- Learning rate

## Results

| Model| Test Accuracy | Class 1 Precision | Class 1 Recall | Class 1 F1 | Macro F1 |
|-------|-------------:|---:|---:|---:|---:|
| Decision Tree | 0.67 | 0.50 | 0.45 | 0.47 | 0.61 |
| Random Forest | 0.72 | 0.67 | 0.36 | 0.47 | 0.64 |
| AdaBoost      | 0.73 | 0.68 | 0.40 | 0.50 | 0.66 |

## Best Model

Among the models tested, AdaBoost performed the best overall.

It achieved:

- Accuracy: 73%
- Class 1 Precision: 68%
- Class 1 Recall: 40%
- Class 1 F1-score: 0.50
- Macro F1-score: 0.66

## What We Learned

The Decision Tree showed signs of overfitting because its training performance was much better than its testing performance.

Random Forest improved the overall accuracy compared with the Decision Tree.

AdaBoost gave the best overall results among the models tested.

However, the recall for SLA breaches (Class 1) was only 40%. This means the model still misses some tickets that actually breach their SLA.

For a real IT service environment, recall for SLA breaches may be especially important because missing a high-risk ticket can lead to a missed SLA.

## Final Conclusion

Among the models evaluated in this project, AdaBoost was selected as the preferred model because it achieved the highest test accuracy, Class 1 F1-score, and macro F1-score.

The model could be improved further before production use through additional feature engineering,and testing additional algorithms such as XGBoost.
