# ✈️ Airline Flight Booking Prediction

A machine learning project that predicts whether an airline customer will complete a **flight booking** using customer booking and travel-related characteristics.

The project demonstrates an end-to-end machine learning workflow, including **exploratory data analysis, data preprocessing, feature engineering, categorical encoding, predictive modeling, cross-validation, model evaluation, and feature-importance analysis**.

<img width="1401" height="790" alt="Screenshot 2026-10-05 at 2 38 34 PM" src="https://github.com/user-attachments/assets/0d85234f-5eb0-47a4-b8ee-902aefc8b017" />


---

## 📌 Project Overview

Airlines can use predictive analytics to identify customers who are more likely to complete a booking and engage them proactively before their journey.

This project uses historical airline customer booking data to build a **Random Forest classification model** that predicts the target variable:

```text
booking_complete
```

Where:

* `0` = Booking not completed
* `1` = Booking completed

The analysis focuses on understanding both **how accurately the model predicts booking completion** and **which variables contribute most to its predictions**.

---

## 🎯 Objectives

The main objectives of this project are to:

* Explore and understand airline customer booking data.
* Identify data-quality issues and patterns in customer behaviour.
* Prepare categorical and numerical variables for machine learning.
* Engineer additional features to improve predictive performance.
* Build a Random Forest classification model.
* Evaluate model performance using multiple classification metrics.
* Validate model robustness using stratified cross-validation.
* Identify the most important predictors of booking completion.
* Translate machine learning findings into actionable business insights.

---

## 📊 Dataset

The dataset contains **50,000 airline customer booking records** and **14 original variables** describing booking and travel behaviour.

### Target Variable

| Variable           | Description                                               |
| ------------------ | --------------------------------------------------------- |
| `booking_complete` | Indicates whether the customer completed a flight booking |

### Key Features

The dataset includes variables related to:

* Sales channel
* Trip type
* Flight day
* Flight hour
* Flight duration
* Route
* Booking origin
* Purchase lead time
* Length of stay
* Number of passengers
* Additional baggage preference
* Preferred seat preference
* In-flight meal preference

---

## 🔍 Exploratory Data Analysis

The analysis includes:

* Dataset structure and data types
* Missing-value analysis
* Duplicate-value analysis
* Descriptive statistics
* Target-variable distribution
* Categorical-variable analysis
* Numerical-variable analysis
* Correlation analysis
* Booking completion rates across customer and flight characteristics

---

## 🛠️ Data Preprocessing & Feature Engineering

The following preprocessing steps were performed:

### Data Cleaning

* Checked for missing values.
* Checked for duplicate records.
* Reviewed data types and categorical variables.
* Converted `flight_day` into a numerical representation.

### Feature Engineering

Two additional features were created:

**Weekend indicator**

```text
is_weekend
```

Identifies whether the customer's flight falls on Saturday or Sunday.

**Total additional services**

```text
total_extra_services
```

Combines:

* Extra baggage
* Preferred seat
* In-flight meals

to represent the number of additional services selected by the customer.

### Categorical Encoding

Categorical variables were transformed using **One-Hot Encoding** with unknown categories handled safely during prediction.

---

## 🤖 Machine Learning Model

### Random Forest Classifier

A Random Forest classification algorithm was selected because it:

* Handles nonlinear relationships effectively.
* Works well with mixed feature types after preprocessing.
* Is relatively robust to noise.
* Provides feature-importance information.
* Is suitable for interpreting which variables contribute to predictive performance.

### Model Configuration

```python
RandomForestClassifier(
    n_estimators=100,
    random_state=42,
    class_weight="balanced",
    n_jobs=-1
)
```

### Data Split

The dataset was divided using an **80/20 stratified train-test split**.

Stratification was applied to preserve the proportion of booking-completion classes across the training and testing datasets.

---

## 📈 Model Evaluation

The model was evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* ROC-AUC
* Confusion Matrix
* 5-fold Stratified Cross-Validation

### Why multiple metrics?

The target variable is imbalanced, so accuracy alone may not provide a complete picture of model performance.

Precision and recall help evaluate how effectively the model identifies customers who complete bookings, while ROC-AUC measures the model's ability to distinguish between booking and non-booking customers.

### Results

> Replace the values below with the final results from the notebook.

| Metric    | Test Set | 5-Fold CV |
| --------- | -------: | --------: |
| Accuracy  |   XX.XX% |    XX.XX% |
| Precision |   XX.XX% |    XX.XX% |
| Recall    |   XX.XX% |    XX.XX% |
| F1 Score  |   XX.XX% |    XX.XX% |
| ROC-AUC   |   XX.XX% |    XX.XX% |

---

## 📊 Feature Importance

Random Forest feature importance was used to identify the variables that contributed most strongly to the model's predictions.

The analysis provides insight into which booking, customer, and flight characteristics are most useful for predicting booking completion.

### Top Predictive Features

> Replace this section with the actual top features from the final model.

1. **Feature 1** — XX.XX%
2. **Feature 2** — XX.XX%
3. **Feature 3** — XX.XX%
4. **Feature 4** — XX.XX%
5. **Feature 5** — XX.XX%

The complete feature-importance results are available in:

```text
outputs/feature_importance.csv
```

---

## 💡 Business Insights

The model demonstrates how predictive analytics can help airlines move from reactive to proactive customer engagement.

Potential applications include:

* Identifying customers with a higher probability of completing a booking.
* Prioritizing customers for targeted marketing campaigns.
* Personalizing offers based on customer and booking characteristics.
* Supporting data-driven customer acquisition strategies.
* Improving the timing and targeting of promotional communications.

### Important Consideration

Feature importance indicates which variables are useful for prediction; it **does not establish causal relationships**. Model performance should also be monitored and validated before deployment in a production environment.

---

## 📁 Project Structure

```text
airline-flight-booking-prediction/
│
├── README.md
│
├── notebooks/
│   ├── 01_getting_started.ipynb
│   └── 02_booking_prediction_analysis.ipynb
│
├── data/
│   └── customer_booking.csv
│
├── scripts/
│   └── booking_prediction.py
│
├── outputs/
│   ├── feature_importance.csv
│   ├── top_10_feature_importance.png
│   └── confusion_matrix.png
│
├── presentation/
│   └── airline_booking_prediction_summary.pptx
│
├── requirements.txt
│
└── .gitignore
```

---

## 💻 Technologies & Libraries

### Programming Language

* Python

### Data Analysis

* Pandas
* NumPy

### Visualization

* Matplotlib
* Seaborn

### Machine Learning

* Scikit-learn
* Random Forest
* One-Hot Encoding
* Stratified Cross-Validation
* Classification Metrics

### Presentation

* Microsoft PowerPoint

---

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/Aleem-mja/airline-flight-booking-prediction.git
```

Navigate to the project directory:

```bash
cd airline-flight-booking-prediction
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate the environment.

### Windows

```bash
venv\Scripts\activate
```

### macOS/Linux

```bash
source venv/bin/activate
```

Install the required packages:

```bash
pip install -r requirements.txt
```

---

## ▶️ Running the Project

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
notebooks/02_booking_prediction_analysis.ipynb
```

Run the notebook cells sequentially.

---

## 📦 Requirements

Example `requirements.txt`:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
jupyter
openpyxl
```

---

## 📌 Key Skills Demonstrated

This project demonstrates practical experience in:

* Python
* Pandas
* NumPy
* Exploratory Data Analysis
* Data Cleaning
* Data Preprocessing
* Feature Engineering
* Categorical Encoding
* Predictive Modeling
* Classification
* Random Forest
* Scikit-learn
* Cross-Validation
* Model Evaluation
* Feature Importance
* Data Visualization
* Business Analytics
* Machine Learning Interpretation

---

## 👤 Author

**Abdul Aleem Jabeer**

Data Analyst | Data Science & Machine Learning

This project is part of my data analytics and machine learning portfolio, demonstrating an end-to-end approach to solving a real-world customer prediction problem.

---

## ⭐ Project Highlights

**50,000+** customer records analyzed
**14** original features
**100-tree** Random Forest model
**5-fold** stratified cross-validation
**Multiple** classification metrics
**Top 10** predictive features identified
**End-to-end** machine learning workflow

<img width="1401" height="790" alt="Screenshot 2026-10-05 at 2 38 34 PM" src="https://github.com/user-attachments/assets/0d85234f-5eb0-47a4-b8ee-902aefc8b017" />

