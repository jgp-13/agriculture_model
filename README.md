# 🌾 Soil-Based Crop Recommendation using Logistic Regression

This notebook explores how soil nutrient data can be used to predict the most suitable crop for a field using a **Logistic Regression** approach. The emphasis is on model building, feature evaluation, and data optimization — within a multi-class classification context.

---

## 📁 Dataset Details

The dataset used: `soil_measures.csv`, includes:

- **N** – Nitrogen content in soil  
- **P** – Phosphorous content  
- **K** – Potassium content  
- **ph** – Soil pH value  
- **crop** – Categorical label for the most suitable crop

The `crop` column was converted from `object` to `category` type to reduce memory usage.

---

## 🔍 Data Analysis & Preprocessing

- Basic structure and stats of the dataset were examined using `.info()` and `.describe()`.
- Distribution of crop types was assessed using `value_counts()`.
- Memory usage optimization was performed, showing a significant reduction after casting `crop` to a category.
- Feature matrix `X` and label vector `y` were created, followed by an 80/20 **train-test split**.
- **StandardScaler** was applied to normalize input features.

---

## 🧪 Model Training

A **Logistic Regression** classifier was trained **independently for each soil feature** to evaluate its predictive power:

- For each feature (`N`, `P`, `K`, `ph`), a separate model was trained.
- Predictions were made using only that feature.
- **F1 Score (weighted)** was used to evaluate performance.

This helped identify which individual soil metrics are most informative when predicting crops.

---

## 📌 Summary of Process

- ✅ Clean dataset with no missing values  
- 🔁 Feature scaling using `StandardScaler`  
- 📊 Model: Logistic Regression  
- 🧠 Evaluation: F1 Score (weighted)  
