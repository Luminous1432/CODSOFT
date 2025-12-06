Task 1 – Movie Genre Classification

📌 Problem Statement
    Build a machine learning model that predicts the genre of a movie based only on its plot/description text.

    Example:
    Input description → “A man must save the city…”
    Output genre → action

📂 Dataset
    Source: Kaggle – “Genre Classification Dataset IMDb”

📂 Files included:
    train_data.txt → ID, TITLE, GENRE, DESCRIPTION
    test_data.txt → ID, TITLE, DESCRIPTION
    test_data_solution.txt → ID, TITLE, GENRE (ground truth)

    Total samples:
      Train ~54k
      Test ~54k

    Format example:
      1 ::: Movie Title ::: drama ::: movie description...

🧹 Preprocessing Steps  
      Load .txt files line by line
      Split using delimiter :::
      Build DataFrames:
        train_df(id, title, genre, description)
        test_df(id, title, description)
        solution_df(id, title, genre)
      Clean invisible characters (like BOM \ufeff)
      Convert text → lowercase, remove stopwords (TF-IDF handles this)

🔠 Feature Extraction (TF-IDF)
      Used TfidfVectorizer from scikit-learn:
      stop_words="english"
      max_features=20000
      TF-IDF converts text → numerical vectors the model can learn from.

🧠 Model & Training
      Algorithm: Logistic Regression (multi-class)
      Library: scikit-learn
      Settings:
          max_iter = 500
      class_weight = "balanced" (because dataset is highly imbalanced)
      
      Train/validation split:
        80% train
        20% validation

      stratify=y to preserve genre distribution

📊 Evaluation
      Validation Accuracy
        ✔ ~48.38%
      Test Accuracy
        ✔ ~48.68%
      Both are similar → good generalization.
      
      Where accuracies come from:
        Validation → from 20% of train_df
        Test → comparing predictions with test_data_solution.txt

🔮 Observations
      ✔ Frequent genres like:
          documentary
          drama
          comedy
          horror
…perform better

    ❌ Rare genres:
          fantasy
          biography
          history
          war
…have lower precision because of imbalance.

🧪 Input / Output Example
      Input text:
          A superhero discovers his powers and fights evil.
      Predicted Genre:
          action

🛠 Libraries Used  
      Python
      pandas
      scikit-learn
      TfidfVectorizer
      LogisticRegression
      accuracy_score
      classification_report

📁 Files in this folder
      movie_genre_classification.ipynb
      README.md (this file)

📌 Summary
      Built complete NLP classification pipeline
      Used TF-IDF + Logistic Regression
      Debugged .txt parsing
      Cleaned ID mismatches
      Achieved ~48–49% accuracy over 25+ genres

This completes Task-1 for CodSoft ML Internship.
