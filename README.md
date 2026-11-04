# Student Performance Prediction Using Machine Learning

A supervised-learning project comparing Logistic Regression, Gaussian Naive Bayes, and Support Vector Machine classifiers on the mathematics subset of the UCI Student Performance dataset.

## Project contents

| File | Description |
|---|---|
| `machine_learning_miniproject.ipynb` | Submitted Google Colab notebook |
| `student_performance_dataset.csv` | Prepared dataset |
| `test_set_model_comparison.csv` | Held-out test metrics |
| `cross_validation_results.csv` | Stratified 5-fold validation metrics |
| `test_set_predictions.csv` | Actual and predicted test labels |
| `feature_importance.csv` | Permutation feature-importance results |
| `project_summary.txt` | Experiment summary |
| `requirements.txt` | Main Python dependencies |
| `.gitignore` | Python, environment, notebook, and secret-file exclusions |

## Target classes

The `Performance` label is derived from final mathematics grade (`G3`):
- **Low:** 0–9
- **Medium:** 10–14
- **High:** 15–20

The notebook excludes `G1`, `G2`, and `G3` as predictor features to reduce direct target leakage.

## Reported test-set results

| Model | Accuracy | Macro F1 |
|---|---:|---:|
| Logistic Regression | 53.16% | 48.86% |
| Support Vector Machine | 49.37% | 35.81% |
| Gaussian Naive Bayes | 26.58% | 26.47% |

## Reported stratified 5-fold cross-validation results

| Model | Mean Accuracy | Mean Macro F1 |
|---|---:|---:|
| Logistic Regression | 48.39% | 45.64% |
| Support Vector Machine | 55.05% | 38.90% |
| Gaussian Naive Bayes | 30.04% | 28.83% |

These values are transcribed from the supplied result files and have not been independently rerun during repository preparation.

## Run the notebook

The notebook was authored for **Google Colab** and contains Colab-specific file upload/download operations. Open it in [Google Colab](https://colab.research.google.com/) and run the cells in order. Install the main packages locally with:

```bash
pip install -r requirements.txt
```

Some Colab-specific cells may need adaptation for local execution. The notebook's original code has been preserved rather than silently rewritten.

## Dataset source

UCI Student Performance dataset: https://archive.ics.uci.edu/dataset/320/student+performance

The supplied dataset is included here for reproducibility. Review the dataset's terms and attribution requirements before redistribution or reuse.

## Limitations and notes

- The supplied dataset contains 395 records.
- Results are based on the supplied train/test and cross-validation output files.
- The reported predictive performance is moderate; this is an educational baseline, not a production student-assessment system.
- The original ZIP also contained serialized `.joblib` model artifacts. Those binary artifacts have not been added to this repository.
- Add the approved author names and institutional affiliation before presenting this as a final academic submission.
