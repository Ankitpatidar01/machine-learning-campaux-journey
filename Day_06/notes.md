# 📊 Univariate & Bivariate Analysis – Notes

---

## 🔹 Univariate Analysis

**Definition:**  
Univariate analysis focuses on analyzing **a single variable** to understand its distribution, central tendency, spread, and frequency.

### 🎯 Purpose
- Understand data distribution
- Detect outliers
- Summarize data
- Identify skewness

---

## 📌 Types of Univariate Analysis

### 1️⃣ Numerical Data

#### a) Histogram
- Shows frequency distribution of continuous data
- Helps identify skewness and spread

```python
plt.hist(df['Age'], bins=5)
plt.show()
```

#### b) Box Plot
- Shows median, quartiles, and outliers

```python
sns.boxplot(y=df['Salary'])
plt.show()
```

#### c) KDE Plot (Density Plot)
- Smooth representation of data distribution

```python
sns.kdeplot(df['Age'], fill=True)
plt.show()
```

#### d) Statistical Summary

```python
df['Age'].describe()
```

---

### 2️⃣ Categorical Data

#### a) Count Plot
- Shows frequency of categories

```python
sns.countplot(x='Gender', data=df)
plt.show()
```

#### b) Bar Plot
- Used for comparing category counts

```python
df['Gender'].value_counts().plot(kind='bar')
plt.show()
```

#### c) Pie Chart
- Shows percentage contribution

```python
df['Gender'].value_counts().plot(kind='pie', autopct='%1.1f%%')
plt.show()
```

---

## ✅ When to Use Univariate Analysis
- Initial data exploration
- Feature understanding
- Data cleaning

---

## 🔹 Bivariate Analysis

**Definition:**  
Bivariate analysis studies the **relationship between two variables** to understand correlation, comparison, or dependency.

### 🎯 Purpose
- Identify relationships
- Compare groups
- Measure correlation

---

## 📌 Types of Bivariate Analysis

### 1️⃣ Numerical vs Numerical

#### a) Scatter Plot
- Shows relationship and correlation

```python
plt.scatter(df['Age'], df['Salary'])
plt.show()
```

#### b) Line Plot
- Shows trend over ordered data

```python
plt.plot(df['Age'], df['Salary'], marker='o')
plt.show()
```

#### c) Correlation Heatmap
- Shows strength of relationship

```python
sns.heatmap(df[['Age','Salary']].corr(), annot=True)
plt.show()
```

---

### 2️⃣ Categorical vs Numerical

#### a) Box Plot
- Compares numerical distribution across categories

```python
sns.boxplot(x='Gender', y='Salary', data=df)
plt.show()
```

#### b) Bar Plot (Mean by Category)

```python
sns.barplot(x='Gender', y='Salary', data=df)
plt.show()
```

---

### 3️⃣ Categorical vs Categorical

#### Count Plot with Hue

```python
sns.countplot(x='Gender', hue='Age', data=df)
plt.show()
```

---

### 4️⃣ Pair Plot
- Shows all pairwise relationships

```python
sns.pairplot(df, hue='Gender')
```

---

## 🔁 Univariate vs Bivariate (Quick Comparison)

| Aspect | Univariate | Bivariate |
|-----|---------|-----------|
| Variables | One | Two |
| Goal | Distribution | Relationship |
| Example Plots | Histogram, Box | Scatter, Heatmap |
| Use Case | Data understanding | Pattern detection |

---

## 🧠 Exam / Interview Ready Lines

- **Univariate Analysis:** Analysis of a single variable to summarize and understand its characteristics.
- **Bivariate Analysis:** Analysis of two variables to identify relationships or comparisons between them.


# Feature Engineering Notes

## 1. Introduction to Feature Engineering
Feature Engineering is the process of using **domain knowledge** to extract features from raw data. These features are used to improve the performance of machine learning algorithms.



### Workflow:
1.  **Dataset Retrieval**
2.  **Data Processing & Wrangling**
3.  **Feature Extraction & Engineering**
4.  **Feature Scaling & Selection**
5.  **Modeling** (Machine Learning Algorithm)
6.  **Model Evaluation & Tuning**
7.  **Deployment & Monitoring**

> **Note:** The process is iterative. If the model is not satisfactory, you reiterate until performance improves.

---

## 2. Core Components
Feature Engineering is broadly divided into four main pillars:

* **Feature Transformation:** Handling missing values, categorical encoding, outlier detection, and scaling.
* **Feature Construction:** Creating new features from existing ones.
* **Feature Selection:** Choosing the most relevant features to reduce noise.
* **Feature Extraction:** Transforming raw data into numerical features (e.g., PCA, LDA).

---

## 3. Feature Transformation Techniques

### 3.1 Missing Value Imputation
* **Delete:** Remove rows or columns with missing values.
* **Fill:** Populate missing values using:
    * **Mean/Median:** For numerical data.
    * **Most Frequent Category (Mode):** For categorical data.

### 3.2 Handling Categorical Values
* **One-Hot Encoding:** Converts categorical data into binary (0 or 1) columns.
    * *Example:* For a feature "Animal" with values [Dog, Cat, Sheep], separate binary columns are created for each.



### 3.3 Outlier Detection
Outliers can change the Linear Regression line sharply. It is essential to detect and remove them before feeding data into an algorithm to ensure stability.

### 3.4 Feature Scaling (Standardization)
**Definition:** A technique to standardize independent features in the data into a fixed range.

**Why do we need it?**
Algorithms like **KNN** use Euclidean distance. If one feature (e.g., Salary: 88,000) has a much larger range than another (e.g., Age: 20), the distance calculation will be dominated by Salary.

**Standardization (Z-Score Normalization):**
Calculated using the formula:
$$x' = \frac{x_i - \mu}{\sigma}$$
* $\mu$ = Mean
* $\sigma$ = Standard Deviation
* **Result:** The new distribution will have a **Mean = 0** and **Standard Deviation = 1**.



---

## 4. Feature Construction
Extracting a new column from existing columns to provide more signal to the model.
* **Example (Titanic Dataset):** Adding `SibSp` (siblings/spouses) and `Parch` (parents/children) to create a new feature called **Family**.

---

## 5. Feature Selection & Extraction

### 5.1 Feature Selection
The goal is to reduce dimensionality, improve model accuracy, and remove redundant information.

### 5.2 Feature Extraction
* **PCA (Principal Component Analysis):** A technique to get features with maximum variance.
* **LDA (Linear Discriminant Analysis):** Focuses on maximizing the separability between known categories.

---

## 6. Algorithm-wise Requirements for Scaling

| Algorithm | Why apply Feature Scaling? |
| :--- | :--- |
| **K-Means / KNN** | Uses Euclidean distance; scaling ensures all features contribute equally. |
| **PCA** | Tries to identify features with maximum variance; variance is scale-sensitive. |
| **ANN** | Helps Gradient Descent converge faster. |
| **Gradient Descent** | Theta ($\theta$) calculation becomes faster. |

**Where Scaling is NOT required:**
* Decision Trees
* Random Forest
* Gradient Boost / XGBoost

---

---

## ✅ End of Notes


