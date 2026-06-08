# EEG Psychiatric Disorder Classifier

A full-stack machine learning web application that predicts psychiatric disorders from EEG (Electroencephalogram) signal data. Built to assist in early detection of mental health conditions by analyzing brainwave patterns.

---

## Overview

Mental health conditions are often diagnosed late due to the complexity of symptoms and limited access to specialists. This project automates the classification of psychiatric disorders using EEG signal features and a trained ML pipeline, providing a fast, data-driven second opinion through a web interface.

---

## Features

- Classifies EEG data into psychiatric disorder categories (main disorder + specific disorder)
- Benchmarks 4 ML models: Random Forest, SVM, Logistic Regression, Decision Tree
- Role-based authentication (Admin / User) with secure password hashing (bcrypt)
- CSV batch prediction — upload a file, get results for multiple patients at once
- EDA dashboard showing dataset distributions and feature insights
- Model performance comparison page (Accuracy, Precision, Recall, F1-Score)
- Model persistence using `joblib` — no retraining needed on restart

---

## Tech Stack

| Layer | Technology |
|---|---|
| Backend | Python, Flask |
| ML | Scikit-learn, Pandas, NumPy |
| Models | Random Forest, SVM, Logistic Regression, Decision Tree |
| Frontend | HTML, CSS (Jinja2 templates) |
| Database | SQLite, Flask-Login |
| Other | joblib (model persistence), SMOTE, RFE |

---

## Model Performance

| Model | Accuracy |
|---|---|
| Random Forest | Best performer (selected for production) |
| SVM | Competitive on balanced classes |
| Logistic Regression | Baseline comparison |
| Decision Tree | Interpretable, slightly lower accuracy |

> Feature selection was performed using Recursive Feature Elimination with Random Forest (RFE-RF) to reduce noise and improve generalization.

---

## Project Structure

```
eeg-psychiatric-disorder-classifier/
│
├── app.py                          # Main Flask application
├── ml_classifiers.py               # ML model training and evaluation
├── create_admin.py                 # Admin user setup script
│
├── *.pkl / *.joblib                # Saved trained models
├── EEG.machinelearning_data_BRMH.csv  # Dataset
├── test1.csv                       # Sample test input
│
├── templates/
│   ├── base.html
│   ├── home.html
│   ├── login.html
│   ├── register.html
│   ├── prediction.html
│   ├── prediction_results.html
│   ├── classification_results.html
│   ├── classifier_selection.html
│   ├── eda.html
│   └── performance_comparison.html
│
└── README.md
```

---

## Getting Started

### Prerequisites

```bash
Python 3.10+
pip
```

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/gundaganitejaswini05/eeg-psychiatric-disorder-classifier.git
cd eeg-psychiatric-disorder-classifier

# 2. Install dependencies
pip install flask flask-login scikit-learn pandas numpy joblib bcrypt

# 3. Set up admin user
python create_admin.py

# 4. Run the application
python app.py
```

### Usage

1. Open your browser and go to `http://localhost:5000`
2. Register or log in with admin credentials
3. Upload a CSV file with EEG features for batch prediction
4. View disorder classification results and model performance comparison

---

## Dataset

- Source: BRMH EEG Dataset (`EEG.machinelearning_data_BRMH.csv`)
- Contains EEG signal features labeled with psychiatric disorder categories
- Preprocessing includes EDA, class imbalance handling (SMOTE), and feature selection (RFE)

---

## Author

**Tejaswini Gundagani**
B.Tech Information Technology — CMR Technical Campus (2026)
[LinkedIn](https://linkedin.com/in/tejaswinigundagani) | [GitHub](https://github.com/gundaganitejaswini05)

---

## License

This project is for academic and research purposes.
