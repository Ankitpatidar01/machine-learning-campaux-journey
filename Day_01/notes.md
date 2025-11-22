# 🤖 Day 1: Machine Learning Foundations & Learning Paradigms

## I. Introduction to Machine Learning (ML) & Deep Learning (DL)

### What is Machine Learning?
Machine Learning is a field of computer science that uses **statistical techniques** to give computer systems the ability to "learn" with data, without being explicitly programmed.

### Why Deep Learning (DL)?
* DL algorithms (like neural networks) generally show **higher performance/accuracy** compared to older algorithms as the **amount of data increases**.
* It excels in handling complex, high-dimensional data (e.g., images, text).
* *\*

---

## II. Types of Machine Learning (Based on Supervision)

### 1. Supervised Learning
* Trained on **labeled data**.
* **Tasks:**
    * **Regression:** Predicting a continuous output (e.g., stock price).
    * **Classification:** Predicting a category/label (e.g., spam detection).

### 2. Unsupervised Learning
* Trained on **unlabeled data** to find hidden structures or patterns.
* **Tasks:**
    * **Clustering** (e.g., grouping customers).
    * **Dimensionality Reduction** (e.g., PCA).
    * **Anomaly Detection** (Outlier analysis).
    * **Association Rule Learning** (Discovering relationships like "If A, then B").

### 3. Semi-supervised Learning
* Trained using a **small amount of labeled data** and a **large amount of unlabeled data**.
* **Example:** In Google Photos, labeling a few images of 'Ankit' allows the system to automatically group all other unlabeled images of him.

### 4. Reinforcement Learning (RL)
* An **agent** learns to make optimal decisions by **interacting with an environment** and receiving **reward or punishment** for its actions.

---

## III. Anomaly Detection (Outlier Detection)

**Goal:** Identify data points (anomalies) that deviate significantly from the normal data distribution.
* **Collective Anomalies:** A group of points that is anomalous (e.g., many failed login attempts from the same IP).

| Method | Anomaly Definition |
| :--- | :--- |
| **Isolation Forest** | Anomalies are easy to isolate; they lie alone in less dense regions. |
| **Local Outlier Factor (LOF)** | Anomalies are farther from their neighbors compared to normal points. |
| **One-Class SVM** | Anomalies lie outside the boundary learned by the model. |
| **DBSCAN** | Points marked directly as **noise points** are considered anomalies. |
| **Autoencoders** | High **reconstruction error** indicates an anomaly. |

---

## IV. Batch Learning vs. Online Learning

| Aspect | Batch Learning (Offline) | Online Learning (Incremental/Streaming) |
| :--- | :--- | :--- |
| **Data Requirement** | Needs **all available data** to train a fixed model. | Trains gradually, processing data **point-by-point** or in small batches. |
| **Memory** | Requires **large memory** to store the entire dataset. | Low memory requirement; handles data streams. |
| **Adaptation** | Slow/Costly to adapt; requires **re-training** on old + new data periodically. | **Learns instantly** from new data; model updates continuously. |
| **Generalization** | High (model sees the entire data distribution). | Lower (model only sees local data; risk of "forgetting" old patterns). |
| **Concept Drift** | Poorly handles changes in data patterns over time. | Excellent for environments where data/concepts **change quickly** (Real-time). |

### Real-World Use Cases

| Learning Type | Use Case | Rationale |
| :--- | :--- | :--- |
| **Batch** | Healthcare Risk Prediction, Image Classification | Data changes slowly; periodic updates are sufficient. |
| **Online** | Market/Stock Prediction, YouTube/Netflix Personalization, Fraud Detection | Market/patterns change rapidly, requiring instant model adoption. |
