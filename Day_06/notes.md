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

---

## ✅ End of Notes

