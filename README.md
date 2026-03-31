# my-final-project
<<<<<<< HEAD
# Netflix Content Rating Prediction

## Project Description

This project uses machine learning to predict the content rating of Netflix titles based on metadata such as release year, IMDb score, description length, and genre information. The goal is to determine whether machine learning models can accurately classify the rating category (such as TV-MA, TV-14, or PG-13) using features derived from Netflix and IMDb datasets. Two models were implemented and compared to evaluate their effectiveness in predicting content ratings.

## Dataset

The dataset used in this project combines Netflix title metadata with IMDb rating information. The merged dataset includes features such as title type, release year, duration, genres, cast information, and IMDb scores.

Basic dataset statistics:

* Approximately 8,000+ titles
* Multiple feature types including numeric, categorical, and text-based fields
* Target variable: `rating` (content rating classification)

Dataset sources:

* Netflix Titles Dataset (Kaggle)
* IMDb Ratings Dataset (Kaggle)

## Feature Engineering

Several custom features were created to improve model performance:

* **Description Length:** Character count of the content description.
* **Genre Count:** Number of genres assigned to each title.
* **Cast Count:** Number of actors listed in the cast field.

These engineered features were designed to capture patterns that may relate to how content is rated.

## Models Implemented

Two machine learning models were implemented for classification:

1. **Logistic Regression**

   * Baseline classification model
   * Hyperparameters: `max_iter=1000`, `solver='lbfgs'`

2. **Random Forest Classifier**

   * Ensemble model capable of capturing nonlinear relationships
   * Hyperparameters: `n_estimators=100`, `max_depth=10`

Both models were trained on the same dataset and evaluated using the same metrics to ensure a fair comparison.

## Current Results

| Model               | Accuracy |
| ------------------- | -------- |
| Logistic Regression | ~40%     |
| Random Forest       | ~42%     |

Random Forest performed slightly better due to its ability to model nonlinear relationships between features. However, both models were affected by class imbalance in the rating categories.

## How to Run the Project

### Install Dependencies

Run the following command to install required libraries:

pip install pandas numpy scikit-learn seaborn matplotlib

### Run the Notebook

Open and run the Jupyter notebook:

`final_project_draft.ipynb`

The notebook will:

1. Load and explore the dataset
2. Perform feature engineering
3. Prepare data for modeling
4. Train and evaluate machine learning models
5. Compare model performance

## Future Improvements

Future improvements for this project include:

* Creating additional engineered features using text analysis from the description column
* Addressing class imbalance using resampling techniques
* Hyperparameter tuning for the Random Forest model
* Testing additional algorithms such as Gradient Boosting or XGBoost

## Author

Anthony Mollica
Data Analytics Student – Adrian College
=======
>>>>>>> 216c806 (completed final project draft with two models and feature engineering)
