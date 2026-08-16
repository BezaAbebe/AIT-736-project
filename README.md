# 30-Day Hospital Readmission Prediction

Predicts whether a diabetic patient will be readmitted to the hospital within 30 days, using the [Diabetes 130-US Hospitals (1999-2008)](https://archive.ics.uci.edu/dataset/296/diabetes+130-us+hospitals+for+years+1999-2008) dataset from the UCI ML Repository.

## Project Structure

- `diabetes.ipynb` — main notebook: data cleaning, feature engineering, model training, and evaluation
- `data/` — raw dataset (`diabetic_data.csv`) and ID mapping reference (`IDS_mapping.csv`)
- `figures/` — generated charts (class balance, missing data, outliers, model comparison, ROC curve, confusion matrix, feature importance)
- `results/` — model scores and supporting CSV outputs

## Models

Four classifiers are trained and compared using `class_weight="balanced"` to account for the ~9% readmission rate:

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |
|---|---|---|---|---|---|
| Baseline (always says no) | 0.910 | 0.000 | 0.000 | 0.000 | 0.500 |
| Logistic Regression | 0.662 | 0.139 | 0.531 | 0.220 | 0.651 |
| Decision Tree | 0.736 | 0.153 | 0.429 | 0.226 | 0.623 |
| Random Forest | 0.712 | 0.152 | 0.484 | 0.231 | 0.651 |

## Setup

```bash
pip install numpy pandas scikit-learn matplotlib jupyter
jupyter notebook diabetes.ipynb
```
