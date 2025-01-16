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

---

These metrics are the foundation for evaluation measures such as **Precision**, **Recall**, **Accuracy**, and **F1 Score**.
