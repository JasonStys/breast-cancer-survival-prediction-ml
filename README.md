# Breast Cancer Survival Prediction ML

An educational machine learning project that explores breast cancer survival prediction using clinical and demographic patient data. The project trains and evaluates classification models to predict survival status and regression models to estimate survival months.

> **Important:** This project is for coursework and portfolio demonstration only. It is not a medical device, diagnostic tool, or substitute for professional medical judgment.

## Project Overview

This project was completed for CS471 and focuses on applying supervised machine learning to a healthcare dataset. The notebook uses patient features such as age, race, marital status, cancer stage, tumor size, hormone receptor status, and lymph node information to predict two outcomes:

1. Survival status, represented as `Alive` or `Dead`
2. Estimated survival duration, represented as `Survival Months`

The project includes exploratory data analysis, preprocessing pipelines, model training, hyperparameter tuning, model evaluation, feature importance analysis, and an interactive prediction function that accepts partial user input.

## Key Features

- Loads and cleans a breast cancer survival dataset
- Converts survival status into a binary classification target
- Separates categorical and numerical features
- Uses one hot encoding for categorical variables
- Uses standard scaling for numerical variables
- Handles missing or partial user input through pipeline based preprocessing
- Trains classification models for survival status prediction
- Trains regression models for survival month estimation
- Uses hyperparameter tuning with randomized and grid search methods
- Saves trained models with Joblib
- Provides an interactive prediction workflow for user supplied patient feature values
- Includes visual analysis with histograms, box plots, feature importance charts, logistic regression curves, and decision tree diagrams

## Dataset

The project uses the public breast cancer dataset by Reihaneh Namdari from Kaggle. The notebook expects the dataset file to be named:

```text
Breast_Cancer.csv
```

Place the file in the same directory as the notebook before running the project.

The uploaded report and notebook describe 14 predictor features:

```text
Age
Race
Marital Status
T Stage
N Stage
6th Stage
differentiate
Grade
A Stage
Tumor Size
Estrogen Status
Progesterone Status
Regional Node Examined
Reginol Node Positive
```

The target columns are:

```text
Survival_Status
Survival Months
```

## Models Used

### Classification Models

- Random Forest Classifier
- Logistic Regression

These models predict whether a patient record is classified as surviving or not surviving.

### Regression Models

- Random Forest Regressor
- Linear Regression

These models estimate the number of survival months.

## Preprocessing Pipeline

The project uses scikit-learn pipelines to keep preprocessing consistent between training and prediction.

Categorical features are processed with:

```text
SimpleImputer
OneHotEncoder
```

Numerical features are processed with:

```text
SimpleImputer
StandardScaler
```

The full preprocessing workflow is managed with:

```text
ColumnTransformer
Pipeline
```

This design makes the project easier to reuse and allows the prediction function to work even when only some input features are provided.

## Model Evaluation

The notebook evaluates classification performance with precision, recall, F1 score, and accuracy. It evaluates regression performance with MAE, RMSE, and R squared.

The final training output in the notebook reports the following tuned model results:

| Model | Task | Accuracy | MAE | RMSE | R squared |
|---|---:|---:|---:|---:|---:|
| Random Forest Classifier | Classification | 0.84 | N/A | N/A | N/A |
| Logistic Regression | Classification | 0.78 | N/A | N/A | N/A |
| Random Forest Regressor | Regression | N/A | 18.42 | 22.52 | 0.051 |
| Linear Regression | Regression | N/A | 18.41 | 22.47 | 0.056 |

Classification performed better than regression in this project. The regression results show that estimating survival months is more difficult with the available features, which makes it a good area for future improvement.

## Visualizations

The project includes visualizations for:

- Survival status distribution
- Age distribution
- Tumor size distribution
- Regional node examined distribution
- Regional node positive distribution
- Numerical feature histograms
- Box plots for numeric variables
- Categorical feature count plots
- Correlation heatmap
- Random Forest feature importance
- Logistic Regression feature coefficients
- Logistic Regression probability curves
- Decision tree diagrams

The feature importance output highlights `Age`, `Regional Node Examined`, `Tumor Size`, and `Reginol Node Positive` as high ranking Random Forest features.

## Interactive Prediction

The notebook includes an interactive input workflow. Users can enter known patient details and leave unknown fields blank. The trained models then output:

```text
Likelihood of Survival
Likelihood of Death
Estimated Months Left to Live
```

Example notebook output:

```text
Likelihood of Survival: 77.95%
Likelihood of Death: 22.05%
Estimated Months Left to Live: 66.1
```

## Technologies Used

- Python
- Pandas
- NumPy
- scikit-learn
- Matplotlib
- Seaborn
- Joblib
- Jupyter Notebook
- Google Colab

## Repository Structure

```text
.
├── CS471_Final_Project_Breast_Cancer.ipynb
├── CS471_Final_Project_Breast_Cancer.pdf
├── CS471_Final_Project_Breast_Cancer_Survival_Prediction_Report.docx
├── README.md
└── requirements.txt
```

Optional local files generated by the notebook:

```text
classification_model.py
regression_model.py
best_rf_clf.pkl
best_lr_clf.pkl
best_rf_reg.pkl
best_lr_reg.pkl
```

Dataset file expected locally:

```text
Breast_Cancer.csv
```

## How to Run

Clone the repository.

```bash
git clone https://github.com/your-username/breast-cancer-survival-prediction-ml.git
cd breast-cancer-survival-prediction-ml
```

Install the required packages.

```bash
pip install pandas numpy scikit-learn matplotlib seaborn joblib notebook
```

Download the dataset from Kaggle and place it in the project folder as:

```text
Breast_Cancer.csv
```

Launch Jupyter Notebook.

```bash
jupyter notebook
```

Open the notebook and run all cells from top to bottom.

## Possible Future Improvements

- Add stronger model validation with stratified splitting and cross validation summaries
- Add confusion matrices and ROC AUC curves for classification
- Add SHAP or permutation importance for explainability
- Add confidence intervals for predictions
- Improve regression performance with additional clinical features
- Test XGBoost, LightGBM, or neural network models
- Build a Streamlit or Flask interface for easier interaction
- Separate the notebook into reusable Python modules and a clean command line interface

## Skills Demonstrated

- Supervised machine learning
- Classification and regression modeling
- Data preprocessing with scikit-learn pipelines
- Exploratory data analysis
- Hyperparameter tuning
- Model evaluation and interpretation
- Data visualization
- Interactive notebook workflows
- Healthcare related machine learning problem framing
