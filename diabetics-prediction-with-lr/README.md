# 🏥 Diabetes Prediction with Machine Learning

This project is a Machine Learning model that predicts whether a patient has diabetes based on diagnostic measures using the Pima Indians Diabetes dataset. The project involves data analysis, data preprocessing, and classification algorithms.

## 🚀 About the Project

Diabetes is a widespread health issue worldwide. The objective of this study is to predict diabetes risk with high accuracy based on specific diagnostic measurements (glucose level, BMI, age, etc.). A **Support Vector Machine (SVM)** algorithm was used for classification in this project.

## 🛠 Technologies and Libraries

* **Python**
* **Pandas & NumPy:** Data manipulation and numerical operations.
* **Seaborn & Matplotlib:** Data visualization and correlation analysis.
* **Scikit-learn (sklearn):** Model building, data scaling, and performance evaluation.

## 📊 Methodology

1.  **Exploratory Data Analysis (EDA):**
    * Examined the general structure of the dataset (`head`, `describe`, `shape`).
    * Analyzed variable distributions and their relationship with the target variable (`Outcome`).
    * Visualized the distribution of the `Outcome` variable.

2.  **Data Preprocessing:**
    * **Standardization:** Used `StandardScaler` to standardize the data, removing scale differences between features to improve model performance.
    * Performed Train/Test split (`train_test_split`).

3.  **Modeling:**
    * Trained a **Support Vector Classifier (SVC)** algorithm using a *linear* kernel.
    * Fitted the model on the training data.

4.  **Model Evaluation:**
    * Measured success using the **Accuracy Score**.
    * Compared accuracy rates on both training and testing sets to check for overfitting/underfitting.

## 📈 Dataset Features

The dataset includes the following features:
* Pregnancies
* Glucose
* BloodPressure
* SkinThickness
* Insulin
* BMI (Body Mass Index)
* DiabetesPedigreeFunction
* Age

## 💻 Installation and Usage

To run this project locally:

```bash
git clone [https://github.com/yourusername/repository-name.git](https://github.com/yourusername/repository-name.git)
pip install pandas numpy seaborn matplotlib scikit-learn
