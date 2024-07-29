# Medical Dataset Analysis and Classification Project

## Overview

This project explores the application of unsupervised and supervised learning techniques on a medical dataset to classify records into different categories. The primary focus is on K-means clustering for unsupervised learning and K-Nearest Neighbors (KNN) for supervised learning.

## Dataset

- The dataset includes records with features relevant to medical conditions.
- There are no missing/null values.
- There is a class imbalance: 210 records under label AB (0) and 100 under label NO (1).

## Methods

### 1. Unsupervised Learning: K-means Clustering

- **Optimal Clusters**: Determined using the elbow method, optimal k = 2.
- **Kernel K-means**: Used polynomial, Gaussian, and sigmoid kernels to map data into higher dimensions.
  - **Best Results**: RBF kernel produced the best results with Adjusted Rand Index (ARI) = 0.28.
  - **Evaluation Metrics**: Silhouette Score and Davies-Bouldin Index used for performance assessment.

### 2. Supervised Learning: K-Nearest Neighbors (KNN)

- **Parameter Tuning**:
  - Best k values: 3 and 4.
  - Test split: 0.3 produced the best results.
- **Distance Metrics**: Tested Euclidean, Manhattan, and Chebyshev distances.
  - **Best Metric**: Euclidean distance with an accuracy of 85%.
- **Cross-Validation**: 10-fold cross-validation to analyze model generalizability.

### Exploratory Data Analysis (EDA)

- **Class Imbalance**: 35.48% difference in distribution of records between classes.
- **Outliers**: Identified using z-score; not removed due to lack of professional guidance.
- **Feature Engineering**:
  - Created a new column breaking down values into 5 grades.
  - Calculated Pelvic-Tilt Ratio (PTR) to categorize into anterior, posterior, and ideal pelvic tilt.

### Results

- **Feature Selection**:
  - Final features: ['pelvic_tilt', 'sacral_slope', 'pelvic_radius', 'spondylolisthesis_grade_median', 'ptr_category'].
  - Features scaled and dimensions reduced using PCA.
- **K-means Clustering**:
  - Simple model ARI score: 0.11.
  - RBF kernel ARI score: 0.28.
- **KNN Classification**:
  - Best accuracy with k=4 and Euclidean distance: 85%.

### Comparison of Models

| Model           | Metric        | Score   |
|-----------------|---------------|---------|
| K-means (RBF)   | ARI           | 0.28    |
| KNN             | Accuracy      | 85%     |
| Gaussian NB     | Accuracy      | 82%     |
| SVM             | Accuracy      | 84%     |

### Conclusion

The project demonstrates that supervised learning (KNN) achieves higher accuracy compared to unsupervised learning (K-means) for this medical dataset. Feature engineering and parameter tuning significantly improve model performance.

## References

1. [IJRS](https://www.ijsr.net/archive/v4i7/SUB156942.pdf)
2. [Nature](https://www.nature.com/articles/s41598-022-10358-x)
3. [Radiopaedia](https://radiopaedia.org/articles/spondylolisthesis-grading-system?lang=gb)
4. [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S1078817421001528)
5. [CiteSeerX](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=da73eea6ca9caa50da746f5744e65861c2ea8d35)
6. [IEOM](https://ieomsociety.org/proceedings/2022paraguay/384.pdf)
