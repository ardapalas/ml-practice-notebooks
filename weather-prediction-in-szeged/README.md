# 🌦️ Weather Prediction in Szeged (2006–2016) – Linear Regression Model

This project predicts **temperature (°C)** using historical weather data collected from Szeged, Hungary, between 2006 and 2016.  
It involves **data cleaning, exploratory data analysis (EDA), feature selection, scaling, and linear regression modeling**.

---

## 📊 Dataset

- **File:** `weatherHistory.csv`
- **Source:** [Kaggle – Weather History Dataset](https://www.kaggle.com/datasets/muthuj7/weather-dataset)
- **Columns:**
  - Temperature (°C)
  - Apparent Temperature (°C)
  - Humidity
  - Wind Speed (km/h)
  - Wind Bearing (degrees)
  - Visibility (km)
  - Pressure (millibars)
  - Precipitation Type (rain/snow)
  - Daily Summary
  - Timestamp (converted into year, month, day)

---

## ⚙️ Project Workflow

### 1. Data Preprocessing
- Converted timestamps into separate `year`, `month`, `day` columns.
- Removed unnecessary timezone and time-of-day details.
- Handled missing values (`Precip Type` had 517 NaN entries).
- Dropped non-numeric and redundant columns (`Apparent Temperature (C)`).

### 2. Exploratory Data Analysis (EDA)
- Explored variable distributions with histograms and boxplots.
- Examined relationships via scatter plots and correlation heatmaps.
- Found strong correlation between `Temperature (C)` and `Apparent Temperature (C)`.

#### 🔹 Example Visualizations
| Temperature Distribution | Correlation Heatmap |
|---------------------------|---------------------|
| ![Temperature Distribution](images/temperature_distribution.png) | ![Correlation Heatmap](images/correlation_heatmap.png) |

---

## 🧩 Feature Selection
After removing irrelevant and categorical variables, the features used were:
```
Humidity
Wind Speed (km/h)
Wind Bearing (degrees)
Visibility (km)
Loud Cover
Pressure (millibars)
```

---

## ⚙️ Data Scaling
- Used `StandardScaler` from `sklearn.preprocessing` to normalize features before model training.

---

## 🧠 Model Training
Algorithm: **Linear Regression**

```python
from sklearn.linear_model import LinearRegression
model = LinearRegression()
model.fit(X_train_scaled, y_train)
```

Data split: **80% training / 20% testing**

---

## 📈 Model Evaluation

| Metric | Result |
|--------|---------|
| **R² Score** | 0.45 |
| **MAE (Mean Absolute Error)** | 5.73 |
| **MSE (Mean Squared Error)** | 30.6 |

➡️ The model explains ~45% of the temperature variance.  
On average, predictions deviate by about **±5–6°C** — reasonable for a simple linear model.

---

## 📉 Prediction vs Actual Visualization

| Actual vs Predicted |
|----------------------|
| ![Prediction Plot](images/pred_vs_actual.png) |

---

## 💡 Insights
- **Humidity** shows strong negative correlation with temperature (r ≈ –0.63).  
- **Visibility** and **Pressure** have weaker influence.  
- **Apparent Temperature (C)** adds redundant information.  
- Linear regression captures part of the variance but struggles with **seasonal patterns**.

---

## 🚀 Future Improvements
- Encode `month` with sine/cosine transformation to capture **seasonality**:
  ```python
  df["month_sin"] = np.sin(2 * np.pi * df["month"]/12)
  df["month_cos"] = np.cos(2 * np.pi * df["month"]/12)
  ```
- Include encoded categorical features like `Precip Type`.
- Experiment with non-linear models:
  - `RandomForestRegressor`
  - `Polynomial Regression`
  - `XGBoost`

---

## 🧰 Requirements

```bash
pandas
numpy
matplotlib
seaborn
scikit-learn
```

Install with:
```bash
pip install -r requirements.txt
```

---

## 📁 Project Structure
```
weather-linear-regression/
│
├── data/
│   └── weatherHistory.csv
│
├── images/
│   ├── temperature_distribution.png
│   ├── correlation_heatmap.png
│   └── pred_vs_actual.png
│
├── Weather in Szeged 2006-2016 - ML.ipynb
├── requirements.txt
└── README.md
```

---

## ✨ Author
**Arda Palas**  
📧 ardapalas82@gmail.com
GitHub: [@ardapalas](https://github.com/ardapalas)

---

## 📝 License
This project is open-source and available under the **MIT License**.
