# 📓 Machine Learning Notes

## Types of Machine Learning (Based on Training)

### 1. Online Learning (Incremental / Streaming Learning)

| Aspect | Description | Source |
| :--- | :--- | :--- |
| **Definition** | [cite_start]The model trains gradually [cite: 14][cite_start], processing one data point or a mini-batch at a time[cite: 17, 21]. [cite_start]The Model trains gradually [cite: 16] [cite_start]and updates itself continuously [cite: 22] [cite_start]as new data comes in[cite: 23, 25]. [cite_start]| [cite: 9, 10, 11, 12, 13, 15, 16, 17, 18, 19, 21, 22, 23, 24, 25] |
| **How it Works** | [cite_start]Trains with small batch of data[cite: 33, 34]. [cite_start]New data arrives $\rightarrow$ Update model instantly[cite: 36]. [cite_start]Continues updating forever without starting from zero[cite: 37, 38]. [cite_start]| [cite: 28, 30, 31, 32, 33, 34, 35, 36, 37, 38] |
| **Data Handling** | [cite_start]Works with data stream[cite: 52]. [cite_start]Can handle infinite full dataset[cite: 55, 56]. [cite_start]| [cite: 52, 55, 56] |
| **Memory Need** | [cite_start]Low [cite: 53][cite_start], doesn't store the full dataset[cite: 53]. [cite_start]| [cite: 53] |
| **Model Update** | [cite_start]Continuous, Real-time[cite: 57]. [cite_start]| [cite: 57] |
| **Adaptation** | [cite_start]Learns new trends immediately[cite: 58, 61, 62]. [cite_start]| [cite: 58, 61, 62] |
| **Training Time** | [cite_start]Very fast for updates[cite: 63]. [cite_start]Lower computation than retraining the full model[cite: 67, 68, 69, 70]. [cite_start]| [cite: 63, 67, 68, 69, 70] |
| **Advantage** | [cite_start]Real-time learning[cite: 54]. [cite_start]Useful where the model must adapt quickly [cite: 60, 65, 66] [cite_start]to streaming data[cite: 64]. [cite_start]| [cite: 54, 60, 64, 65, 66] |
| **Disadvantage** | [cite_start]May overfit to the most recent samples[cite: 74, 75, 76]. [cite_start]Model may forget old patterns[cite: 77]. [cite_start]Debugging and convergence monitoring are difficult[cite: 78, 81]. [cite_start]| [cite: 74, 75, 76, 77, 78, 81] |

---

### Real-world Use Cases for Online Learning

| Use Case | Why Online is Needed | Source |
| :--- | :--- | :--- |
| **Stock Price Prediction** | [cite_start]Market changes every second[cite: 87, 88, 93]. [cite_start]| [cite: 86, 87, 88, 93] |
| **Google Keyboard Auto Suggestion** | [cite_start]Learns from what you type[cite: 94]. [cite_start]| [cite: 89, 94] |
| **Fraud Detection** | [cite_start]Fraud strategies evolve[cite: 95]. [cite_start]| [cite: 90, 95] |
| **YouTube/Netflix Personalization** | [cite_start]Updates based on new user behavior[cite: 96, 97, 98]. [cite_start]| [cite: 91, 92, 96, 97, 98] |

---

## Learning Approaches (Based on Learning)

### 1. Instance-Based Learning (Memorizing / Lazy Learning)

* [cite_start]**Key Idea:** "Learn by remembering"[cite: 128].
* [cite_start]**Definition:** Instead of learning a generalized model [cite: 109][cite_start], the algorithm simply **stores the training data** [cite: 110] [cite_start]and uses similarity/comparison with existing stored instances [cite: 112, 117, 131, 134] [cite_start]when predicting[cite: 114].
* [cite_start]**Prediction:** New input [cite: 163] [cite_start]$\rightarrow$ find similar instances [cite: 163] [cite_start]$\rightarrow$ predict based on them[cite: 164].
* [cite_start]**Examples:** K-Nearest Neighbors (KNN) [cite: 136][cite_start], Locally Weighted Regression [cite: 136][cite_start], Case-Based Reasoning[cite: 136].
* [cite_start]**Analogy:** A doctor recalling past patients with similar symptoms [cite: 177, 179] [cite_start]to diagnose a new patient[cite: 181, 182].

| Feature | Description | Source |
| :--- | :--- | :--- |
| **Learning Time** | [cite_start]Fast (almost no training)[cite: 142, 143]. [cite_start]| [cite: 141, 142, 143] |
| **Prediction Time** | [cite_start]Slow [cite: 145] (must compare with many stored examples) [cite_start][cite: 145, 146]. [cite_start]| [cite: 144, 145, 146] |
| **Memory Usage** | [cite_start]High [cite: 150] (stores full or majority of training data) [cite_start][cite: 150, 151]. [cite_start]| [cite: 149, 150, 151] |
| **Generalization** | [cite_start]Local [cite: 153] (predictions based on nearby data) [cite_start][cite: 153, 155]. [cite_start]| [cite: 152, 153, 155] |
| **Adaptability** | [cite_start]Good [cite: 157] [cite_start](can quick update [cite: 159] [cite_start]when new data arrives [cite: 158]). [cite_start]| [cite: 156, 157, 158, 159] |

### 2. Model-Based Learning (Eager Learning)

* [cite_start]**Definition:** The algorithm **creates a general mathematical Model** [cite: 186, 188] (a function) [cite_start]from the training data [cite: 189] [cite_start]**before** making predictions[cite: 190].
* [cite_start]**Prediction:** Build a function $y=F(x)$ [cite: 221][cite_start], then use this stored function to predict new cases[cite: 222].
* [cite_start]**Examples:** Linear Regression [cite: 196][cite_start], Logistic Regression [cite: 201][cite_start], Neural Network [cite: 201][cite_start], Decision trees [cite: 202][cite_start], SVM (Support Vector Machine)[cite: 203].
* [cite_start]**Analogy:** Learning grammar rules [cite: 236] [cite_start]to form sentences [cite: 237] [cite_start]instead of memorizing examples[cite: 238].
* [cite_start]**Works Well When:** Relationships are strong and can be approximated by a function[cite: 227, 229].

| Feature | Description | Source |
| :--- | :--- | :--- |
| **Learning Time** | [cite_start]Slow [cite: 207] (training required) [cite_start][cite: 207]. [cite_start]| [cite: 206, 207] |
| **Prediction Time** | [cite_start]Faster (After storing Model Parameters)[cite: 209]. [cite_start]| [cite: 208, 209] |
| **Memory Usage** | [cite_start]Low [cite: 211] (stores only weights/model structure) [cite_start][cite: 211]. [cite_start]| [cite: 210, 211] |
| **Generalization** | [cite_start]Global [cite: 216] (a single function suitable for all data) [cite_start][cite: 217]. [cite_start]| [cite: 213, 216, 217] |
| **Adaptability** | [cite_start]Updating requires retraining[cite: 218]. [cite_start]| [cite: 215, 218] |

---

## Challenges in Machine Learning

| Challenge | Description | Source |
| :--- | :--- | :--- |
| **Data Collection** | [cite_start]Gathering enough and the **right kind of data** is the first major hurdle[cite: 242]. [cite_start]Without it, the ML system struggles[cite: 243, 246]. [cite_start]| [cite: 241, 242, 243, 246] |
| **Insufficient Data** | [cite_start]When the dataset size is too small [cite: 247][cite_start], the model cannot generalize well [cite: 248] [cite_start]or learn meaningful patterns[cite: 249]. [cite_start]More data $\rightarrow$ more perfection of the system[cite: 251, 252]. [cite_start]| [cite: 245, 247, 248, 249, 251, 252] |
| **Non-Representative Data** | [cite_start]Training data doesn't reflect the real world (e.g., distribution shift, sample bias) [cite: 255][cite_start], and the model may fail when deployed[cite: 258, 260]. [cite_start]| [cite: 253, 254, 255, 258, 260] |
| **Poor Quality Data** | [cite_start]Issues like **Missing values** [cite: 263][cite_start], **Incorrect labels** [cite: 263][cite_start], or **noisy features** [cite: 264] [cite_start]significantly degrade model performance[cite: 265]. [cite_start]| [cite: 262, 263, 264, 265] |
| **Irrelevant Features** | [cite_start]Including features that don't have predictive power (irrelevant features) [cite: 269, 270] [cite_start]can confuse the model [cite: 276][cite_start], increase complexity [cite: 277][cite_start], and degrade generalization[cite: 281]. [cite_start]| [cite: 267, 268, 269, 270, 271, 272, 273, 274, 275, 276, 277, 281] |
| **Overfitting** | [cite_start]The model becomes **too complex** [cite: 283] [cite_start]and learns not only the **real pattern** [cite: 284] [cite_start]but also the **random noise** or details[cite: 286, 287, 288]. [cite_start]Shows high accuracy during training but **fails on new/unseen data**[cite: 296, 298, 299, 301, 302]. [cite_start]*Analogy: Memorizing answers instead of understanding the concept*[cite: 289, 293]. [cite_start]| [cite: 279, 282, 283, 284, 286, 287, 288, 289, 293, 296, 298, 299, 301, 302] |
| **Underfitting** | [cite_start]Happens when a machine model is **too simple** [cite: 309] [cite_start]and cannot understand the pattern in the data properly[cite: 310, 314]. [cite_start]Performs poorly in both practice tests and real exams[cite: 325, 327, 329]. [cite_start]*Analogy: A student who studied very little*[cite: 318, 320]. [cite_start]| [cite: 304, 309, 310, 314, 318, 320, 325, 327, 329] |
| **Deployment / Integration** | [cite_start]Putting a model into production (integration with apps, latency, scaling) [cite: 331] [cite_start]poses big hurdles [cite: 334][cite_start], even when the model works in the lab[cite: 330]. [cite_start]| [cite: 330, 331, 334] |
| **Cost / Resources** | [cite_start]Data Collection [cite: 348][cite_start], Storage [cite: 349][cite_start], computation [cite: 349][cite_start], model training [cite: 350][cite_start], and monitoring [cite: 350] [cite_start]all cost time and money[cite: 352]. [cite_start]| [cite: 347, 348, 349, 350, 352] |

---

## Machine Learning Applications

| Industry | Application | Description | Source |
| :--- | :--- | :--- | :--- |
| **Healthcare** | [cite_start]Disease Diagnosis (ML)[cite: 362, 363]. | [cite_start]Analysing medical images to detect anomalies[cite: 367, 368]. [cite_start]| [cite: 361, 362, 363, 367, 368] |
| **Healthcare** | [cite_start]Predictive Analytics[cite: 364]. | [cite_start]Forecasting patient re-admission[cite: 365, 366]. [cite_start]| [cite: 364, 365, 366] |
| **Finance & Banking** | [cite_start]Fraud Detection[cite: 370]. | [cite_start]Spotting unusual transactions via ML[cite: 371, 372, 374]. [cite_start]| [cite: 369, 370, 371, 372, 374] |
| **Finance & Banking** | [cite_start]Credit Scoring[cite: 375]. | [cite_start]Predicting default risk [cite: 377, 378] [cite_start]using past financial data + other features[cite: 375, 376]. [cite_start]| [cite: 375, 376, 377, 378] |
| **Retail & E-commerce** | [cite_start]Recommendation Systems[cite: 380]. | [cite_start]Suggesting products based on user behavior and purchase history[cite: 380]. [cite_start]| [cite: 379, 380] |
| **Retail & E-commerce** | [cite_start]Inventory Optimisation[cite: 381]. | [cite_start]Predicting demands and managing supply chain[cite: 382, 383, 384]. [cite_start]| [cite: 381, 382, 383, 384] |
| **Manufacturing** | [cite_start]Predictive Maintenance[cite: 388]. | [cite_start]Using sensor data [cite: 389] [cite_start]to forecast machine failure[cite: 391]. [cite_start]| [cite: 385, 387, 388, 389, 391] |
