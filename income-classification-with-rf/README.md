# 💰 Income Classification Analysis

This is a data science project that predicts whether an individual's annual income exceeds $50,000 based on census data containing demographic and employment information.

## 🎯 Project Goal

The goal is to develop a classification model using Census Data to analyze income inequality or economic status. This project specifically focuses on handling categorical data and **Feature Engineering**.

## 🧰 Technologies

* **Python**
* **Pandas:** Dataframe management.
* **Seaborn & Matplotlib:** Comprehensive data visualization (Countplot, Heatmap, etc.).
* **Scikit-learn:** Data preprocessing and modeling tools.

## 🔍 Process and Methodology

### 1. Exploratory Data Analysis (EDA)
Visualized the impact of variables on income status:
* **Education vs. Income:** Analyzed how income levels change with education.
* **Age and Gender Distribution:** Examined which age groups and genders fall into the high-income category.
* **Marital Status:** Visualized the effect of relationship status on income.

### 2. Data Cleaning and Preprocessing
* Analyzed the dataset for missing or redundant values.
* **Label Encoding:** Converted categorical variables (Workclass, Education, Marital Status, Occupation, etc.) into numerical values so the model can process them.
* Performed correlation analysis (Heatmap) to examine relationships between features.

### 3. Modeling and Results
* Split the dataset into dependent (Income) and independent variables.
* Created training (`X_train`) and testing (`X_test`) sets.
* Trained the classification model and made predictions on the test set.
* Evaluated model performance using accuracy metrics.

## 📂 About the Dataset

The dataset (Adult Census Income) includes features such as:
* **Age, Workclass, Education**
* **Marital-status, Occupation, Relationship**
* **Race, Sex**
* **Capital-gain, Capital-loss**
* **Hours-per-week, Native-country**

## 🚀 How to Run

After installing the necessary libraries, run the `.ipynb` file to see the analysis steps.

```bash
pip install -r requirements.txt
# or manually
pip install pandas seaborn sklearn matplotlib
