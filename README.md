Project Overview

This project aims to predict heart disease using machine learning models. It involves data preprocessing, exploratory data analysis (EDA), feature selection, model training, and API deployment using Flask.

Steps Implemented

1. Data Preprocessing

The dataset was loaded from UCI_Heart_Disease_Data.csv.

Missing values in numerical columns were replaced with their median values.

Categorical variables were imputed using their most frequent values.

Label Encoding was applied to categorical features.

2. Exploratory Data Analysis (EDA)

Statistical summaries and unique values of categorical features were analyzed.

The correlation matrix was plotted to identify relationships between features.

Data imbalance was handled using SMOTE (Synthetic Minority Over-sampling Technique).

Visualizations were generated to analyze relationships between age, cholesterol levels, and disease severity.

3. Feature Selection

Feature importance was analyzed using Random Forest.

SelectKBest method was used to select the most significant features for prediction.

4. Model Building & Evaluation

Multiple models were trained and evaluated:

Random Forest Classifier

XGBoost Classifier

The best model was selected based on accuracy and classification reports.

Hyperparameter tuning was performed using GridSearchCV to optimize the XGBoost model.

The confusion matrix was plotted for model evaluation.

5. Model Deployment

The best model was saved as a pickle file (xgb_model.pkl).

A Flask API was created to serve predictions.

API testing was conducted using Postman.

API Usage (Postman)

Endpoint:

POST /predict

Request Body (JSON):

{
    "age": 45,
    "cp": 2,
    "thalach": 150,
    "exang": 1,
    "oldpeak": 2.3,
    "sex": 1,
    "trestbps": 160,
    "chol": 230,
    "fbs": 0,
    "restecg": 1,
    "slope": 1,
    "ca": 3,
    "thal": 1,
    "dataset": 0
}

Response:

{
    "prediction": 3
}

Repository Structure

|-- data/
|   |-- UCI_Heart_Disease_Data.csv
|-- models/
|   |-- xgb_model.pkl
|-- src/
|   |-- data_preprocessing.py
|   |-- model_training.py
|   |-- feature_selection.py
|   |-- api.py
|-- README.md
|-- requirements.txt

Installation

To run the project locally, install the dependencies:

pip install -r requirements.txt

Run the Flask API:

python api.py

Conclusion

This project successfully predicts heart disease using machine learning models. The best-performing model was deployed as an API, allowing real-time predictions.
