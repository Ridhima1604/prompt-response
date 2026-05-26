# Prompt – Diabetes Prediction System

## Context and Role

As a Machine Learning Engineer and Full Stack Developer with a focus on healthcare analytics, your task is to build a complete Diabetes Prediction System using the Pima Indians Diabetes Dataset.

The project should cover the full workflow—from training the machine learning model to building the backend and frontend. It must include a machine learning pipeline, REST API backend, responsive dashboard UI, database integration, user authentication, prediction history, visual analytics, and deployment setup.

The aim is to create a production-ready healthcare platform that can predict whether a patient may have diabetes based on medical details. The system should also explain prediction results clearly, save patient prediction records, and provide an easy-to-use interface for doctors, students, and healthcare staff.

---

## Objective

Build a complete end-to-end Diabetes Prediction System that can:

- Uses the Pima Indians Diabetes Dataset for prediction
- Cleans and preprocesses patient health data
- Performs EDA and feature visualization
- Trains and compares multiple supervised machine learning models
- Selects and saves the best-performing model
- Exposes predictions through backend APIs
- Builds frontend forms and dashboards
- Stores users and prediction history securely
- Displays analytics and risk trends
- Handles validations and errors gracefully
- Supports deployment locally and on cloud platforms

---

## Dataset Requirements

### Dataset

Use the Pima Indians Diabetes Dataset

### Input Features

- Pregnancies
- Glucose
- Blood Pressure
- Skin Thickness
- Insulin
- BMI
- Diabetes Pedigree Function
- Age

### Outcome

- `0 = Non-Diabetic`
- `1 = Diabetic`

---

## Data Processing Requirements

### Data Cleaning

Perform preprocessing before model training.

### Tasks

- Replace invalid zero values in:
  - Glucose
  - Blood Pressure
  - Skin Thickness
  - Insulin
  - BMI
- Handle missing/null values
- Remove duplicate records
- Detect and handle outliers

### Data Processing Techniques

Apply the following techniques:

#### Missing Value Handling

- Median imputation
- Null value detection

#### Outlier Detection

- Interquartile Range (IQR)
- Box plot analysis

#### Feature Scaling

- Standardization using StandardScaler
- Optional normalization using MinMaxScaler

#### Data Splitting

- Train / validation / test split

#### Feature Relationship Analysis

- Correlation matrix
- Heatmap analysis

#### Class Imbalance Handling (Optional)

- SMOTE

#### Data Formatting

- Ensure numerical consistency
- Convert data into model-ready format

---

## Exploratory Data Analysis

Include:

- Histograms
- Heatmap
- Box plots
- Class balance chart
- Feature importance graph

---

## Machine Learning Requirements

### Train and Compare Models

Implement:

- Logistic Regression
- Decision Tree
- Random Forest
- Support Vector Machine
- K-Nearest Neighbors
- Gradient Boosting

### Hyperparameter Tuning

Use:

- GridSearchCV
- RandomizedSearchCV

### Evaluation Metrics

Measure:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC
- Confusion Matrix

---

## Backend Requirements (FastAPI / Flask)

Use:

- Python
- FastAPI
- REST API

### Authentication

Implement:

- JWT token authentication

---

## Frontend Requirements

Use:

- HTML
- Tailwind CSS
- React Router DOM
- Chart.js
- Axios

---

## Database Requirements

Use:

- PostgreSQL
- MongoDB

---

## Error Handling

The system must handle errors gracefully across machine learning, backend, frontend, and database.

### Dataset Errors

Handle:

- Missing dataset file
- Invalid CSV format
- Empty dataset
- Duplicate records
- Missing required columns

### Model Training Errors

Handle:

- Training failure
- Invalid preprocessing output
- Hyperparameter tuning failure
- Model save/load failure

### Backend API Errors

Handle:

- Invalid request payload
- Missing required fields
- Invalid feature values
- Authentication failure
- Token expiration
- Internal server errors

Return structured JSON:

```json
{
  "status": "error",
  "message": "Invalid glucose value"
}
```

### Frontend Errors

Handle:

- Empty form submission
- Invalid numeric input
- Failed API request
- Network/server unavailable
- Loading state issues

Display:

- Validation errors
- Error alerts
- Success confirmation

### Database Errors

Handle:

- Database connection failure
- Insert/update failure
- Duplicate user registration
- Prediction history retrieval failure

---

## Folder Structure

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
├── requirements.txt
├── README.md
```

---

## Performance and Scalability

Ensure the system:

- Loads quickly
- Handles multiple requests efficiently
- Supports future scaling
- Optimizes model loading
- Maintains responsive UI performance

---

## Expected Output

The final system should deliver:

- Cleaned dataset
- EDA visualizations
- Multiple trained models
- Best model saved
- REST API backend
- Frontend dashboard
- Prediction history
- Authentication
- Analytics
