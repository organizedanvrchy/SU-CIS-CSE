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

  Where:
    - **SS_res**: Residual sum of squares, representing the sum of squared differences between the actual and predicted values.<br>
    SS_res = Σ(yᵢ - ŷᵢ)²
    
    - `yᵢ`: Actual value.
    - `ŷᵢ`: Predicted value.
    
    - **SS_tot**: Total sum of squares, representing the total variance in the actual values.<br>
    SS_tot = Σ(yᵢ - ȳ)²
    - `ȳ`: Mean of the actual values.
    
    - ### Interpretation
        - **R² = 1**: Perfect fit. The model explains 100% of the variance in the data.
        - **R² = 0**: The model explains none of the variance; it performs as poorly as predicting the mean of the data.
        - **R² < 0**: The model performs worse than a baseline model that predicts the mean.

    - ### Example Calculation
    
        - Consider the following data for actual (`yᵢ`) and predicted (`ŷᵢ`) values:
            
            | **Data Point** | **Actual (yᵢ)** | **Predicted (ŷᵢ)** |
            |----------------|------------------|---------------------|
            | 1              | 3                | 2.8                 |
            | 2              | 5                | 5.3                 |
            | 3              | 7                | 6.9                 |
            | 4              | 9                | 8.7                 |
    
        - #### Step 1: Compute SS_res<br>
          SS_res = Σ(yᵢ - ŷᵢ)² = (3 - 2.8)² + (5 - 5.3)² + (7 - 6.9)² + (9 - 8.7)² = 0.04 + 0.09 + 0.01 + 0.09 = 0.23
        - #### Step 2: Compute SS_tot<br>
          Mean (ȳ) = (3 + 5 + 7 + 9) / 4 = 6 SS_tot = Σ(yᵢ - ȳ)² = (3 - 6)² + (5 - 6)² + (7 - 6)² + (9 - 6)² = 9 + 1 + 1 + 9 = 20
        - #### Step 3: Compute R²<br>
          R² = 1 - (SS_res / SS_tot) = 1 - (0.23 / 20) = 1 - 0.0115 ≈ 0.9885 (98.85%)


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

---

# Confusion Matrix Overview
The confusion matrix is a key concept in evaluating the performance of classification models. Below is a summary of its components and layout.

## Definitions

| Metric               | Description                                                                                       |
|----------------------|---------------------------------------------------------------------------------------------------|
| **True Positive (TP)** | Correctly predicted positive cases. The model predicts "Positive" when the actual label is "Positive." |
| **True Negative (TN)** | Correctly predicted negative cases. The model predicts "Negative" when the actual label is "Negative." |
| **False Positive (FP)** | Incorrectly predicted positive cases (Type I Error). The model predicts "Positive" when the actual label is "Negative." |
| **False Negative (FN)** | Incorrectly predicted negative cases (Type II Error). The model predicts "Negative" when the actual label is "Positive." |
| **Condition Positive (P)** | Total actual positive cases in the dataset. \( P = TP + FN \) |
| **Condition Negative (N)** | Total actual negative cases in the dataset. \( N = TN + FP \) |

## Confusion Matrix Layout

|                   | **Predicted Positive** | **Predicted Negative** |
|-------------------|-------------------------|-------------------------|
| **Actual Positive** | True Positive (TP)      | False Negative (FN)     |
| **Actual Negative** | False Positive (FP)     | True Negative (TN)      |

## Confusion Matrix Example

Consider a binary classification problem with the following results:

|                   | **Predicted Positive** | **Predicted Negative** |
|-------------------|-------------------------|-------------------------|
| **Actual Positive** | 50                      | 10                      |
| **Actual Negative** | 5                       | 35                      |

### Components:
- **True Positive (TP)** = 50  
  The model correctly identified 50 actual positives as positive.
  
- **False Negative (FN)** = 10  
  The model failed to identify 10 actual positives, predicting them as negative.
  
- **False Positive (FP)** = 5  
  The model incorrectly identified 5 actual negatives as positive.
  
- **True Negative (TN)** = 35  
  The model correctly identified 35 actual negatives as negative.

### Metric Calculations:

1. Accuracy = (TP + TN) / (TP + TN + FP + FN) Accuracy = (50 + 35) / (50 + 35 + 5 + 10) = 85 / 100 = 0.85 (85%)
2. Precision = TP / (TP + FP) Precision = 50 / (50 + 5) = 50 / 55 ≈ 0.91 (91%)
3. Recall = TP / (TP + FN) Recall = 50 / (50 + 10) = 50 / 60 ≈ 0.83 (83%)
4. F1 = 2 * (Precision * Recall) / (Precision + Recall) F1 = 2 * (0.91 * 0.83) / (0.91 + 0.83) F1 ≈ 2 * 0.7553 / 1.74 ≈ 0.867 (87%)
5. Specificity = TN / (TN + FP) Specificity = 35 / (35 + 5) = 35 / 40 = 0.875 (87.5%)

### Summary of Metrics for the Example:

| Metric         | Value    |
|----------------|----------|
| Accuracy       | 85%      |
| Precision      | 91%      |
| Recall         | 83%      |
| F1 Score       | 87%      |
| Specificity    | 87.5%    |
