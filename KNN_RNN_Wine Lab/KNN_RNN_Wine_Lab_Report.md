# K-Nearest Neighbors (KNN) and Radius Neighbors (RNN) Classification using the Wine Dataset

## Student Information

**Name:** Sagar Bhetwal  
**Course:** Advanced Big Data and Data Mining 
**Instituition:** University of the Cumberlands 
**Instructor:** Dr. Satish Penmatsa
**Lab Title:** K-Nearest Neighbors (KNN) and Radius Neighbors (RNN) Classification  
**Date:** Feb 14, 2026  

---

## 1. Introduction

Machine learning classification algorithms rely heavily on how similarity between data samples is measured. Distance-based algorithms such as K-Nearest Neighbors (KNN) and Radius Neighbors (RNN) classify data points based on their proximity to neighboring samples in feature space. The effectiveness of these methods depends strongly on parameter selection and dataset characteristics.

This lab explores the performance of KNN and RNN classifiers using the Wine dataset available in the sklearn Python library. The dataset consists of chemical analysis results for wines derived from three different cultivars. Each sample contains multiple continuous features representing chemical properties such as alcohol content, magnesium level, and color intensity.

The objective of this experiment is to evaluate how parameter choices influence classification accuracy and to understand when each method may be preferable in practical applications.

---

## 2. Dataset Description

The Wine dataset contains:

- 178 samples
- 13 numerical features
- 3 target classes

Each class represents a different wine category. Since all features are continuous numeric values with different scales, preprocessing is required to ensure fair distance computation.

---

## 3. Methodology

### 3.1 Data Preparation

The following preprocessing steps were performed:

1. The Wine dataset was loaded using sklearn datasets.
2. Basic data exploration was conducted.
3. The dataset was divided into 80% training and 20% testing data.
4. Feature scaling was applied using StandardScaler.

Feature scaling is necessary because distance-based algorithms are sensitive to feature magnitude.

---

### 3.2 K-Nearest Neighbors (KNN)

The KNN classifier predicts class labels based on the majority class among the nearest neighbors. The parameter **k** determines how many neighbors participate in classification.

The following values were evaluated:

```
k = 1, 5, 11, 15, 21
```

For each value:
- The model was trained using training data.
- Predictions were made on test data.
- Accuracy was recorded.

---

### 3.3 Radius Neighbors (RNN)

The Radius Neighbors classifier selects neighbors based on distance instead of a fixed count. All samples within a defined radius contribute to classification.

The following radius values were tested:

```
radius = 350, 400, 450, 500, 550, 600
```

Accuracy was evaluated for each radius value.

---

## 4. Results and Visualization

Accuracy plots were generated for both models showing performance trends across parameter values.

### Observations

- Small k values in KNN increase sensitivity to noise.
- Larger k values provide more stable predictions.
- RNN performance varies significantly depending on radius size.
- Very small radius values may not include enough neighbors.
- Very large radius values may include samples from multiple classes.

---

## 5. Performance Comparison

The Wine dataset contains relatively well-separated classes, which explains why KNN produces consistent results. RNN is more sensitive because the number of neighbors changes dynamically.

KNN provides predictable performance, while RNN may be beneficial when dataset density varies across regions.

---

## 6. Discussion

The experiment demonstrates that algorithm performance depends heavily on parameter selection. Proper preprocessing and parameter tuning are essential for reliable machine learning models.

KNN is preferable when dataset density is uniform and stable performance is desired. RNN may perform better when data distribution varies significantly.

---

## 7. Conclusion

This lab has helped me demonstrate the influence of neighborhood definition on classification accuracy. KNN showed consistent performance due to fixed neighbor selection, while RNN required careful radius tuning. The results reinforce the importance of model evaluation and parameter optimization in machine learning workflows.

---

## 8. Technologies Used

- Python
- Jupyter Notebook
- NumPy
- Pandas
- Matplotlib
- Scikit-learn

---

## 9. References

- Pedregosa, F., et al. (2011). Scikit-learn: Machine Learning in Python.
- Scikit-learn Documentation: https://scikit-learn.org/
- UCI Machine Learning Repository: Wine Dataset.