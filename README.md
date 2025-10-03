# Data Science Certificate Program – Bar-Ilan University  
## Product Demand Prediction for Inventory Management in an Indian Restaurant

### Overview
This project analyzes online order data from a single Indian restaurant in order to identify which product combinations (frequent baskets of items) are most common and to predict ordering patterns for the following three days.  
Using **Apriori algorithms for frequent itemset mining**, feature engineering, and machine learning models (Logistic Regression, Random Forest, Gradient Boosting, AdaBoost), the goal is to support **inventory management decisions** by anticipating short-term demand.

---

### Data
- Online orders: product-level transactions collected from the restaurant’s ordering system  
- Product prices: used to evaluate basket composition and revenue impact  
- Calendar data: weekdays, months, holidays  
- Weather data: daily min/avg/max temperatures for contextual features  

**Model inputs:**  
- Cleaned and merged flat table including order features, weather, and calendar variables  
- Engineered features such as lags, ratios, and dummy variables  

---

### Method
- Built a unified **flat table** with SQL to merge and organize inputs  
- **Exploratory Data Analysis (EDA):** examined distributions and correlations, handled missing values/outliers, removed irrelevant or duplicate records, and used R to test correlations and significance across features  
- **Feature engineering** to derive meaningful predictors  
- Model development and comparison: Logistic Regression, Random Forest, Gradient Boosting, AdaBoost  
- **Hyperparameter tuning** via Grid Search  
- Evaluation with AUC, Accuracy, Precision, Recall  

---

### Results
- **Best performing model:** AdaBoost  
- **Test performance:** AUC ≈ 0.80, balanced performance across metrics  
- Frequent product combinations successfully identified using Apriori, supporting classification features  
- EDA revealed strong correlations between weather, calendar effects, and ordering behavior  
- Qualitative examples and detailed tables are provided in the PDF report  

---

### Repository Structure
