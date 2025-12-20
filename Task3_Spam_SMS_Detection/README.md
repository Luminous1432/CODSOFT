# Task 3 – Spam SMS Detection

## 📌 Problem Statement
Build a machine learning model that can automatically classify SMS messages as **Spam** or **Ham (legitimate)** based only on the message text.

### Example:
Input message → "Congratulations! You have won a free prize. Click now!"  
Output → Spam

---

## 📂 Dataset Source
SMS Spam Collection Dataset (Kaggle)

---

## 📂 Dataset Details
- Total messages: ~5,500
- Labels:
  - ham → legitimate message
  - spam → unwanted promotional message

---

## 🧹 Preprocessing Steps
- Loaded dataset using pandas
- Selected relevant columns (label, text)
- Renamed columns for clarity
- Encoded labels:
  - ham → 0
  - spam → 1
- Converted text to lowercase
- Removed unnecessary characters
- Stopwords handled automatically during TF-IDF

---

## 🔠 Feature Extraction (TF-IDF)
Used **TfidfVectorizer** from scikit-learn:
- stop_words = "english"

TF-IDF converts SMS text into numerical vectors that the model can learn from.

---

## 🧠 Model & Training
- Algorithm: Multinomial Naive Bayes
- Library: scikit-learn

### Train / Test Split:
- 80% Training
- 20% Testing

---

## 📊 Evaluation Results
- **Accuracy:** 96.68%

### Classification Highlights:
- Ham messages classified with very high recall
- Spam messages detected with high precision
- Model performs well despite class imbalance

---

## 🧪 Input / Output Example

**Input:**  
"You have WON a free prize! Click this link now!"  

**Predicted Output:**  
Spam

**Input:**  
"I dont think!!!"  

**Predicted Output:**  
Ham

---

## 🛠 Libraries Used
- Python
- pandas
- numpy
- scikit-learn
- TfidfVectorizer
- MultinomialNB
- accuracy_score
- classification_report

---

## 📁 Files in this Folder
- spam_sms_detection.ipynb
- README.md

---

## 📌 Summary
- Built a complete NLP classification pipeline
- Used TF-IDF for feature extraction
- Trained Multinomial Naive Bayes classifier
- Achieved **96.68% accuracy**
- Successfully distinguishes spam from legitimate messages

---

✔ This completes **Task 3 – Spam SMS Detection** for the **CodSoft Machine Learning Internship**.
