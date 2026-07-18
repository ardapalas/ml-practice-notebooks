# Car Evaluation Prediction using Decision Tree 🚗🌳

This project builds a **Decision Tree Classifier** to predict the acceptability of a car based on various features such as buying price, maintenance cost, safety, and capacity. The workflow includes data preprocessing, ordinal encoding, hyperparameter tuning, and tree visualization.

## 📊 Project Overview

The goal is to classify cars into one of four categories: `unacc` (unacceptable), `acc` (acceptable), `good`, or `vgood` (very good).

**Key Steps:**
1.  **Data Preprocessing:** Handling categorical variables using **Ordinal Encoding** (mapping 'low', 'med', 'high', 'vhigh' to numerical values).
2.  **Model Training:** Building a baseline Decision Tree Classifier.
3.  **Evaluation:** Using Accuracy Score, Confusion Matrix, and Classification Report.
4.  **Optimization:** Using `GridSearchCV` to tune hyperparameters (criterion, splitter, max_depth).
5.  **Visualization:** Plotting the decision tree structure.

## 📂 Dataset Features

The dataset consists of 1727 rows with the following attributes:

* **buying price:** vhigh, high, med, low.
* **maintenance cost:** vhigh, high, med, low.
* **number of doors:** 2, 3, 4, 5more.
* **number of persons:** 2, 4, more.
* **lug_boot:** small, med, big.
* **safety:** low, med, high.
* **class (Target):** unacc, acc, good, vgood.

## 🛠️ Technologies Used

* **Python 3.x**
* **Pandas & NumPy:** Data manipulation.
* **Scikit-learn:** Modeling, Encoding, GridSearch, and Evaluation metrics.
* **Matplotlib & Seaborn:** Visualization.

## 📈 Model Performance

The model performed exceptionally well on the test data.

| Metric | Score |
| :--- | :--- |
| **Base Model Accuracy** | ~95.6% |
| **GridSearch Best Accuracy** | ~95.5% |

### Confusion Matrix Insights
The model shows high precision and recall, particularly for the 'unacc' class, which constitutes the majority of the dataset.

## 🔍 Hyperparameter Tuning

`GridSearchCV` was used to find the optimal parameters to prevent overfitting:
* **Criterion:** Gini, Entropy, Log_loss
* **Splitter:** Best, Random
* **Max Depth:** [8, 9, 10, None]
* **Max Features:** Sqrt, Log2, None

**Best Parameters Found:**
```python
{'criterion': 'gini', 'max_depth': 10, 'max_features': None, 'splitter': 'random'}
