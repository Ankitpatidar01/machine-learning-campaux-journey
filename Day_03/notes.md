# 📓 Machine Learning Notes

## 1. Machine Learning Development Life Cycle (MLDLC)

MLDLC is a cycle followed to build systematic, repeatable, and reliable ML systems.

* **Failure points:** A model may fail after deployment due to wrong data or improper evaluation giving misleading results.

| Step | Title | Description |
| :--- | :--- | :--- |
| **1** | **Define the Problem** | Decide what the problem is. Determine the required cost and the size of the team needed. Identify if the Machine Learning Model is **unsupervised** or **supervised**. |
| **2** | **Gathering the Data** | Collect data from databases, web scraping, sensors, logs, and APIs. **More data** leads to a **Better Model**. |
| **3** | **Data Processing** | This is where **most time is spent**. Involves:<ul><li>Handling missing values.</li><li>Removing duplicate / noisy entries.</li><li>Outlier treatment.</li><li>Encoding categorical data.</li><li>Scaling / normalization.</li></ul> |
| **4** | **Exploratory Data Analysis (EDA)** | Understand data patterns, trends, and correlations. Use plots, visualization, and statistical summaries. Helps identify patterns, outliers, relationships, and data imbalance. Guides feature engineering and model selection. |
| **5** | **Feature Engineering/Selection** | **Creating new meaningful features** using domain understanding. *Example: Extracting year/month from date or calculating age from DOB (Date of Birth)*. **Removing unimportant or redundant features**. Improves model accuracy and performance. |
| **6** | **Model Training & Evaluation** | Select a suitable algorithm and train the model. Split the dataset into train, validation, and test sets. Compare multiple algorithms. Perform hyperparameter tuning. Avoid overfitting and underfitting. |
| **7** | **Model Deployment** | Take the best model and integrate it with the real system. Can be done using Flask / REST API, Docker Container, or a Cloud platform (AWS, GCP, Azure). The model should solve the real-world use case. |
| **8** | **Testing & Monitoring** | Test model performance in the real environment. Check **Latency**, **Accuracy**, **Model Drift**, and **Reliability**. Testing is continuous even after deployment. |
| **9** | **Optimization** | Improve the model using: more data, hyperparameter tuning, new features, or a retraining strategy. ML is a **continuous cycle**, not a one-time activity. |

---

## 2. Tensors

### Definition and Attributes

* A **tensor** is essentially a **multi-dimensional array** (a generalization of a scalar, vector, and matrix).
* **Key Attributes:**
    * **Rank (or Order):** The number of axes or dimensions of the tensor.
    * **Shape:** The size of each axis (how many elements along each dimension).
    * **Datatype:** The type of element inside (e.g., Float32, Int64).

### Tensors by Rank

| Rank | Name | Example |
| :--- | :--- | :--- |
| **Rank 0** | **Scalar** | A single number. |
| **Rank 1** | **Vector** | e.g., $[1, 2, 3, 4]$. |
| **Rank 2** | **Matrix** | Tables of numbers, e.g., $\begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{bmatrix}$. |
| **Rank 3+** | **Multi-dimensional** | Color image (Height $\times$ Width $\times$ Channels), or a batch of images (Batch Size $\times$ Height $\times$ Width $\times$ Channels). |

### Importance in Machine Learning

* In ML frameworks (TensorFlow, PyTorch), **everything is a tensor**: inputs, outputs, weights, and activations.
* Data is often multi-dimensional (e.g., images, time-series, videos, 3D Scans).
* Tensors allow us to represent and manipulate such data efficiently.
* Neural networks process tensor operations, and frameworks optimize these operations on hardware (GPU/TPU) for **speed and scale**.
* Understanding tensor shapes, ranks, and transformations is **critical** when building or debugging models.

### Tensor Examples

* **Time Series Data (3D):** Time series data for 365 days of highest/lowest price has a shape of (365, 2). If collected for 10 years, the shape becomes **(10, 365, 2)**, where the first axis is the Time axis.
* **Images (4D):** Shape is typically **(Batch Size, Height, Width, Channel)**.
* **Videos (5D):** A video is a collection of images (frames). For example, 4 videos of 60 seconds at 30 FPS would result in a **5D tensor**.

### Tensor Operations

* **Element-wise operations:** Add a scalar or multiply each element.
* **Matrix multiplication (Tensor contraction):** Generalizing the dot product for higher dimensions.
* **Reshaping / Flattening:** Changing shape while preserving data order.
* **Transposing / Permuting axes:** Changing which axis corresponds to what (important when the model expects a certain shape).
