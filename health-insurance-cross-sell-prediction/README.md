# Health Insurance Cross-Sell Prediction

A machine learning project that predicts whether existing health insurance customers will be interested in purchasing vehicle insurance. Built using the [Kaggle Health Insurance Cross Sell Prediction](https://www.kaggle.com/datasets/anmolkumar/health-insurance-cross-sell-prediction) dataset.

## Problem Statement

An insurance company wants to identify which of its existing health insurance policyholders would also be interested in vehicle insurance. Predicting customer interest helps the company plan communication strategies, optimize outreach, and improve revenue.

## Dataset

The dataset contains information about customer demographics, vehicle details, and policy information with the following features:

- **Gender** - Male or Female
- **Age** - Age of the customer
- **Driving_License** - Whether the customer has a driving license (1: Yes, 0: No)
- **Region_Code** - Unique code for the customer's region
- **Previously_Insured** - Whether the customer already has vehicle insurance (1: Yes, 0: No)
- **Vehicle_Age** - Age of the vehicle
- **Vehicle_Damage** - Whether the vehicle was damaged in the past (1: Yes, 0: No)
- **Annual_Premium** - The amount the customer pays as premium in a year
- **Policy_Sales_Channel** - Anonymized code for the outreach channel
- **Vintage** - Number of days the customer has been associated with the company
- **Response** - Target variable (1: Interested, 0: Not interested)

## Approach

### 1. Data Preprocessing
- Dropped the `id` column
- Encoded categorical features (`Gender`, `Vehicle_Age`, `Vehicle_Damage`) using manual mapping
- Applied `StandardScaler` for feature scaling

### 2. Exploratory Data Analysis
- Correlation heatmap to identify relationships between features
- Key findings: `Previously_Insured` has a negative correlation (-0.34) and `Vehicle_Damage` has a positive correlation (0.35) with the target variable
- Visualized class distribution, response rates by insurance status, and vehicle damage impact

### 3. Handling Class Imbalance
- The target variable is highly imbalanced
- Applied **SMOTE** (Synthetic Minority Over-sampling Technique) to balance the training data

### 4. Model Training and Comparison
The following models were trained and evaluated:

| Model | Description |
|---|---|
| Logistic Regression | Baseline linear model |
| Decision Tree | Tree-based model with depth and leaf constraints |
| Random Forest | Ensemble of decision trees with balanced class weights |
| Support Vector Classifier | SVM with probability estimates and balanced class weights |

Models were compared on Accuracy, Precision, Recall, F1-Score, and ROC-AUC.

### 5. Final Model
Random Forest Classifier trained on SMOTE-resampled data was used as the final model, evaluated with a full classification report and confusion matrix.

## Tech Stack

- Python
- NumPy, Pandas
- Matplotlib, Seaborn
- Scikit-learn
- Imbalanced-learn (SMOTE)

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/health-insurance-cross-sell-prediction.git
   ```
2. Install dependencies:
   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn imbalanced-learn
   ```
3. Place `train.csv` and `test.csv` in the project directory (download from [Kaggle](https://www.kaggle.com/datasets/anmolkumar/health-insurance-cross-sell-prediction)).
4. Open and run the notebook:
   ```bash
   jupyter notebook HealthInsurancePrediction.ipynb
   ```

## Project Structure

```
.
├── HealthInsurancePrediction.ipynb   # Main notebook
├── train.csv                         # Training data (from Kaggle)
├── test.csv                          # Test data (from Kaggle)
└── README.md
```

## Results

The project includes a model comparison framework that evaluates four different classifiers. The `compare_models` function trains Logistic Regression, Decision Tree, Random Forest, and SVC on SMOTE-resampled data and compares them using a custom probability threshold.

### Random Forest Classifier (Final Model - SMOTE)

The Random Forest Classifier trained on SMOTE-balanced data was selected as the final model. Below are the results on the validation set (76,222 samples):

| Class | Precision | Recall | F1-Score | Support |
|---|---|---|---|---|
| 0 (Not Interested) | 0.91 | 0.91 | 0.91 | 66,880 |
| 1 (Interested) | 0.33 | 0.33 | 0.33 | 9,342 |

- **Overall Accuracy:** 83.76%
- **Weighted Avg F1-Score:** 0.84
- **Macro Avg F1-Score:** 0.62

### Key Observations

- The model achieves strong performance on the majority class (class 0) with 0.91 precision, recall, and F1-score.
- The minority class (class 1) remains challenging with 0.33 across all metrics despite SMOTE oversampling, reflecting the difficulty of the imbalanced classification problem.
- SMOTE improved minority class detection compared to training without it, but there is still room for improvement through hyperparameter tuning, threshold optimization, or trying other resampling strategies.
- The `compare_models` utility function in the notebook allows easy benchmarking of Logistic Regression, Decision Tree, Random Forest, and SVC side by side on metrics including Accuracy, Precision, Recall, F1-Score, and ROC-AUC.

## License

This project is open source and available under the [MIT License](LICENSE).
