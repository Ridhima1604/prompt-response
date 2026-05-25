
#  Diabetes Prediction System

A complete end-to-end **Machine Learning + FastAPI + Frontend Dashboard** project that predicts whether a patient is diabetic using the **Pima Indians Diabetes Dataset**.

This system is built for doctors, students, and healthcare staff to quickly assess diabetes risk based on patient health measurements, view prediction history, and analyze model performance through interactive dashboards.

---

## deployed link
https://stupendous-hotteok-4b75eb.netlify.app/

##  Features

###  Machine Learning Pipeline
- Data cleaning and preprocessing
- Exploratory Data Analysis (EDA)
- Feature scaling and engineering
- Multiple ML model training
- Hyperparameter tuning
- Best model selection and saving

###  Prediction API
- REST API using **FastAPI / Flask**
- Predict diabetes from user input
- Returns prediction + probability + risk level
- JWT authentication
- Model metrics endpoints
- Prediction history API

###  Frontend Dashboard
- Login / Register pages
- Diabetes prediction form
- Model metrics dashboard
- Prediction history
- Risk trend charts
- Responsive UI for mobile + desktop

###  Database Integration
- Store users
- Store predictions
- Track model versions and logs

###  Deployment Ready
- Localhost
- Docker
- Render / Railway / Vercel

---

#  Dataset

Dataset used: **Pima Indians Diabetes Dataset**

### Input Features

- Pregnancies
- Glucose
- Blood Pressure
- Skin Thickness
- Insulin
- BMI
- Diabetes Pedigree Function
- Age

### Target

- **0 → Non-Diabetic**
- **1 → Diabetic**

---

#  Data Preprocessing

### Data Cleaning
- Replace invalid zero values in:
  - Glucose
  - Blood Pressure
  - Skin Thickness
  - Insulin
  - BMI
- Median imputation
- Remove duplicates
- Handle null values
- Outlier detection using IQR

### Feature Engineering
- Standardization
- Correlation analysis
- Train / Validation / Test split
- Optional SMOTE for class balancing

---

#  Exploratory Data Analysis

Visualizations included:

- Histograms
- Correlation heatmap
- Box plots
- Class distribution chart
- Feature importance graphs

---

#  Machine Learning Models

Models trained and compared:

- Logistic Regression
- Decision Tree
- Random Forest
- Support Vector Machine
- K-Nearest Neighbors
- Gradient Boosting
- XGBoost *(optional)*

### Hyperparameter Tuning
- GridSearchCV
- RandomizedSearchCV

### Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC
- Confusion Matrix

### Priority
Focus is on:

 Minimizing false negatives  
 Maximizing recall  
 Improving ROC-AUC

---

#  Backend API

Built using **FastAPI / Flask**

## Endpoints

### POST `/train-model`
Train and save the model

### POST `/predict`
Predict diabetes

### GET `/metrics`
Fetch model metrics

### GET `/history`
Fetch prediction history

### GET `/model-info`
Model details

### POST `/register`
Register new user

### POST `/login`
User authentication

---

## Example Prediction Response

```json
{
  "prediction": "Diabetic",
  "probability": "87%",
  "risk_level": "High"
}
```

---

#  Frontend Pages

- Login
- Register
- Dashboard
- Prediction Form
- Model Metrics
- Prediction History
- Admin Panel

### Prediction Form Fields

- Pregnancies
- Glucose
- Blood Pressure
- Skin Thickness
- Insulin
- BMI
- DPF
- Age

---

#  Dashboard Features

- Accuracy cards
- Charts
- Risk trends
- Recent predictions
- Form validation
- Loading indicators
- Error handling

---

#  Database Schema

## Users

| Field | Type |
|------|------|
| id | Integer |
| name | String |
| email | String |
| password | String |

---

## Predictions

| Field | Type |
|------|------|
| id | Integer |
| user_id | Integer |
| input fields | JSON |
| prediction | String |
| probability | String |
| created_at | DateTime |

---

## Model Logs

| Field | Type |
|------|------|
| id | Integer |
| version | String |
| accuracy | Float |
| recall | Float |
| created_at | DateTime |

---

#  Project Structure

```bash
diabetes_prediction_project/
│
├── backend/
│   ├── app.py
│   ├── routes/
│   ├── auth/
│   ├── models/
│   └── database/
│
├── ml/
│   ├── train.py
│   ├── preprocess.py
│   ├── predict.py
│   └── saved_model.pkl
│
├── frontend/
│   ├── src/components/
│   ├── pages/
│   └── charts/
│
├── dataset/
│
├── requirements.txt
└── README.md
```

---

#  Dependencies

```txt
pandas
numpy
matplotlib
seaborn
scikit-learn
fastapi
uvicorn
joblib
react / angular / streamlit
```

---

#  Run Locally

## Clone repository

```bash
git clone <repository-url>
cd diabetes_prediction_project
```

## Install dependencies

```bash
pip install -r requirements.txt
```

## Start backend

```bash
uvicorn backend.app:app --reload
```

## Start frontend

```bash
npm install
npm start
```

---

#  Docker Deployment

Build image:

```bash
docker build -t diabetes-prediction .
```

Run:

```bash
docker run -p 8000:8000 diabetes-prediction
```

---

#  Deployment Platforms

You can deploy on:

- Render
- Railway
- Vercel
- Docker
- Localhost

---

#  Final Output

Example:

```txt
Prediction: Diabetic
Probability: 87%
Risk Level: High
```

---

#  Project Goal

The goal of this project is to provide an accurate and user-friendly diabetes prediction system that helps identify diabetes risk early using machine learning and healthcare analytics.

It combines:

- Data Science
- Machine Learning
- Backend APIs
- Frontend Dashboard
- Database Management
- Deployment

into one complete production-ready healthcare analytics platform.

---

#  Author

**Ridhima Pandey**
````

This is ready for GitHub as `README.md`.
