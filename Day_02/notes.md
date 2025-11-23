# 📓 Machine Learning Notes

## Types of Machine Learning (Based on Training)

### 1. Online Learning (Incremental / Streaming Learning)

| Aspect | Description |
| :--- | :--- |
| **Definition** | The model trains gradually, processing one data point or a mini-batch at a time. The Model trains gradually and updates itself continuously as new data comes in. |
| **How it Works** | Trains with small batch of data. New data arrives $\rightarrow$ Update model instantly. Continues updating forever without starting from zero. |
| **Data Handling** | Works with data stream. Can handle infinite full dataset. Does not store the full dataset. |
| **Memory Need** | Low (due to not storing the full dataset). |
| **Model Update** | Continuous, Real-time. |
| **Adaptation** | Learns new trends immediately. Useful where the model must adapt quickly to streaming data. |
| **Training Time** | Very fast for updates. Lower computation than retraining the full model. |
| **Advantage** | Real-time learning. |
| **Disadvantage** | May overfit to the most recent samples. Model may forget old patterns. Debugging and convergence monitoring are difficult. |

---

### Real-world Use Cases for Online Learning

| Use Case | Why Online is Needed |
| :--- | :--- |
| **Stock Price Prediction** | Market changes every second. |
| **Google Keyboard Auto Suggestion** | Learns from what you type. |
| **Fraud Detection** | Fraud strategies evolve. |
| **YouTube/Netflix Personalization** | Updates based on new user behavior. |

---

## Learning Approaches (Based on Learning)

### 1. Instance-Based Learning (Memorizing / Lazy Learning)

* **Key Idea:** "Learn by remembering".
* **Definition:** Instead of learning a generalized model, the algorithm simply **stores the training data** and uses similarity/comparison with existing stored instances when predicting.
* **Prediction:** New input $\rightarrow$ find similar instances $\rightarrow$ predict based on them.
* **Examples:** K-Nearest Neighbors (KNN), Locally Weighted Regression, Case-Based Reasoning.
* **Analogy:** A doctor recalling past patients with similar symptoms to diagnose a new patient.

| Feature | Description |
| :--- | :--- |
| **Learning Time** | Fast (almost no training). |
| **Prediction Time** | Slow (must compare with many stored examples). |
| **Memory Usage** | High (stores full or majority of training data). |
| **Generalization** | Local (predictions based on nearby data). |
| **Adaptability** | Good (can quick update when new data arrives). |

### 2. Model-Based Learning (Eager Learning)

* **Definition:** The algorithm **creates a general mathematical Model** (a function) from the training data **before** making predictions.
* **Prediction:** Build a function $y=F(x)$, then use this stored function to predict new cases.
* **Examples:** Linear Regression, Logistic Regression, Neural Network, Decision trees, SVM (Support Vector Machine).
* **Analogy:** Learning grammar rules to form sentences instead of memorizing examples.
* **Works Well When:** Relationships are strong and can be approximated by a function.

| Feature | Description |
| :--- | :--- |
| **Learning Time** | Slow (training required). |
| **Prediction Time** | Faster (After storing Model Parameters). |
| **Memory Usage** | Low (stores only weights/model structure). |
| **Generalization** | Global (a single function suitable for all data). |
| **Adaptability** | Updating requires retraining. |

---

## Challenges in Machine Learning

| Challenge | Description |
| :--- | :--- |
| **Data Collection** | Gathering enough and the **right kind of data** is the first major hurdle. Without it, the ML system struggles. |
| **Insufficient Data** | When the dataset size is too small, the model cannot generalize well or learn meaningful patterns. More data $\rightarrow$ more perfection of the system. |
| **Non-Representative Data** | Training data doesn't reflect the real world (e.g., distribution shift, sample bias), and the model may fail when deployed. |
| **Poor Quality Data** | Issues like **Missing values**, **Incorrect labels**, or **noisy features** significantly degrade model performance. |
| **Irrelevant Features** | Including features that don't have predictive power (irrelevant features) can confuse the model, increase complexity, and degrade generalization. |
| **Overfitting** | The model becomes **too complex** and learns not only the **real pattern** but also the **random noise** or details. Shows high accuracy during training but **fails on new/unseen data**. *Analogy: Memorizing answers instead of understanding the concept*. |
| **Underfitting** | Happens when a machine model is **too simple** and cannot understand the pattern in the data properly. Performs poorly in both practice tests and real exams. *Analogy: A student who studied very little*. |
| **Deployment / Integration** | Putting a model into production (integration with apps, latency, scaling) poses big hurdles, even when the model works in the lab. |
| **Cost / Resources** | Data collection, storage, computation, model training, and monitoring all cost time and money. |

---

## Machine Learning Applications

| Industry | Application | Description |
| :--- | :--- | :--- |
| **Healthcare** | Disease Diagnosis (ML). | Analysing medical images to detect anomalies. |
| **Healthcare** | Predictive Analytics. | Forecasting patient re-admission. |
| **Finance & Banking** | Fraud Detection. | Spotting unusual transactions via ML. |
| **Finance & Banking** | Credit Scoring. | Predicting default risk using past financial data + other features. |
| **Retail & E-commerce** | Recommendation Systems. | Suggesting products based on user behavior and purchase history. |
| **Retail & E-commerce** | Inventory Optimisation. | Predicting demands and managing supply chain. |
| **Manufacturing** | Predictive Maintenance. | Using sensor data to forecast machine failure. |
