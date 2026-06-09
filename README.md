# 🧠 Comment Category Prediction using Machine Learning & NLP

A Machine Learning and Natural Language Processing (NLP) project focused on automatically classifying user comments into predefined categories using textual content and metadata features.

## 🚀 Project Overview

Online platforms generate massive amounts of user comments every day. Manually categorizing these comments is time-consuming and inefficient.

In this project, I developed a multi-class classification system that predicts the category of a user comment by leveraging:

* Comment text (NLP features)
* User interaction signals
* Emoticon usage
* Temporal information
* Post-level metadata

The objective was to build a robust model capable of accurately classifying comments into one of four categories while handling class imbalance and missing data challenges.

---

## 📌 Problem Statement

Given a dataset containing user comments and associated metadata, predict the correct comment category (Label 0–3).

### Dataset Features

#### Text Features

* Comment text

#### Interaction Features

* Upvotes
* Downvotes
* if_1
* if_2

#### Emoticon Features

* emoticon_1
* emoticon_2
* emoticon_3

#### Demographic Indicators

* Race
* Religion
* Gender
* Disability

#### Temporal Features

* Created Date

#### Metadata

* Post ID

---

## 🔍 Exploratory Data Analysis (EDA)

Key findings from the analysis:

### Class Imbalance

* Label 0 was the dominant class.
* Labels 1 and 3 appeared significantly less frequently.
* Special care was required during model evaluation.

### Missing Values

* Demographic features contained a large proportion of missing values (~73%).
* Missing comments were replaced with empty strings.
* Highly sparse demographic columns were excluded from modeling.

### Text Analysis

* Comment length showed limited predictive power.
* Common word frequencies were similar across classes.
* TF-IDF representation was required to capture meaningful textual patterns.

### Feature Correlations

* `if_2` showed the strongest correlation with the target variable.
* Most numerical features individually had weak predictive strength.
* Text features contributed the majority of classification power.

---

## 🛠️ Feature Engineering

### Text Processing

* Text cleaning and preprocessing
* TF-IDF Vectorization
* Unigrams and Bigrams
* Maximum 8000 features

### Engineered Features

* Character Length
* Word Count
* Total Emoticons
* Month Extraction from Timestamp

### Numerical Processing

* Feature Scaling
* Metadata Integration

---

## 🤖 Models Evaluated

### 1. Logistic Regression

Strong baseline model for high-dimensional sparse text data.

**Validation Accuracy:** 90.17%

### 2. Multinomial Naive Bayes

A classical NLP model optimized for text classification tasks.

**Validation Accuracy:** 69.63%

### 3. LightGBM (Final Model)

Gradient Boosting framework capable of learning complex relationships between textual and numerical features.

**Validation Accuracy:** 91.1%

---

## 🎯 Hyperparameter Tuning

RandomizedSearchCV was used to optimize the LightGBM model.

### Best Parameters

```python
{
    'subsample': 0.9,
    'num_leaves': 50,
    'n_estimators': 500,
    'learning_rate': 0.05,
    'colsample_bytree': 0.8
}
```

### Benefits

* Improved generalization
* Reduced overfitting
* Better model stability
* Higher validation accuracy

---

## 📊 Final Results

| Model               | Validation Accuracy |
| ------------------- | ------------------- |
| LightGBM            | 91.1%               |
| Logistic Regression | 90.17%              |
| Naive Bayes         | 69.63%              |

🏆 **Best Model: LightGBM**

The tuned LightGBM classifier achieved the highest performance and was selected as the final model for generating test predictions.

---

## 🧰 Tech Stack

### Programming Language

* Python

### Data Analysis

* Pandas
* NumPy

### Data Visualization

* Matplotlib
* Seaborn

### Machine Learning

* Scikit-Learn
* LightGBM

### NLP

* TF-IDF Vectorizer

### Model Optimization

* RandomizedSearchCV

---

## 📂 Project Workflow

1. Data Loading & Inspection
2. Data Cleaning & Missing Value Handling
3. Exploratory Data Analysis
4. Text Preprocessing
5. Feature Engineering
6. TF-IDF Vectorization
7. Model Training
8. Hyperparameter Tuning
9. Model Evaluation
10. Test Prediction Generation

---

## 📈 Key Learnings

* Importance of feature engineering in NLP tasks.
* Handling imbalanced datasets effectively.
* Combining textual and numerical features improves performance.
* Gradient Boosting models such as LightGBM can significantly outperform traditional classifiers.
* Hyperparameter tuning plays a crucial role in maximizing model performance.

---

## ✅ Outcome

Successfully developed a comment classification system that:

* Processes textual and metadata features.
* Handles missing and imbalanced data.
* Achieves over **91% validation accuracy**.
* Utilizes optimized LightGBM for robust multi-class prediction.

---

### 👨‍💻 Author

**Adhyan Mishra**

Aspiring Data Analyst / Machine Learning Enthusiast

Passionate about Data Science, Machine Learning, NLP, and Business Analytics.
