# Titanic Survival Prediction — Capstone Project

A machine learning project that predicts passenger survival on the Titanic using the classic Kaggle dataset. Three traditional ML models and a neural network are trained and compared.

---

## Models

| Model | F1-Score |
|---|---|
| Logistic Regression | ~0.74 |
| Random Forest | ~0.72 |
| K-Nearest Neighbours | ~0.71 |
| Neural Network (Keras) | ~0.81 val. accuracy |

Logistic Regression achieved the best F1-score. The neural network reached comparable accuracy but offered no significant advantage on this small tabular dataset.

---

## How to Run

**1. Clone the repo**
```bash
git clone https://github.com/naif-bin-dair/capsotne-project-naif-bin-dair.git
cd capsotne-project-naif-bin-dair
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. Run the notebook / script**
```bash
jupyter notebook notebook.ipynb
```

---

## Dependencies

`pandas` · `numpy` · `matplotlib` · `seaborn` · `scikit-learn` · `tensorflow`

---

## Notes

- Missing `Age` values are imputed with the median; `Embarked` with the mode.
- The `Cabin` column is dropped due to excessive missing data.
- Numerical features are standardised before training KNN and the neural network.
- AI was used to assist with writing code and the report; all material is fully understood by the author.
