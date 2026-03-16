# 🚗 Car Price Prediction with Machine Learning

## 📌 Project Overview
This project builds and evaluates multiple machine learning models to predict **used car prices** using vehicle attributes such as year, mileage, manufacturer, and vehicle type.

The objectives are to:
- Identify key factors affecting vehicle prices
- Compare multiple regression models
- Select the best-performing model based on predictive accuracy and generalization

This project demonstrates an **end-to-end machine learning workflow**, including feature engineering, model comparison, cross-validation, and model interpretability.

---

# 📊 Dataset

The dataset contains used vehicle listings with the following features:

- `year`
- `age`
- `odometer`
- `manufacturer`
- `model`
- `paint_color`
- `type`

### Engineered Features
Additional variables were created to improve model performance:

- `log_odometer`
- `age_group`
- `mileage_group`
- target encoded variables:
  - `model_target_encoded`
  - `manufacturer_target_encoded`
  - `type_target_encoded`
  - `paint_color_target_encoded`

**Target Variable**

---

# ⚙️ Feature Engineering

### Derived Variables
- `age = current_year − year`
- `log_odometer` to normalize mileage distribution

### Feature Grouping
- `age_group`
- `mileage_group`

### Target Encoding
High-cardinality categorical variables were encoded using **target encoding** to capture relationships between categories and price.

---

# 🤖 Models Evaluated

| Model | Description |
|------|-------------|
| Linear Regression | Baseline regression model |
| Ridge Regression | Linear model with L2 regularization |
| Lasso Regression | Linear model with feature selection |
| Support Vector Regression (SVR) | Nonlinear regression model |

---

# 📈 Model Performance

### Baseline Models

| Model | Train R² | Test R² | Test RMSE | Test MAE | Overfitting |
|------|------|------|------|------|------|
| Linear Regression | 0.653 | 0.646 | 0.536 | 0.342 | 0.007 |
| Ridge Regression | 0.653 | 0.646 | 0.536 | 0.342 | 0.007 |
| Lasso Regression | 0.000 | -0.0001 | 0.901 | 0.725 | 0.000 |

---

### Advanced Model

| Model | Train R² | Test R² | Test RMSE | Test MAE | Overfitting |
|------|------|------|------|------|------|
| SVR | 0.779 | **0.685** | **0.506** | **0.296** | 0.094 |

SVR achieved the **highest predictive performance**, although it required longer training time compared to linear models.

---

# 🔁 Cross Validation

A **5-fold cross-validation** was performed on the Ridge Regression model.

| Metric | Value |
|------|------|
| Mean CV R² | **0.6528** |
| Standard Deviation | 0.0012 |
| Mean CV RMSE | **0.527** |
| RMSE Std Dev | 0.0025 |

The low standard deviation indicates **stable performance across folds**.

---

# 🏆 Final Model Comparison

| Model | Test R² | Test RMSE | Test MAE |
|------|------|------|------|
| **SVR** | **0.6850** | **0.5056** | **0.2960** |
| Ridge Regression | 0.6460 | 0.5360 | 0.3416 |
| Linear Regression | 0.6460 | 0.5360 | 0.3416 |
| Lasso Regression | -0.0001 | 0.9009 | 0.7249 |

### Best Performing Model
**Support Vector Regression (SVR)**

Reasons:
- Highest predictive accuracy
- Captures nonlinear relationships
- Lower prediction error (RMSE)

However, **Ridge Regression remains highly interpretable and computationally efficient.**

---

# 🔎 Feature Importance

Feature importance was analyzed using **Ridge regression coefficients**.

Top predictors influencing price:

1. `model_target_encoded`
2. `age`
3. `year`
4. `type_target_encoded`
5. `odometer`
6. `paint_color_target_encoded`

### Key Insight

- **Vehicle model** strongly affects resale value
- **Newer vehicles increase price**
- **Higher mileage reduces resale price**

---

# 📉 Key Insights

Main factors affecting used car prices:

1. Vehicle model
2. Vehicle age
3. Mileage
4. Vehicle type
5. Manufacturer reputation

Regularized linear models perform well when **features are correlated**, which explains Ridge Regression’s strong performance.

---

# 🛠 Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

---

# 📂 Project Structure
car-price-prediction/
│
├── data/
├── notebooks/
│ └── car_price_analysis.ipynb
├── images/
├── README.md
└── requirements.txt


---

# 🚀 Future Improvements

Potential improvements include:

- Gradient Boosting models (XGBoost / LightGBM)
- Hyperparameter tuning
- Additional feature engineering
- Geographic market features
- Deep learning regression models

These could further improve predictive accuracy.


---

# 🛠️ Installation & Usage

Follow these steps to set up and run the car price prediction project:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/car-price-prediction.git
   cd car-price-prediction
   ```

2. **Create and activate a virtual environment (optional but recommended):**
   ```bash
   python -m venv env
   source env/bin/activate   # On Windows: env\Scripts\activate
   ```

3. **Install required dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch the Jupyter Notebook:**
   ```bash
   jupyter notebook notebooks/car_price_analysis.ipynb
   ```

5. **Explore and run the notebook to reproduce the results and experiment with the models.**

*Ensure you have Python 3.7+ installed on your machine.*

---

# 📚 Conclusion

This project demonstrates a complete **machine learning regression workflow**, including:

- feature engineering
- model comparison
- cross-validation
- model interpretability

Both **regularized linear models and nonlinear SVR models** can effectively predict used car prices, with **SVR achieving the highest accuracy**.
However, **Ridge Regression remains highly interpretable and computationally efficient.**

---


Machine Learning Project focused on **regression modeling, feature engineering, and model evaluation**.