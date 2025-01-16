# Machine Learning Analysis

## Definitions

| Metric               | Description                                                                                       |
|----------------------|---------------------------------------------------------------------------------------------------|
| **True Positive (TP)** | Correctly predicted positive cases. The model predicts "Positive" when the actual label is "Positive." |
| **True Negative (TN)** | Correctly predicted negative cases. The model predicts "Negative" when the actual label is "Negative." |
| **False Positive (FP)** | Incorrectly predicted positive cases (Type I Error). The model predicts "Positive" when the actual label is "Negative." |
| **False Negative (FN)** | Incorrectly predicted negative cases (Type II Error). The model predicts "Negative" when the actual label is "Positive." |
| **Condition Positive (P)** | Total actual positive cases in the dataset. \( P = TP + FN \) |
| **Condition Negative (N)** | Total actual negative cases in the dataset. \( N = TN + FP \) |

## Confusion Matrix

Below is a typical confusion matrix layout for binary classification:

|                   | **Predicted Positive** | **Predicted Negative** |
|-------------------|-------------------------|-------------------------|
| **Actual Positive** | True Positive (TP)      | False Negative (FN)     |
| **Actual Negative** | False Positive (FP)     | True Negative (TN)      |

These metrics are the foundation for evaluation measures such as **Precision**, **Recall**, **Accuracy**, and **F1 Score**.

---

# Machine Learning Metrics
## 1. Classification Metrics
- **Accuracy**: Proportion of correctly classified samples.<br>
    Accuracy = (TP + TN) / (TP + TN + FP + FN)

- **Precision**: Proportion of true positive predictions out of total positive predictions.<br>
    Precision = TP / (TP + FP)

- **Recall (Sensitivity/True Positive Rate)**: Proportion of true positives out of actual positives.<br>
    Recall = TP / (TP + FN)

- **F1 Score**: Harmonic mean of precision and recall.<br>
    F1 = 2 * (Precision * Recall) / (Precision + Recall)

- **ROC-AUC (Receiver Operating Characteristic - Area Under Curve)**: Measures the trade-off between the true positive rate and false positive rate.

- **Log Loss (Cross-Entropy Loss)**: Penalizes incorrect probabilities assigned to classes.


## 2. Regression Metrics
- **Mean Absolute Error (MAE)**: Average of absolute differences between predicted and actual values.<br>
    MAE = (1/n) * Σ|yi - yi_hat|

- **Mean Squared Error (MSE)**: Average of squared differences between predicted and actual values.<br>
    MSE = (1/n) * Σ(yi - yi_hat)²

- **Root Mean Squared Error (RMSE)**: Square root of MSE.<br>
    RMSE = √MSE

- **R² (Coefficient of Determination)**: Proportion of variance explained by the model.<br>
    R² = 1 - (SS_res / SS_tot)

## 3. Clustering Metrics
- **Silhouette Score**: Measures how similar a data point is to its cluster compared to other clusters. <br>
    Silhouette = (b - a) / max(a, b) 
  where:
- `a` = intra-cluster distance
- `b` = nearest-cluster distance

- **Adjusted Rand Index (ARI)**: Measures similarity between predicted and true cluster assignments, adjusting for chance.

- **Davies-Bouldin Index**: Measures average similarity ratio of intra-cluster distances to inter-cluster distances (lower is better).

## 4. Ranking Metrics
- **Mean Average Precision (MAP)**: Average precision across multiple queries.

- **Normalized Discounted Cumulative Gain (NDCG)**: Assesses ranking quality by assigning higher importance to correctly ranked items at the top.

## 5. Multi-Class/Imbalanced Metrics
- **Macro Averaging**: Averages metric scores equally across classes.
- **Micro Averaging**: Averages metric scores considering class frequency.
- **Weighted Averaging**: Averages metric scores weighted by class frequency.
