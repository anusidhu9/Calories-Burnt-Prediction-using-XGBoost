# Calories Burnt Prediction

A machine learning project that predicts calories burned during exercise using an **XGBoost regression model**.

## Project Overview

The project combines exercise and calorie data, performs exploratory data analysis, encodes the categorical `Gender` feature, trains an XGBoost regressor, and evaluates predictions using **Mean Absolute Error (MAE)**.

The cleaned notebook is organized so it can be run locally or from a cloned GitHub repository without Google Colab/Google Drive-specific paths.

## Project Structure

```text
calories-burnt-prediction/
├── data/
│   ├── calories.csv
│   └── exercise.csv
├── models/
│   ├── xgb_model.pkl
│   └── feature_cols.pkl
├── notebooks/
│   └── Calories_Burnt_Prediction_Clean.ipynb
├── .gitignore
├── README.md
└── requirements.txt
```

> **Note:** The dataset files and trained model files are not included in this package. Add them locally if you have permission to redistribute them.

## Dataset

The notebook expects two CSV files:

- `data/calories.csv`
- `data/exercise.csv`

The two files are combined using their row order, with `Calories` taken from `calories.csv`.

## Features

The model uses these exercise-related features:

- Gender
- Age
- Height
- Weight
- Duration
- Heart_Rate
- Body_Temp

`User_ID` is excluded from model training, while `Calories` is the prediction target.

## Machine Learning Workflow

1. Load the datasets
2. Combine the datasets
3. Inspect shape, data types, descriptive statistics, and missing values
4. Perform exploratory data analysis
5. Encode `Gender`
6. Separate features and target
7. Split the data into training and testing sets
8. Train an XGBoost regression model
9. Evaluate the model using Mean Absolute Error
10. Save the trained model and feature names

## Installation

Use Python 3.10+ and install the dependencies:

```bash
pip install -r requirements.txt
```

## Run the Notebook

Start Jupyter:

```bash
jupyter notebook
```

Then open:

```text
notebooks/Calories_Burnt_Prediction_Clean.ipynb
```

Before running it, place `calories.csv` and `exercise.csv` in the `data/` directory.

## Model Output

After successful training, the notebook creates:

```text
models/xgb_model.pkl
models/feature_cols.pkl
```

These files can be loaded later with `joblib` for prediction or deployment.

## Evaluation

The notebook reports **Mean Absolute Error (MAE)** on the held-out test set. Run the notebook to reproduce the metric in your own environment.

## Reproducibility

The train/test split uses `random_state=2`.

The XGBoost model also uses the same random seed.

## Important Notes

- Do not commit private datasets, credentials, API keys, or local environment files.
- Do not commit large model artifacts unless you intentionally want them versioned.
- The original notebook contained Google Colab/Google Drive paths and repeated model-saving/loading steps. Those have been removed from the cleaned GitHub-ready version.
