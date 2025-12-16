# 🛒 E-Commerce Text Classification using TF-IDF & Linear SVC

## 📌 Project Overview
This project focuses on **text classification** using an e-commerce dataset where product-related text data is categorized into multiple classes.  
The objective is to build an efficient and accurate machine learning pipeline using classical NLP techniques and compare different model performances.

---

## 🧠 Problem Statement
Given textual data from an e-commerce platform (such as product descriptions or titles), the task is to classify each text into one of the predefined categories.

---

## 🛠️ Tech Stack & Libraries
- Python  
- pandas 
- scikit-learn  
- spaCy  
- matplotlib, seaborn  

---

## 🔄 Data Preprocessing
The following preprocessing steps were applied to clean and standardize the text data:

- Removal of stop words  
- Lemmatization to convert words into their base form  
- Handling missing values in text data  
- Stratified train-test split to maintain class distribution  

These steps help reduce noise and improve model performance.

---

## 🧩 Feature Engineering
### TF-IDF Vectorization
- Used **TF-IDF Vectorizer** to convert text data into numerical feature vectors  
- Assigns higher weight to informative and less frequent words  
- Reduces the impact of common words that carry little semantic meaning  

---

## Models Used

### 1️⃣ K-Nearest Neighbors (KNN)
- Used initially for baseline comparison  
- Performed reasonably well  
- High prediction time due to distance calculations in high-dimensional TF-IDF space  

### 2️⃣ Linear Support Vector Classifier (LinearSVC)
- Final and best-performing model  
- Extremely fast training and prediction  
- Well-suited for high-dimensional sparse text features  

---

##Model Evaluation
Models were evaluated using:

- Precision  
- Recall  
- F1-score  
- Accuracy  
- Confusion Matrix  

---

## 🔥 Final Model Performance (LinearSVC)

- **Accuracy:** 98%  
- **Macro F1-score:** 0.98  
- **Weighted F1-score:** 0.98  

The confusion matrix shows strong diagonal dominance, indicating excellent class separation with minimal misclassification.

---

## 📈 Results & Model Comparison

| Model | Accuracy | Training + Prediction Time |
|-----|----------|----------------------------|
| KNN | ~96% | ~2 minutes |
| LinearSVC | **~98%** | **~3 seconds** |

LinearSVC significantly outperformed KNN in both accuracy and computational efficiency.

---

## ✅ Key Takeaways
- TF-IDF combined with LinearSVC is highly effective for text classification tasks  
- Linear models scale efficiently for large text datasets  
- Proper preprocessing and stratified splitting improve model reliability  

---

## 🚀 Future Improvements
- Use n-grams (bi-grams and tri-grams) for better contextual understanding  
- Perform hyperparameter tuning using GridSearchCV  
- Experiment with word embeddings or transformer-based models  

---

