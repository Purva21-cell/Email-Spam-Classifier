#  Email Spam Classifier Using Logistic Regression

##  Project Overview

This project implements a Machine Learning-based Spam Classifier using **Logistic Regression** and **TF-IDF (Term Frequency-Inverse Document Frequency)**.

The model analyzes text messages and classifies them into two categories:

- **Ham:** Legitimate messages.
- **Spam:** Unwanted or promotional messages.

The project uses a publicly available UCI SMS Spam Collection dataset to train and evaluate the classification model.

## Project Objectives

- Collect a public spam/ham text dataset.
- Perform text preprocessing and cleaning.
- Convert text into numerical features using TF-IDF.
- Train a Logistic Regression classification model.
- Evaluate model performance using Accuracy, Precision, Recall, and F1-score.
- Export the trained model for future predictions.
- Test the model using new text messages.

##  Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming language |
| Jupyter Notebook | Development environment |
| Pandas | Data manipulation |
| NumPy | Numerical operations |
| Scikit-learn | Machine Learning |
| TF-IDF | Text feature extraction |
| Logistic Regression | Classification algorithm |
| Matplotlib | Data visualization |
| Seaborn | Confusion matrix visualization |
| Joblib | Model serialization |

##  Dataset

**Dataset:** UCI SMS Spam Collection

The dataset contains labeled text messages classified as:

- `ham` – Legitimate messages
- `spam` – Spam messages

Dataset source:

https://archive.ics.uci.edu/dataset/228/sms+spam+collection

The dataset contains approximately 5,574 messages.

##  Project Workflow

### 1. Data Collection
Download and load the publicly available UCI SMS Spam Collection dataset.

### 2. Data Preprocessing
- Convert text into lowercase.
- Remove unnecessary special characters.
- Remove extra spaces.
- Encode labels:
  - Ham = 0
  - Spam = 1

### 3. Train-Test Split
Split the dataset into:
- 80% Training data
- 20% Testing data

### 4. TF-IDF Feature Extraction

Use `TfidfVectorizer` to convert text messages into numerical features.

### 5. Model Training

Train a Logistic Regression classifier using Scikit-learn.

### 6. Model Evaluation

Evaluate the trained model using:
- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

### 7. Model Export

Save the trained Logistic Regression model and TF-IDF vectorizer using Joblib.

Exported file:

`spam_classifier_model.pkl`

### 8. Prediction Testing

Test the saved model with new messages to determine whether they are Spam or Ham.

##  Model Performance

The following results were obtained from the implemented notebook:

| Evaluation Metric | Result |
|---|---:|
| Accuracy | 96.50% |
| Precision | 1.0000 |
| Recall | 0.7383 |
| F1-Score | 0.8494 |

### Classification Report

| Class | Precision | Recall | F1-Score |
|---|---:|---:|---:|
| Ham | 0.96 | 1.00 | 0.98 |
| Spam | 1.00 | 0.74 | 0.85 |

**Note:** These are the results from the current train-test split. Performance may vary with different datasets or configurations.

##  Installation and Execution

### Step 1: Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

### Step 2: Navigate to the Project Folder

```bash
cd YOUR_PROJECT_FOLDER
```

### Step 3: Install Required Libraries

```bash
pip install pandas numpy scikit-learn matplotlib seaborn joblib
```

### Step 4: Open Jupyter Notebook

```bash
jupyter notebook
```

### Step 5: Run the Notebook

Open:

`Email_Spam_Classifier_Final.ipynb`

Execute all cells sequentially.

The notebook will download the dataset, preprocess the messages, train the model, evaluate its performance, and export the trained model.

##  Project Structure

```text
Email-Spam-Classifier/
│
├── Email_Spam_Classifier_Final.ipynb
│
├── spam_classifier_model.pkl
│
├── README.md
│
└── spam_dataset.zip
```

*Note: The dataset ZIP file is downloaded automatically when the notebook runs. Include generated files in your repository only if you intend to distribute them.*

##  Example Predictions

| Input Message | Prediction |
|---|---|
| Congratulations! You have won a free prize. Claim now! | SPAM |
| Hey, are we meeting today? | HAM |
| URGENT! You have won a cash reward. Call now! | SPAM |
| Please send me the assignment notes. | HAM |

##  Saved Model

The trained model is exported using Joblib.

```python
import joblib

joblib.dump(
    {
        "model": model,
        "tfidf": tfidf
    },
    "spam_classifier_model.pkl"
)
```

The exported file can be loaded later for making predictions without retraining the model.

##  Future Improvements

- Use a larger email-specific spam dataset.
- Improve spam detection recall.
- Experiment with Naive Bayes and other classification algorithms.
- Develop a web-based spam detection interface.
- Add real-time message classification.

##  Conclusion

This project demonstrates how Machine Learning and Natural Language Processing techniques can be used to classify spam and legitimate text messages.

By combining TF-IDF feature extraction with Logistic Regression, the model achieved **96.50% accuracy** on the test dataset.

The trained model is also exported for future use and predictions.

---

**Project:** Email Spam Classifier Using Logistic Regression  
**Domain:** Machine Learning / Natural Language Processing  
**Algorithm:** Logistic Regression  
**Feature Extraction:** TF-IDF  
**Environment:** Python / Jupyter Notebook
