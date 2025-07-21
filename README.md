# 🏡 Real Estate Price Prediction using Multiple Regression Models

This project aims to predict housing prices based on various property features and compare the performance of multiple regression models using R-squared and RMSE metrics.

---

## 📊 Objective

The goal is to:
- Explore feature relationships with house prices
- Train and compare several regression models
- Identify the best-performing model(s) using evaluation metrics like R² and RMSE

---

## 🛠️ Tools & Technologies
- **Python**: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`
- **Jupyter Notebook**: For analysis and model training

---

## 🗃️ Dataset Description

Each row represents a house listing with the following features:

| Feature | Description |
|---------|-------------|
| `Square_Feet` | Total built-up area |
| `Num_Bedrooms` | Number of bedrooms |
| `Num_Bathrooms` | Number of bathrooms |
| `Num_Floors` | Total floors |
| `Year_Built` | Year of construction |
| `Has_Garden`, `Has_Pool` | Binary indicators for amenities |
| `Garage_Size` | Capacity of garage |
| `Location_Score` | Neighborhood quality score |
| `Distance_to_Center` | Distance to city center (km) |
| `Price` | Target variable (house price) |

---

## 🔍 Exploratory Data Analysis

### 🔥 Correlation Heatmap

![Correlation Heatmap](./correlation_heatmap.png)

Key Observations:
- `Square_Feet` and `Num_Bedrooms` have the strongest positive correlation with `Price` (0.56).
- `Year_Built` has moderate correlation (0.42).
- Features like `Garage_Size`, `Has_Garden`, and `Distance_to_Center` show weak correlation individually.

---

## 🧠 Models Trained & Evaluated

The following regression models were trained:
- Linear-based:
  - `SGDRegressor`
  - `ElasticNet`
  - `Ridge`
  - `Lasso`
- Tree-based:
  - `DecisionTreeRegressor`
  - `RandomForestRegressor`
- Distance-based:
  - `KNNRegressor`

---

## 📈 Model Performance – R² Score

<img width="990" height="390" alt="image" src="https://github.com/user-attachments/assets/20799cd5-0b36-4723-9c9e-40572968037f" />


- **Best performers**: `SGD`, `ElasticNet`, `Ridge`, and `Lasso` all achieved **R² ≈ 0.97**
- Tree-based and KNN models underperformed in comparison

---

## 📉 Model Performance – RMSE

<img width="990" height="390" alt="image" src="https://github.com/user-attachments/assets/180463c5-0bc7-45d7-b610-bc19f922597c" />


- **Lowest RMSE**:
  - `ElasticNet`: ~21985
  - `Lasso`: ~21985
  - `SGD`: ~21993
- **Worst RMSE**: `KNN` (~88,946), `DecisionTree` (~70,313)

---

## ✅ Conclusions

- **Linear models (especially regularized ones)** perform best for this dataset
- Features like `Square_Feet`, `Bedrooms`, and `Year_Built` are key price indicators
- Tree-based and KNN models may overfit or underfit due to limited signal in some features

---
