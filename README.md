# 🛍️ Retail Sales Prediction – Rossmann Case Study

**📌 Mid-Course Assessment – Machine Learning Case Study**  
**🔧 Project Type:** Regression  
**👤 Contributor:** Jatin Kanyan  
**📂 Repository:** [GitHub Link to Project](#)

---

## 📚 Overview

Rossmann is a major European drugstore chain with over 3,000 stores. This project focuses on forecasting **daily sales for the next 6 weeks** using historical data for over 1,100 stores. The goal is to support better inventory, staff, and promotion planning at the store level.

---

## 🎯 Problem Statement

Managers need reliable predictions of daily sales that consider promotions, holidays, store characteristics, and local competition. This project aims to create a robust **regression model** to predict sales using features from both the store-level metadata and historical sales.

---

## 📂 Datasets Used

- `train.csv`: Historical daily sales data (~1 million records)
- `store.csv`: Store metadata (store type, promotions, competition)

---

## 🧠 Feature Engineering

- Extracted `Year`, `Month`, `Day`, and `WeekOfYear` from `Date`
- Transformed categorical features using one-hot encoding (e.g., `StoreType`, `Assortment`)
- Removed irrelevant or biased data:
  - Stores closed (`Open == 0`)
  - Entries with zero sales
- Imputed missing values using **median** for numeric columns
- Removed high-missing-value features: `Promo2Since`, `CompetitionOpenSinceYear`, etc.

---

## 📊 Exploratory Data Analysis

- **Sales** are highly correlated with the number of **Customers**
- **Promotions** have a strong positive impact on both sales and customer visits
- **Sunday** is the highest-grossing day, despite only 33 stores being open
- **StoreType A** is the most common and busiest, while **StoreType D** has the highest average cart value
- **School holidays** tend to increase sales, more than state holidays
- **Promo2** campaigns show negligible impact on sales
- **Competition distance** inversely impacts store performance

---

## 📈 Data Preprocessing

- Removed outliers in `Sales` using IQR method
- Converted `StoreType` and `Assortment` into dummies
- Scaled features using `MinMaxScaler`
- Split data into **training (70%)** and **testing (30%)**

---

## 🧪 Models & Evaluation

### 1️⃣ Linear Regression (OLS)

- **R² Score (Train/Test)**: 0.780 / 0.782
- **RMSE (Test)**: ~1152.99
- **MAPE (Test)**: ~14.23%

### 2️⃣ Lasso Regression (LARS)

- **R² Score (Train/Test)**: 0.7807 / 0.7823
- **RMSE (Test)**: ~1153.06
- **MAPE (Test)**: ~14.23%

### 3️⃣ Decision Tree Regressor

- **R² Score (Train/Test)**: 0.999 / 0.915
- **RMSE (Test)**: ~717.28
- **MAPE (Test)**: ~7.64%

📌 **Note:** Decision Tree shows excellent fit but might suffer from **overfitting**, as indicated by near-perfect train scores.

---

## 📌 Model Comparison

| Model              | Train Score | Test Score | Test RMSE | Test MAPE |
|-------------------|-------------|------------|-----------|-----------|
| Linear Regression | 0.78075     | 0.78239    | 1152.99   | 14.23%    |
| Lasso Regression  | 0.78073     | 0.78236    | 1153.06   | 14.23%    |
| Decision Tree     | 0.99999     | 0.91578    | 717.28    | 7.64%     |

---

## 🛠️ Tools & Technologies

- **Languages**: Python  
- **Libraries**: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `statsmodels`  
- **IDE**: Jupyter Notebook  
- **Version Control**: Git + GitHub  

---

## 🔍 Key Insights

1. **Customers & Sales** have the highest correlation.
2. **Promotions** significantly impact sales — but only run on weekdays.
3. **StoreType A** has high volume, **D** has high average spend.
4. **Promo2** isn't as effective as expected.
5. **School holidays** boost sales more than state holidays.
6. **Christmas week** sees a big spike in sales.
7. **Greater competition distance = better performance**
8. Removing closed stores and 0-sales rows improves model performance.

---

## 🚀 Future Enhancements

- Incorporate **XGBoost/LightGBM** for better model generalization
- Explore **time-series modeling** using Prophet/ARIMA
- Build a **Streamlit dashboard** for real-time predictions
- Perform **GridSearchCV** for hyperparameter tuning
- Implement **store-specific models** for granular insights

---

---

## 👋 Contact

📧 [JatinKanyan11@gmail.com]  




