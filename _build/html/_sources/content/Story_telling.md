
# Data Stories on Datasets

We explore **two Kaggle datasets**—one for **classification** (Heart Disease) and another for **regression** (Avocado Prices). Each dataset is analyzed as follows:

1. **Problem Statement**  
2. **Understanding the Data**  
3. **Data Transformations & Exploration**  
4. **Visualizing Patterns**  
5. **Deciding on the Approach**  
6. **Data Sufficiency & Next Steps**

---

## Story 1: Heart Disease Classification

### 1. Problem Statement

We aim to predict the **presence of heart disease** using patient demographics and medical measurements.

**Dataset**: [Heart Disease UCI](https://www.kaggle.com/ronitf/heart-disease-uci)  
**File Name**: `heart.csv`

---

### 2. Understanding the Data

#### Columns Overview:

- `age`: Age in years  
- `sex`: 1 = male, 0 = female  
- `cp`: Chest pain type (4 categories)  
- `trestbps`: Resting blood pressure (mm Hg)  
- `chol`: Serum cholesterol (mg/dl)  
- `fbs`: Fasting blood sugar > 120 mg/dl (1 = true; 0 = false)  
- `restecg`: Resting ECG results (0, 1, 2)  
- `thalach`: Maximum heart rate achieved  
- `exang`: Exercise-induced angina (1 = yes; 0 = no)  
- `oldpeak`: ST depression induced by exercise relative to rest  
- `slope`: Slope of the peak exercise ST segment  
- `ca`: Number of major vessels (0–3)  
- `thal`: 3 = normal, 6 = fixed defect, 7 = reversible defect  
- `target`: 1 = heart disease present, 0 = no heart disease (binary target)

**Key Insight**: `target` is binary → This is a **classification problem**.

---

### 3. Data Transformations & Exploration

#### Python Code:
```python
import pandas as pd

# Load the dataset
heart_data = pd.read_csv('heart.csv')

# Explore dataset
print(heart_data.head())
print(heart_data.info())
print(heart_data.describe())

# Check for missing values
print(heart_data.isnull().sum())
```

**Observations**:  
- The dataset has no significant missing values.
- Features like `cp`, `thal`, `restecg` need encoding for modeling.

---

### 4. Visualizing Patterns

#### 4.1 Target Distribution:
```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.countplot(x='target', data=heart_data)
plt.title('Heart Disease Distribution (0 = No, 1 = Yes)')
plt.xlabel('Heart Disease')
plt.ylabel('Count')
plt.show()
```

#### 4.2 Correlation Heatmap:
```python
corr_matrix = heart_data.corr()

plt.figure(figsize=(10, 8))
sns.heatmap(corr_matrix, annot=True, cmap='coolwarm')
plt.title('Correlation Heatmap')
plt.show()
```

---

### 5. Deciding on the Approach

This is a **classification problem** because the target variable (`target`) is binary (0 or 1).

---

### 6. Data Sufficiency & Next Steps

- **Dataset Size**: ~303 rows, suitable for exploratory analysis.
- **Potential Models**: Logistic Regression, Random Forest, or XGBoost.
- **Evaluation Metrics**: Accuracy, Precision, Recall, F1, and ROC-AUC.
- **Validation**: Perform cross-validation for robustness.

---

## Story 2: Avocado Prices Regression

### 1. Problem Statement

Predict the **average price of avocados** in different US regions.

**Dataset**: [Avocado Prices](https://www.kaggle.com/datasets/neuromusic/avocado-prices)  
**File Name**: `avocado.csv`

---

### 2. Understanding the Data

#### Columns Overview:

- `Date`: Observation date  
- `AveragePrice`: Average price of a single avocado (target variable)  
- `Total Volume`: Total number of avocados sold  
- `type`: Avocado type (conventional or organic)  
- `year`: Year of observation  
- `region`: Region of observation  
- Size-specific columns: `4046`, `4225`, `4770` (PLU codes for specific avocado sizes)

**Key Insight**: `AveragePrice` is a **continuous variable** → This is a **regression problem**.

---

### 3. Data Transformations & Exploration

#### Python Code:
```python
import pandas as pd

# Load the dataset
avocado_data = pd.read_csv('avocado.csv')

# Explore dataset
print(avocado_data.head())
print(avocado_data.info())
print(avocado_data.describe())

# Check for missing values
print(avocado_data.isna().sum())
```

**Observations**:  
- Convert `Date` to datetime format.
- Encode `type` and `region` as categorical features.

---

### 4. Visualizing Patterns

#### 4.1 Price Distribution:
```python
sns.histplot(data=avocado_data, x='AveragePrice', kde=True)
plt.title('Price Distribution')
plt.xlabel('Price')
plt.ylabel('Count')
plt.show()
```

#### 4.2 Price by Type:
```python
sns.boxplot(data=avocado_data, x='type', y='AveragePrice')
plt.title('Price by Avocado Type')
plt.xlabel('Type')
plt.ylabel('Price')
plt.show()
```

#### 4.3 Correlation Heatmap:
```python
numerical_cols = ['AveragePrice', 'Total Volume', '4046', '4225', '4770']
corr_matrix = avocado_data[numerical_cols].corr()

plt.figure(figsize=(8, 6))
sns.heatmap(corr_matrix, annot=True, cmap='coolwarm')
plt.title('Correlation Heatmap')
plt.show()
```

---

### 5. Deciding on the Approach

This is a **regression problem** because the target variable (`AveragePrice`) is continuous.

---

### 6. Data Sufficiency & Next Steps

- **Dataset Size**: ~18,000 rows, suitable for regression modeling.
- **Potential Models**: Linear Regression, Random Forest, or XGBoost.
- **Evaluation Metrics**: RMSE, MAE, and R².
- **Validation**: Perform train-test split and cross-validation for robust results.

---

# Conclusion

We explored two datasets:

1. **Heart Disease** (Classification):  
   - Target: `target` (0 or 1)  
   - Suggested models: Logistic Regression, Random Forest.  

2. **Avocado Prices** (Regression):  
   - Target: `AveragePrice` (continuous)  
   - Suggested models: Linear Regression, Random Forest.

### Common Workflow:
1. Understand the dataset (features, target variable).  
2. Clean and preprocess the data (missing values, encoding).  
3. Visualize patterns and correlations.  
4. Choose the correct approach (classification or regression).  
5. Validate results using appropriate metrics.

---


