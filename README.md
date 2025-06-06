# 💬 Sentiment Classification

This project was completed as part of the **Machine Learning COMP-544DL** course at the **University of Nicosia**.

The goal was to develop a sentiment classification model using text data labeled as **positive**, **neutral**, or **negative**. The project involved detailed preprocessing, feature extraction, model selection, and evaluation — all based on a dataset of 8,000 text samples.

---

## 📁 Project Structure

| File                                  | Description |
|---------------------------------------|-------------|
| `experiments1.ipynb`                 | Evaluates and compares ML models using TF-IDF and CountVectorizer (LogReg, NB, SVC, RF). |
| `experiments2_preprocess_validation.ipynb` | Tests different preprocessing variations and validates their effects on model accuracy. |
| `Technical Report.pdf`               | Full write-up describing methodology, results, EDA, and insights. |
| `train.csv`                          | The labeled dataset with text and sentiment labels. |

---

## 🧪 Dataset

- **Source**: Internal course dataset (8,000 samples)
- **Task**: Multi-class classification (positive, neutral, negative)
- **Splitting**: 90% used for training and tuning; 10% held back for final evaluation
- **Imbalance**: Class distribution – 38% positive, 35% neutral, 27% negative

---

## ⚙️ Preprocessing Steps

1. URL, mention, and hashtag removal/splitting
2. Emoticon and slang replacement (e.g. `lol` → "laughing out loud")
3. Lowercasing, punctuation removal
4. Non-English text translation (~30-40 cases)
5. Porter stemming
6. Filtering 1-character words, truncating to max 200 tokens

---

## 🧠 Models & Techniques

- **Vectorization**: TF-IDF, CountVectorizer (with unigrams and bigrams)
- **Classifiers Tested**:
  - Linear SVM (LinearSVC)
  - Naive Bayes
  - Logistic Regression
  - Random Forest
- **Final Model**: Voting Classifier (ensemble of SVC, NB, and LR)

Additional experiments included:
- GridSearch with 10-fold stratified CV
- Class imbalance handling via class weights
- DBSCAN outlier detection
- Dimensionality reduction with SVD & PCA
- Threshold tuning for prediction probabilities

---

## 📊 Results Summary

- All core models achieved **~60% cross-validation accuracy**
- Including bigrams improved feature representation
- SVC achieved highest recall for negative class
- Voting Classifier chosen for robustness and vocabulary coverage
