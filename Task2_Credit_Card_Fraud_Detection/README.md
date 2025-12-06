Task 2 – Credit Card Transaction Fraud Detection 
📌 Problem Statement
    Build a machine learning model that predicts whether a credit card transaction is fraud (1) or legit (0) based only on transaction and customer features.

📂 Dataset
  Dataset used from Kaggle:
    https://www.kaggle.com/datasets/kartik2112/fraud-detection

  Files included:
    fraudTrain.csv
    fraudTest.csv

🧹 Data Preprocessing
    Steps applied:
      loaded train & test CSV
      separated features (X) and target (y)
      removed personally identifiable and text-heavy columns (if present)
   
    one-hot encoding for:
      category
      gender
    
    Balanced training using:
      class_weight = "balanced"

🧠 Models Used
1) Logistic Regression (baseline)
      Simply trained on encoded features
      Result:
        accuracy ~86%
        recall for fraud ~10%

2) Random Forest (improved model)
      Used:
       n_estimators=200
       class_weight="balanced"

Performance:
  accuracy ~99%
  recall for fraud ~33%
  significantly better detection of minority class

📈 Final Results
| Model               | Accuracy | Fraud Recall |
| ------------------- | -------- | ------------ |
| Logistic Regression | ~86%     | ~10%         |
| Random Forest       | ~99%     | ~33%         |

Random Forest clearly performs better for detecting fraudulent transactions.

📥 Example Prediction
    Input row:
        amt, category, gender, location, ...
    Output:
        0 → legitimate
        1 → fraud

🛠 Technologies Used
    Python
    Pandas
    scikit-learn
    LogisticRegression
    RandomForestClassifier
    classification_report

📁 Files in this folder
    Task2_credit_fraud.ipynb
    README.md (this file)

🧾 Conclusion
      Fraud datasets are highly imbalanced.
      Logistic Regression handles imbalance poorly.
      Random Forest significantly improves recall for fraud.
      Tree-based models are better choices for fraud detection.
   
