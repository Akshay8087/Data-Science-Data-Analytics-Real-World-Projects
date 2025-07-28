# 📊 Customer Churn Prediction - End-to-End Data Science Project
![Python](https://img.shields.io/badge/Python-3.8+-blue.svg?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-black?logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-Scientific%20Computing-purple?logo=numpy)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange?logo=matplotlib)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Graphics-lightblue?logo=seaborn)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange?logo=scikit-learn)
![XGBoost](https://img.shields.io/badge/XGBoost-Gradient%20Boosting-red?logo=python)
![SMOTE](https://img.shields.io/badge/SMOTE-Imbalanced%20Data-teal?logo=python)
![Pickle](https://img.shields.io/badge/Pickle-Serialization-grey?logo=python)

## 📚 Table of Contents

- [✅ General Overview](#-general-overview)
- [📊 Business Objective](#-business-objective)
- [🧠 Machine Learning Workflow](#-machine-learning-workflow)
- [🧰 Tech Stack](#-tech-stack)
- [📦 Libraries and Dependencies](#-libraries-and-dependencies)
- [🧱 Code Structure](#-code-structure)
- [🧮 Functions and Classes](#-functions-and-classes)
- [🚀 Model Performance](#-model-performance)
- [🔄 Loops and Conditionals](#-loops-and-conditionals)
- [⚠️ Error Handling](#️-error-handling)
- [📊 Performance and Optimization](#-performance-and-optimization)
- [🧪 Testing and Validation](#-testing-and-validation)
- [📝 Documentation & Comments](#-documentation--comments)
- [📎 Recommendations](#-recommendations)
- [📁 Output Artifacts](#-output-artifacts)
- [🛠️ How to Run](#️-how-to-run)


## ✅ General Overview

This project demonstrates a complete data science pipeline to **predict customer churn** for a telecommunications company. The aim is to develop a classification model that identifies customers who are at high risk of leaving the service, enabling proactive retention strategies.


## 📊 Business Objective

Customer churn can lead to significant revenue loss. By predicting churn in advance, businesses can take corrective measures such as providing personalized offers or improving customer service.

This predictive model helps the business:
- Identify high-risk customers
- Reduce churn rate
- Improve customer satisfaction and profitability
---

## 🧠 Machine Learning Workflow
<img width="2816" height="720" alt="Image" src="https://github.com/user-attachments/assets/8bf4558a-aa8a-4f63-b584-9cf35bf77498" />

---
**Input and Output:**

- **Input:**  
  A CSV file: `WA_Fn-UseC_-Telco-Customer-Churn.csv` containing customer demographics, services, and account info.
  
- **Output:**  
  - `Customer_churn_model.pkl`: Trained XGBoost classification model.  
  - `encoder.pkl`: LabelEncoder object used to transform categorical features.

---

## 🧰 Tech Stack

- **Languages**: Python (pandas, numpy)
- **Visualization**: Matplotlib, Seaborn
- **Modeling**: Scikit-learn, XGBoost
- **Imbalance Handling**: SMOTE (imblearn)
- **Serialization**: Pickle

---

## 📦 Libraries and Dependencies

| Library | Purpose |
|--------|---------|
| `pandas`, `numpy` | Data manipulation and numerical computations |
| `matplotlib.pyplot`, `seaborn` | Data visualization |
| `imblearn.over_sampling.SMOTE` | Handle class imbalance |
| `sklearn.preprocessing.LabelEncoder` | Encode categorical variables |
| `sklearn.model_selection` | Data splitting and hyperparameter tuning |
| `sklearn.tree.DecisionTreeClassifier` | Baseline classification model |
| `sklearn.ensemble.RandomForestClassifier` | Ensemble learning model |
| `xgboost.XGBRFClassifier` | Final XGBoost model |
| `sklearn.metrics` | Model evaluation metrics |
| `pickle` | Save models to disk |
| `warnings` | Suppress warnings |

- ✅ No unused imports detected.
- ✅ All libraries are utilized effectively.
- ⚠️ No unnecessary imports present.
---

## 🧱 Code Structure

The script is well-structured, reflecting the data science lifecycle:
1. **Setup**: Import libraries and load dataset  
2. **Data Cleaning**: Handle data types and remove irrelevant columns  
3. **EDA**: Visualizations of numerical and categorical variables  
4. **Feature Engineering**: Label encoding and SMOTE balancing  
5. **Model Training**: Train/test split, train three models  
6. **Evaluation**: Accuracy, confusion matrix, classification report  
7. **Model Saving**: Save best model and encoder using pickle

The use of Jupyter Notebook markdown cells provides good readability.

---

## 🧮 Functions and Classes

### Defined Helper Functions:

```python
def plot_histogram(df, column_name):
    """
    Plot histogram with KDE, mean, and median lines.
 """
```


✅ Both functions are documented with docstrings.

---

# 🚀 Model Performance

### Classification Models and Their Performance:

| Model            | Accuracy |
|------------------|----------|
| Decision Tree    | 80.34%   |
| Random Forest    | 81.48%   |
| **XGBoost (Final)** | **82.33%** |

### Final Model: XGBoost Classifier

#### Confusion Matrix:

|                | Predicted No | Predicted Yes |
|----------------|--------------|----------------|
| **Actual No**  | 1307         | 181            |
| **Actual Yes** | 169          | 257            |

#### Classification Report:

| Class         | Precision | Recall | F1-Score | Support |
|---------------|-----------|--------|----------|---------|
| No Churn (0)  | 0.89      | 0.88   | 0.88     | 1488    |
| Churn (1)     | 0.59      | 0.60   | 0.60     | 426     |
| **Overall**   | **0.82**  | **0.82** | **0.82** | **1914** |

✅ **XGBoost chosen for deployment due to highest test accuracy.**


---

# 🔄 Loops and Conditionals

- A `for` loop is used to print unique values of categorical features.
- Logic is efficient, readable, and avoids deep nesting.

---

# ⚠️ Error Handling

- Includes `ValueError` handling in custom plotting functions.
- ⚠️ **Missing try-except blocks for file I/O operations.**
  > 🛠️ Recommended for production-grade robustness.

---

# 📊 Performance and Optimization

- Efficient libraries (`pandas`, `numpy`) are used for all computations.
- `GridSearchCV` helps with optimal hyperparameter tuning.
  > 💡 Consider `RandomizedSearchCV` for faster execution on larger datasets.

---

# 🧪 Testing and Validation

- ❌ No unit testing implemented.
- ✅ Validation is done using a proper **train-test split**, which ensures fair evaluation on unseen data.

---

# 📝 Documentation & Comments

- ✅ Markdown cells are used effectively in Jupyter Notebook to explain each section.
- ✅ Inline comments clearly describe the purpose of important lines or operations.

---

# 📎 Recommendations

### ✅ Code Quality
- Refactor the notebook into modular functions like:
  - `load_data()`
  - `preprocess_data()`
  - `train_model()`
  - `evaluate_model()`

### ⚡ Performance
- Replace `GridSearchCV` with `RandomizedSearchCV` for quicker tuning when dataset grows.

### 🔧 Maintainability
- Add `try-except` blocks for file reading/writing.
- Include a `requirements.txt` file for easy dependency installation.

---

# 📁 Output Artifacts

- `Customer_churn_model.pkl` - Trained XGBoost model
- `encoder.pkl` - LabelEncoder object used for categorical transformation

---

```bash
📂 Project Structure
├── WA_Fn-UseC_-Telco-Customer-Churn.csv
├── Customer Churn.ipynb
├── Customer_churn_model.pkl
├── encoder.pkl
└── README.md
```

---
# 🛠️ How to Run

```bash
# Clone the repository
git clone https://github.com/Akshay8087/churn-prediction.git
```
```bash
# Navigate into the project folder
cd churn-prediction
```

```bash
# Install dependencies
pip install -r requirements.txt
```
```bash
# Run the script (if converted from notebook to script)
python churn_model.py
```



---

## 📬 Contact

**Author:** Akshay Rathod  
📧 Email: [akshayrathod8179@gmail.com](mailto:akshayrathod8179@gmail.com)  
💼 LinkedIn: [linkedin.com/in/akshayrathod](https://www.linkedin.com/in/akshayrathod)  
💻 GitHub: [github.com/Akshay8087](https://github.com/Akshay8087)


---

