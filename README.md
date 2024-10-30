# Arrhythmia Classification Using Machine Learning

## Overview

This project focuses on arrhythmia classification from ECG data using machine learning. Arrhythmia is an irregular heartbeat condition, diagnosed using ECG data. The primary objective of this project is to predict the presence of arrhythmia and classify it into one of the 12 possible categories. This classification task uses machine learning algorithms, including Random Forest, Support Vector Machines, and Neural Networks, to evaluate model performance and enhance diagnostic accuracy.

## Dataset

The dataset is sourced from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Arrhythmia) and contains:
- 452 samples with 279 features, representing various patient metrics and ECG-derived information.
- 16 classes, where 12 classes denote specific arrhythmia types, and the rest cover normal or other heart conditions.

### Key Features:
- Patient Attributes: Age, Sex, Height, Weight.
- ECG Measures: QRS duration, PR interval, QT interval, T interval, P interval, and Heart rate.
- Other Measurements: Vector angles for various ECG components and intrinsic deflection metrics.

## Data Preprocessing

1. **Handling Missing Data:** Filled missing values represented as `?` with the mean of the respective columns.
2. **Outlier Detection and Handling:** 
   - Outliers in height (values 780 and 608) replaced with reasonable estimates.
3. **Feature Scaling and Encoding:** Applied StandardScaler for numerical data, and encoded categorical features where needed.
4. **Dimensionality Reduction:** Used Principal Component Analysis (PCA) to reduce features from 279 to 121, retaining 98% of explained variance.

## Models Used

### 1. Random Forest
An ensemble model suited for multi-class classification, particularly effective for high-dimensional data. It uses multiple decision trees to reduce overfitting and enhance generalization.

### 2. Support Vector Machines (SVM)
SVM finds the optimal hyperplane to separate data points into distinct classes, making it robust to noise and outliers.

### 3. Neural Networks
Neural networks, with hidden layers, learn complex mappings between features and classes, providing flexibility for complex classification tasks.

## Model Evaluation

Each model was evaluated on accuracy, precision, recall, and F1-score. Key observations include:
- **Random Forest and Neural Networks**: Highest accuracy with training data, though they slightly underperformed on test data.
- **SVM**: Lower training accuracy but generalized better on test data.
- **Neural Network**: Achieved the highest test accuracy at 72% after hyperparameter tuning.

| Model               | Accuracy (Training) | Accuracy (Test) |
|---------------------|---------------------|-----------------|
| Random Forest       | 100%                | 70%            |
| Support Vector Machine | 60%             | 60%            |
| Neural Networks     | 100%                | 72%            |

## Conclusion

The best performance was achieved by Neural Networks with an accuracy of 72%, making it the preferred choice for this arrhythmia classification task.

## References

- Guvenir, H., Acar, B., Muderrisoglu, H., & Quinlan, R. (1998). Arrhythmia. UCI Machine Learning Repository. [DOI: 10.24432/C5BS32](https://doi.org/10.24432/C5BS32).

## Project Structure

- **data/** - Directory containing raw and preprocessed data files.
- **notebooks/** - Jupyter notebooks with data preprocessing, EDA, and model implementation.
- **models/** - Saved model files.
- **results/** - Evaluation metrics and visualizations.
- **README.md** - Project documentation.

---

This project was developed as part of the Data Analytics Engineering program at Northeastern University, under the guidance of Prof. Srinivasan Radhakrishnan.
