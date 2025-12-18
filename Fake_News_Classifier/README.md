# Fake News Classification using Word Embeddings

## 📌 Overview
This project focuses on building a **Fake News Classification system** using Natural Language Processing (NLP) techniques and traditional machine learning algorithms. News articles are classified as **Fake** or **Real** by converting text into numerical representations using **pre-trained word embeddings** from spaCy, followed by supervised classification.

The dataset used for this project is sourced from **Kaggle**.

---

## 📊 Dataset
- Original dataset size: approximately **31,000** news articles
- Text column: news article content
- Target column: `Fake`
  - `0` → Real News  
  - `1` → Fake News

### Duplicate Handling
During exploratory data analysis, approximately **3,000 duplicate samples** (around **9–10%** of the dataset) were identified.

- Duplicate entries were removed to:
  - Prevent information leakage
  - Improve generalization
  - Ensure realistic evaluation performance

- Final dataset size after cleaning: approximately **28,000** samples

---

## 🧹 Text Representation
- Pre-trained spaCy model used: **`en_core_web_lg`**
- Each token is represented by a **300-dimensional dense vector**
- Document-level vectors are created by aggregating token vectors (mean pooling)
- No aggressive stop-word removal or lemmatization was applied, as semantic meaning is already captured by word embeddings

---

## ⚙️ Feature Engineering
- Each news article is transformed into a fixed-length dense vector
- These vectors are directly used as input features for machine learning models
- Unnecessary spaCy pipeline components were disabled to improve efficiency

---

## 🔀 Train-Test Split
- Split ratio: **80% training / 20% testing**
- **Stratified split** used to maintain class balance
- Random state fixed for reproducibility

---

## 🤖 Models Used
The following models were trained and evaluated:

- **Linear Support Vector Classifier (LinearSVC)**
- **Multinomial Naive Bayes (MultinomialNB)**

---

## 📈 Evaluation Metrics
Models were evaluated using standard classification metrics:
- Precision
- Recall
- F1-score
- Accuracy

---

## 🧪 Results

### 🔹 Linear Support Vector Classifier (LinearSVC)

          precision    recall  f1-score   support

       0       0.98      0.99      0.99      2142
       1       0.99      0.98      0.99      2348

accuracy                           0.99      4490

- **Accuracy:** 99%
- Strong performance across both classes
- Demonstrates the effectiveness of dense word embeddings combined with linear classifiers

---

### 🔹 Multinomial Naive Bayes

          precision    recall  f1-score   support

       0       0.90      0.79      0.84      2142
       1       0.83      0.92      0.87      2348

accuracy                           0.86      4490

- **Accuracy:** 86%
- Performed reasonably well but was outperformed by LinearSVC
- Naive Bayes showed lower precision for fake news detection

---

## 🧠 Observations
- **LinearSVC significantly outperformed MultinomialNB** on dense word embeddings
- Pre-trained embeddings helped capture semantic relationships beyond simple word frequency
- Linear models proved more effective for high-dimensional continuous feature spaces

---


## 📌 Conclusion
This project demonstrates that combining **pre-trained word embeddings** with **linear classifiers** can yield strong results for fake news detection. Among the evaluated models, **LinearSVC achieved the best overall performance**, making it a suitable choice for large-scale text classification tasks.

---

## 👤 Author
**Saurabh Vishwakarma**  
BCA | Data Science & Machine Learning  

