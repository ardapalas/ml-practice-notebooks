# Algerian Forest Fires Prediction 🌲🔥

This project applies Machine Learning Regression techniques to predict the **Fire Weather Index (FWI)** using the Algerian Forest Fires dataset. The workflow includes extensive data cleaning, exploratory data analysis (EDA), handling multicollinearity, and comparing multiple regression models.

## 📊 Project Overview

The goal is to predict the risk of forest fires based on weather conditions. The project covers the end-to-end data science pipeline:
1.  **Data Loading & Cleaning:** Handling missing values, correcting data types, and encoding categorical variables.
2.  **Exploratory Data Analysis:** Visualizing correlations using heatmaps.
3.  **Feature Selection:** Removing highly correlated features (multicollinearity) such as DC, BUI, and DMC to prevent overfitting.
4.  **Preprocessing:** Standardization using `StandardScaler`.
5.  **Modeling:** Training and evaluating Linear, Lasso, Ridge, and ElasticNet regression models (including Cross-Validation).

## 📂 Dataset

The dataset includes 244 instances that regroup a period of two regions of Algeria: the Bejaia region located in the northeast of Algeria and the Sidi Bel-Abbes region located in the northwest of Algeria.

* **Target Variable:** `FWI` (Fire Weather Index)
* **Features Used:** Temperature, RH (Relative Humidity), Ws (Wind Speed), Rain, FFMC, ISI, etc.

## 🛠️ Technologies & Libraries

* **Python 3.x**
* **Pandas & NumPy:** Data manipulation and numerical operations.
* **Matplotlib & Seaborn:** Data visualization and correlation heatmaps.
* **Scikit-learn:** Data preprocessing, model training, and evaluation metrics.

## 📈 Model Performance

The models were evaluated using MAE (Mean Absolute Error), MSE (Mean Squared Error), and R2 Score.

| Model | MAE | R2 Score |
| :--- | :--- | :--- |
| **Linear Regression** | 0.54 | 98.4% |
| **Lasso Regression** | 0.70 | 98.3% |
| **Ridge Regression** | 0.56 | 98.4% |
| **ElasticNet** | 0.73 | 98.2% |

*Note: Cross-Validation (CV) versions of the models were also implemented to find the optimal alpha parameters.*

## 🚀 How to Run

1.  Clone the repository:
    ```bash
    git clone [https://github.com/yourusername/Algerian-Forest-Fires-Prediction.git](https://github.com/yourusername/Algerian-Forest-Fires-Prediction.git)
    ```
2.  Install the required libraries:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn
    ```
3.  Run the Jupyter Notebook:
    ```bash
    jupyter notebook AlgerianForestFires.ipynb
    ```

## 📝 Conclusion

The Linear and Ridge regression models performed exceptionally well on this dataset, achieving an R2 score of approximately **0.98**, demonstrating a strong linear relationship between the weather features and the Fire Weather Index.
