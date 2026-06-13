# 📧 Mail Spam Classification (Ham vs Spam)

A **Machine Learning & NLP project** for classifying SMS messages into **Spam** or **Ham (not spam)** using **text preprocessing**, **Bag-of-Words (BOW)**, **TF-IDF**, and multiple ML models including **Naive Bayes** and **Decision Trees**.
<br>
<br>

---


## 🚀 Project Overview

Spam messages are a significant problem in digital communication. The goal of this project is to develop a **robust classification pipeline** that can effectively detect spam messages by leveraging **NLP preprocessing** and **machine learning techniques**.

The project demonstrates:

* Text preprocessing (cleaning, stemming, stopword removal)
* Feature extraction (Bag-of-Words & TF-IDF)
* Model training (Naive Bayes, Decision Tree)
* Model evaluation (Accuracy, Precision, Recall, F1-score)
<br>

---

## 📂 Dataset

* **Dataset Used**: [SMS Spam Collection Dataset](SMSSpamCollection)
  * `label` → `ham` or `spam`
  * `message` → the SMS text
<br>

---

## 🔑 Key Concepts Explained

### 1️⃣ Text Preprocessing

* **Regex Cleaning** → Removed all non-alphabetic characters (numbers, punctuation).
* **Lowercasing** → Standardized text to avoid treating `Spam` and `spam` as different words.
* **Tokenization** → Split messages into individual words.
* **Stopword Removal** → Removed common words (e.g., "the", "is", "at") that do not add meaning.
* **Stemming** → Reduced words to their root form using **Porter Stemmer**.

  * Example: *“playing” → “play”*, *“studies” → “studi”*
  * This reduces vocabulary size and improves model generalization.
<br>

---

### 2️⃣ Feature Engineering

#### 👜 Bag-of-Words (BOW)

* Creates a **vocabulary of words** from the dataset.
* Represents each message as a **vector of word counts**.
* Limitations: Ignores meaning & order, only counts frequencies.

#### 🧮 TF-IDF (Term Frequency–Inverse Document Frequency)

* Improves upon BOW by weighting words.
* **TF (Term Frequency):** How often a word appears in a document.
* **IDF (Inverse Document Frequency):** How rare a word is across documents.
* Formula:

  ```
  TF-IDF = (Frequency of word in document) * log(Total docs / Docs containing word)
  ```
* This ensures common words like *“the”* have low weight, while rare, spam-indicative words like *“free”, “winner”* have higher weight.
<br>

---

### 3️⃣ Models Used

#### 🔹 Naive Bayes Classifier (MultinomialNB)

* Works well with **text data**.
* Assumes independence between features (words).
* Efficient for large vocabulary sizes.
* Achieved **high accuracy (\~95%)** on test set.

#### 🔹 Decision Tree Classifier

* Splits data based on word presence/absence.
* Visualizes decisions but prone to overfitting.
* Useful for interpretability of rules.
<br>

---

## ⚙️ Implementation Steps

1. **Load Dataset** → SMS Spam Collection dataset.
2. **Preprocessing** → Regex, tokenization, stopword removal, stemming.
3. **Feature Extraction** → Bag-of-Words & TF-IDF (n-grams included).
4. **Train-Test Split** → 80% training, 20% testing.
5. **Model Training** → Multinomial Naive Bayes & Decision Tree.
6. **Evaluation** → Accuracy, Precision, Recall, F1-score.
<br>

---

## 📊 Results

| Model        | Feature Set | Accuracy | Precision (Spam) | Recall (Spam) | F1-score |
| ------------ | ----------- | -------- | ---------------- | ------------- | -------- |
| Naive Bayes  | BOW         | \~94%    | 0.92             | 0.93          | 0.92     |
| DecisionTree | BOW         | \~90%    | 0.88             | 0.89          | 0.88     |
| Naive Bayes  | TF-IDF      | \~95%    | 0.93             | 0.94          | 0.94     |
| DecisionTree | TF-IDF      | \~91%    | 0.89             | 0.88          | 0.88     |

✅ **Naive Bayes with TF-IDF performed the best**.
<br>

---

## 🛠️ Tech Stack

* **Python 3.10**
* **Libraries**:

  * `pandas`, `numpy` → Data manipulation
  * `nltk` → Preprocessing (stopwords, stemming)
  * `scikit-learn` → Feature extraction & ML models
  * `matplotlib` → Visualizations
<br>

---

## 📈 Future Improvements

* Add **deep learning models** (LSTMs, Transformers).
* Use **Word Embeddings** (Word2Vec, GloVe, BERT) for semantic meaning.
* Handle **imbalanced dataset** using SMOTE or class weights.
* Deploy as a **Flask/Django web app** for real-world usage.
<br>

---
