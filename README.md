# Netflix Content Rating Prediction

## Project Overview

This project applies machine learning techniques to predict Netflix content ratings (e.g., TV-MA, TV-14, PG) using metadata and textual features from Netflix and IMDb datasets. The goal is to evaluate whether classification models can accurately predict content ratings based on attributes such as release year, genre information, cast size, IMDb score, and text-based features extracted from descriptions.

Multiple machine learning models were built and compared, along with feature engineering, natural language processing, clustering analysis, and hyperparameter tuning.

---

## Dataset

The dataset combines Netflix title metadata with IMDb ratings.

**Key characteristics:**
- ~8,000+ titles
- Mix of numeric, categorical, and text features
- Target variable: `rating` (content classification label)

**Data sources:**
- Netflix Titles Dataset (Kaggle)
- IMDb Ratings Dataset (Kaggle)

---

## Feature Engineering

The following features were created to improve predictive performance:

- **Description Length:** Measures length of content descriptions.
- **Genre Count:** Number of genres assigned to each title.
- **Cast Count:** Number of actors listed in the cast.
- **Mature Keyword Count:** Counts presence of mature-themed words (e.g., violence, crime, war).
- **Country Count:** Number of countries involved in production.

These features help capture content complexity, production scale, and thematic maturity.

---

## NLP and Clustering Analysis

Natural language processing techniques were applied using TF-IDF vectorization on the description field to extract keyword-level patterns from text data.

In addition, K-Means clustering was used to group similar titles based on feature similarity. While clusters do not directly correspond to rating categories, they reveal underlying structure in the dataset and highlight patterns in content grouping.

---

## Models Implemented

### Logistic Regression
- Baseline linear classification model
- Hyperparameter: `max_iter=1000`

### Random Forest (Baseline)
- Ensemble tree-based model
- Hyperparameters: `n_estimators=100`, `max_depth=10`

### Random Forest (Optimized)
- Tuned using GridSearchCV
- Parameters included `max_depth` and `min_samples_split`

---

## Model Performance

| Model | Accuracy | Precision | Recall | F1 Score |
|------|----------|-----------|--------|----------|
| Logistic Regression | 0.396 | 0.258 | 0.396 | 0.287 |
| Random Forest (Baseline) | 0.403 | 0.357 | 0.403 | 0.352 |
| Random Forest (Optimized) | **0.412 (Best)** | **0.382** | **0.412** | **0.358** |

The optimized Random Forest model achieved the best overall performance across all evaluation metrics, indicating that hyperparameter tuning improved the model's ability to generalize and capture patterns in the dataset.

---

## Final Model Selection

The **Random Forest (Optimized)** model was selected as the final model.

Although the improvement over the baseline model is modest, the optimized model achieved the highest accuracy, precision, recall, and F1 score across all tested models. This indicates that tuning parameters such as `max_depth` and `min_samples_split` helped improve generalization performance.

Therefore, the optimized Random Forest model is the most suitable choice for deployment in this project.

---

## Key Insights

- Genre and text-based features provide important signals for rating prediction.
- Mature keyword indicators improve interpretability of content classification.
- Class imbalance significantly impacts overall model performance.
- Hyperparameter tuning provided a measurable improvement in model performance, with the optimized Random Forest outperforming the baseline model.

---

## Ethical Considerations

This model may reflect biases present in the dataset, including uneven representation of content ratings and regional differences in classification standards. If used in production, incorrect predictions could result in inappropriate content categorization.

To mitigate risk, the model should be used as a decision-support tool rather than a fully automated system. Human review is recommended for borderline cases, and regular monitoring should be performed to ensure fairness and reliability.

---

## Business Recommendations

This model can assist streaming platforms in pre-classifying new content before official ratings are assigned. It may help flag titles that require additional review for age appropriateness.

However, due to moderate accuracy, the model should not be used independently for automated decision-making. Instead, it should support content moderation teams as an advisory tool. Periodic retraining is recommended as new content is added.

---

## How to Run the Project

## Install Dependencies

pip install pandas numpy scikit-learn seaborn matplotlib
Run Notebook


## How to Run the Notebook

Open the notebook:

Then run the cells in order:

- Load dataset  
- Feature engineering  
- Train models  
- Evaluate results  

---

## Future Improvements

- Improve NLP features using Word2Vec or transformer-based embeddings (e.g., BERT)
- Address class imbalance using SMOTE or resampling techniques
- Test advanced models such as XGBoost or LightGBM
- Group ratings into broader categories (Kids / Teen / Mature)

---

## Author

Anthony Mollica  
Data Analytics Student – Adrian College

---
