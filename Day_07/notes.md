# Column Transformation in Machine Learning

## What is Column Transformation?
Column transformation is a data preprocessing technique used to apply **different transformations to different columns** of a dataset based on their data type and role.

---

## Why Column Transformation is Required?

### 1. Different Columns Have Different Data Types
A dataset usually contains:
- **Numerical data** (Age, Salary)
- **Categorical data** (City, Gender)
- **Target variable** (Label)

Each type needs a **different preprocessing method**.

| Column Type | Example | Required Transformation |
|------------|--------|-------------------------|
| Numerical | Age, Salary | Scaling |
| Categorical | City, Gender | Encoding |
| Target | Purchased | No transformation |

---

### 2. Machine Learning Models Require Numerical Data
Most ML algorithms:
- ❌ Cannot process strings or text
- ✅ Work only with numerical values

So:
- Categorical columns → Encoding (OneHot / Label)
- Numerical columns → Scaling (StandardScaler / MinMaxScaler)

---

### 3. Prevents Data Leakage
Column transformation ensures:
- Training data → `fit + transform`
- Test data → `transform only`

This avoids **using test data information during training**, which can otherwise lead to incorrect model performance.

---

### 4. Maintains Feature Consistency
Without column transformation:
- Feature order can get mixed
- Train-test feature mismatch may occur

Column transformation guarantees:
- Correct column mapping
- Same structure for training and testing data

---

### 5. Clean, Structured, and Reusable Code
Instead of applying transformations manually:
- Scaling separately
- Encoding separately
- Merging features manually

Column transformation allows:
- All preprocessing in one place
- Easy reuse using pipelines
- Cleaner and production-ready code

---

## Example (Conceptual)

```python
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import StandardScaler, OneHotEncoder

ct = ColumnTransformer(
    transformers=[
        ('num', StandardScaler(), ['Age', 'Salary']),
        ('cat', OneHotEncoder(), ['City'])
    ]
)
