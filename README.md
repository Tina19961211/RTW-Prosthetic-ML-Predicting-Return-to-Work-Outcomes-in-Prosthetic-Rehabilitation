# RTW-Prosthetic-ML-Predicting-Return-to-Work-Outcomes-in-Prosthetic-Rehabilitation
An explainable machine learning framework for predicting return-to-work (RTW) outcomes among individuals with limb loss, integrating psychosocial, functional, and demographic variables with SHAP-based model interpretability.
# Overview
Return to work (RTW) is one of the most meaningful indicators of successful rehabilitation following limb amputation. Beyond economic independence, employment is associated with improved self-esteem, functional recovery, and long-term quality of life.
This project develops and evaluates supervised machine learning models, Logistic Regression and Random Forest — to predict whether individuals with limb loss return to employment. The pipeline incorporates rigorous multicollinearity diagnostics, Leave-One-Out Cross-Validation (LOOCV) suited to small clinical samples, and SHAP-based explainability to ensure findings are clinically interpretable.

# Repository Structure
RTW-Prosthetic-ML/


├── RTW-GMS-code.ipynb


├── GMS_dataset.xlsx


├── README.md


├── requirements.txt


└── outputs/


├── confusion_matrix.png


├── shap_importance.png


├── radar_chart.png


└── shap_force_plot.html

# Dataset
Sample size: 44 participants
Population: Individuals with limb amputation
Target variable: Return to Work (Yes / No)
Source: the data was collected during the Amputee Coalition National Conference
Key variable domains:

Demographic: Age, Gender, Race, Education, Employment Status
Clinical: Level of Amputation, Time Since Amputation, Pain (NRS), Fear-Avoidance (FFABQ)
Psychosocial: Satisfaction With Life (SWLS), Growth Mindset (GMS), Anxiety (GAD-7), Depression (PHQ-9), Social Support (MSPSS), Loneliness (UCLA)
Functional: Prosthetic Mobility (PLUS-M)

The dataset is lightweight (n = 44) and is stored directly in the repository. If the data contains identifiable participant information, ensure ethical approval permits public sharing or keep the repository private.

# Methods
Preprocessing: Gender binary encoding, amputation date converted to continuous Years_Since_Amputation, age binned and one-hot encoded, race and employment status one-hot encoded, feature scaling via StandardScaler.
Multicollinearity Diagnostics (VIF): Prior to model fitting, Variance Inflation Factors were computed for all predictors. All features returned VIF values below 5, confirming no problematic multicollinearity. The full feature set was retained for model training.
Model Evaluation: Leave-One-Out Cross-Validation (LOOCV) was used given the small sample size (n = 44). Metrics reported: Accuracy, F1 (binary), F1 (macro), ROC-AUC.
Explainability: SHAP (SHapley Additive exPlanations) values were computed for the final Random Forest model to identify the most influential predictors and their directional effects on RTW predictions.

# Key Results
Logistic Regression= Accuracy: ~0.75
Random Forest= Accuracy: ~0.75, higher F1 and ROC-AUC
Top predictors of RTW (SHAP):

Satisfaction With Life (SWLS)
Growth Mindset (GMS)
Prosthetic Mobility (PLUS-M)

These findings support a biopsychosocial model of rehabilitation: successful return to work is jointly shaped by psychological well-being and functional mobility, not physical recovery alone.

# Installation
git clone https://github.com/<your-username>/RTW-Prosthetic-ML.git
cd RTW-Prosthetic-ML
pip install -r requirements.txt
jupyter notebook GMS_RTW_model.ipynb
requirements.txt:
pandas, numpy, scikit-learn, xgboost, shap, matplotlib, seaborn, statsmodels, openpyxl, jupyter

# Citation
If you use this code or dataset in your research, please cite:
Author: Tina
Title: RTW-Prosthetic-ML: Predicting Return-to-Work Outcomes in Prosthetic Rehabilitation
Year: 2025
URL: https://github.com/<your-username>/RTW-Prosthetic-ML


# Acknowledgements
This work was conducted as part of a doctoral research project in prosthetic rehabilitation. All participant data were collected under appropriate ethical oversight.
