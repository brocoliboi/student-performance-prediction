# Student Performance Prediction Using Machine Learning

A supervised-learning project comparing Logistic Regression, Gaussian Naive Bayes and Support Vector Machine (RBF kernel) on the mathematics subset of the UCI Student Performance dataset.

## Run the project

1. Clone or download this repository.
2. Install dependencies: `pip install -r requirements.txt`.
3. Open `machine_learning_miniproject.ipynb` in Jupyter or Google Colab.
4. Run all cells from top to bottom. The notebook downloads the UCI dataset automatically; **no manual file upload is required**.

The notebook saves the trained models, dataset, evaluation CSVs and `model_metadata.json` in its working directory.

## Target definition

The target is derived from final mathematics grade (`G3`):
- **Low:** 0–9
- **Medium:** 10–14
- **High:** 15–20

To avoid direct target leakage, `G1`, `G2` and `G3` are excluded from predictor features.

## Models and evaluation

The project compares:
- Logistic Regression
- Gaussian Naive Bayes
- Support Vector Machine with an RBF kernel

Evaluation includes a stratified train/test split, accuracy, macro-averaged precision/recall/F1, classification reports, confusion matrices, stratified 5-fold cross-validation and permutation feature importance.

The model selected for saving is the one with the highest mean cross-validation Macro F1. Macro F1 gives each class equal weight, which is useful when class frequencies differ.

## Repository contents

| File | Description |
|---|---|
| `machine_learning_miniproject.ipynb` | End-to-end, reproducible notebook |
| `student_performance_dataset.csv` | Prepared dataset |
| `best_model.joblib` | Selected fitted pipeline |
| `all_trained_models.joblib` | All three fitted pipelines |
| `test_set_model_comparison.csv` | Held-out test metrics |
| `cross_validation_results.csv` | 5-fold CV metrics |
| `test_set_predictions.csv` | Actual and predicted test labels |
| `feature_importance.csv` | Permutation importance |
| `project_summary.txt` | Experiment summary |
| `requirements.txt` | Python dependencies |
| `.gitignore` | Files excluded from Git |

## Loading a saved model

```python
import joblib
import pandas as pd

model = joblib.load("best_model.joblib")
new_student = pd.DataFrame([{
    # Supply the same predictor columns used in the notebook.
}])
prediction = model.predict(new_student)
print(prediction[0])
```

The input DataFrame must contain the same feature names and compatible values as the training data. Use the same scikit-learn version used to create the serialized model; the notebook records the active version in `model_metadata.json` when it is run.

## Dataset source

UCI Machine Learning Repository — [Student Performance](https://archive.ics.uci.edu/dataset/320/student+performance). The notebook downloads the official archive and uses `student-mat.csv`.

## Limitations

- The mathematics dataset contains 395 students, so results may not generalize to other schools or populations.
- This is an educational classification experiment, not a validated tool for making decisions about individual students.
- The three-level target is derived from the final grade, and performance depends on the selected grade thresholds.
- Cross-validation is performed on the training split; the test split is reserved for final evaluation.
