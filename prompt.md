# Diabetes Prediction System

## Overview

The **Diabetes Prediction System** is a full-stack machine learning healthcare analytics platform built using the **Pima Indians Diabetes Dataset**.

The system predicts whether a patient is diabetic based on diagnostic measurements and provides:

- Diabetes prediction
- Probability score
- Risk level
- Visual analytics dashboard
- Prediction history
- Authentication
- Database storage
- Deployment support

This platform can be used by:

- Doctors
- Healthcare staff
- Students
- Researchers

---

# Objective

Build a production-ready end-to-end healthcare prediction system that:

- Uses the Pima Indians Diabetes Dataset
- Cleans and preprocesses data
- Performs EDA
- Trains multiple ML models
- Selects the best model
- Saves the trained model
- Exposes predictions through REST APIs
- Builds responsive frontend dashboard
- Stores users and prediction history
- Handles validation/errors
- Supports cloud deployment

---

# Dataset Information

## Dataset

**Pima Indians Diabetes Dataset**

## Input Features

| Feature | Description |
|---|---|
| Pregnancies | Number of pregnancies |
| Glucose | Plasma glucose concentration |
| BloodPressure | Diastolic blood pressure |
| SkinThickness | Triceps skin fold thickness |
| Insulin | 2-Hour serum insulin |
| BMI | Body Mass Index |
| DiabetesPedigreeFunction | Genetic diabetes score |
| Age | Patient age |

## Target

| Value | Meaning |
|---|---|
| 0 | Non-Diabetic |
| 1 | Diabetic |

---

# Data Preprocessing

## 1. Data Cleaning

### Replace invalid zero values

For these columns:

- Glucose
- BloodPressure
- SkinThickness
- Insulin
- BMI

Replace `0` with median values.

### Handle Missing Values

- Detect null values
- Median imputation

### Remove Duplicates

- Drop duplicate rows

### Outlier Detection

Use **IQR method**

Formula:

Q1 = 25th percentile  
Q3 = 75th percentile

IQR = Q3 - Q1

Outlier limits:

Lower = Q1 - 1.5 × IQR

Upper = Q3 + 1.5 × IQR

---

# Feature Engineering

- Standardization using `StandardScaler`
- Correlation analysis
- Train/Validation/Test split
- Optional SMOTE for class imbalance

Recommended split:

- Train → 70%
- Validation → 15%
- Test → 15%

---

# Exploratory Data Analysis

Perform:

## Histograms

Check feature distribution.

## Heatmap

Feature correlation matrix.

## Boxplots

Identify outliers.

## Class Balance Chart

Check diabetic vs non-diabetic.

## Feature Importance Graph

For tree-based models.

---

# Machine Learning Models

Train and compare:

## Logistic Regression

Good baseline.

## Decision Tree

Easy interpretation.

## Random Forest

Better performance.

## Support Vector Machine

Works well with scaling.

## KNN

Distance-based.

## Gradient Boosting

Strong ensemble model.

## XGBoost (Optional)

Advanced boosting.

---

# Hyperparameter Tuning

Use:

- GridSearchCV
- RandomizedSearchCV

Example:

## Random Forest

Parameters:

- n_estimators
- max_depth
- min_samples_split

---

# Evaluation Metrics

Compare:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC
- Confusion Matrix

Priority:

## Minimize False Negatives

Because missing diabetes is risky.

Focus on:

- High Recall
- High ROC-AUC

---

# Best Model Saving

Save trained model:

```python
joblib.dump(model, "saved_model.pkl")
```

Save scaler:

```python
joblib.dump(scaler, "scaler.pkl")
```

---

# Backend

Framework:

- FastAPI
- Flask (alternative)

---

# API Endpoints

## POST /train-model

Train and save model.

---

## POST /predict

Predict diabetes.

Request:

```json
{
  "pregnancies": 2,
  "glucose": 150,
  "blood_pressure": 85,
  "skin_thickness": 32,
  "insulin": 130,
  "bmi": 33.2,
  "dpf": 0.62,
  "age": 45
}
```

Response:

```json
{
  "prediction": "Diabetic",
  "probability": "82%",
  "risk_level": "High"
}
```

---

## GET /metrics

Returns:

- accuracy
- recall
- F1
- ROC-AUC

---

## GET /history

Returns prediction history.

---

## GET /model-info

Returns:

- model name
- version
- training date

---

## POST /register

User registration.

---

## POST /login

JWT authentication.

---

# Validation

Validate:

- Pregnancies >= 0
- Glucose > 0
- BloodPressure > 0
- BMI > 0
- Age > 0

Handle:

- invalid payload
- missing fields
- server errors

---

# Authentication

JWT Token-based login

Flow:

Register → Login → Receive Token → Access APIs

---

# Frontend

Framework:

- React
- Angular
- Streamlit (optional)

---

# Pages

## Login/Register

User authentication

---

## Dashboard

Show:

- Total predictions
- Accuracy cards
- Charts
- Risk trends

---

## Prediction Form

Fields:

- Pregnancies
- Glucose
- Blood Pressure
- Skin Thickness
- Insulin
- BMI
- DPF
- Age

---

## Model Metrics

Display:

- Accuracy
- Recall
- ROC curve

---

## Prediction History

Show previous records

---

## Admin Panel

Manage:

- users
- model versions
- prediction logs

---

# UI Features

- Responsive mobile + desktop
- Form validation
- Loading state
- Success alerts
- Error messages

---

# Database

Use:

- PostgreSQL
- MongoDB
- SQLite

---

# Tables

## Users

| Column | Type |
|---|---|
| id | Integer |
| name | String |
| email | String |
| password | String |

---

## Predictions

| Column | Type |
|---|---|
| id | Integer |
| user_id | FK |
| pregnancies | Integer |
| glucose | Float |
| blood_pressure | Float |
| skin_thickness | Float |
| insulin | Float |
| bmi | Float |
| dpf | Float |
| age | Integer |
| prediction | String |
| probability | Float |
| created_at | Timestamp |

---

## Model Logs

| Column | Type |
|---|---|
| id | Integer |
| version | String |
| accuracy | Float |
| recall | Float |
| created_at | Timestamp |

---

# Project Folder Structure

```bash
diabetes_prediction_project/
│
├── backend/
│   ├── app.py
│   ├── routes/
│   ├── auth/
│   ├── models/
│   ├── database/
│
├── ml/
│   ├── train.py
│   ├── preprocess.py
│   ├── predict.py
│   ├── saved_model.pkl
│
├── frontend/
│   ├── src/components/
│   ├── pages/
│   ├── charts/
│
├── dataset/
│
├── requirements.txt
│
├── README.md
```

---

# Dependencies

```txt
pandas
numpy
matplotlib
seaborn
scikit-learn
fastapi
uvicorn
joblib
sqlalchemy
jwt
react
```

---

# Deployment

## Localhost

Backend:

```bash
uvicorn app:app --reload
```

Frontend:

```bash
npm start
```

---

## Docker

Create Dockerfile

Run:

```bash
docker build -t diabetes-app .
docker run -p 8000:8000 diabetes-app
```

---

## Cloud Deployment

Supported:

- Render
- Railway
- Vercel

---

# Expected Output

Project delivers:

- Clean dataset
- EDA charts
- Trained ML models
- Best model saved
- Prediction REST API
- Responsive frontend dashboard
- Authentication
- Prediction history
- Database integration
- Deployment ready system

---

# Final Example

Input:

Glucose = 165  
BMI = 34.8  
Age = 42

Output:

```json
{
  "prediction": "Diabetic",
  "probability": "87%",
  "risk_level": "High"
}
```

---

# Future Improvements

- SHAP explainability
- Email report generation
- PDF export
- Doctor recommendation
- Real-time analytics
- Multi-language support

---

# Conclusion

This project combines:

- Machine Learning
- Healthcare analytics
- REST APIs
- Database management
- Frontend development
- Deployment

to build a complete **Diabetes Prediction System** suitable for real-world healthcare prediction.
