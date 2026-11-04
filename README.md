## Student Performance Prediction Using Machine Learning

A supervised-learning project comparing Logistic Regression, Gaussian Naive Bayes, and Support Vector Machine classifiers on the mathematics subset of the UCI Student Performance dataset.

### Project contents
- `machine_learning_miniproject.ipynb` — Google Colab notebook
- `student_performance_dataset.csv` — prepared dataset
- `test_set_model_comparison.csv` — held-out test metrics
- `cross_validation_results.csv` — stratified 5-fold validation metrics
- `test_set_predictions.csv` — actual and predicted test labels
- `feature_importance.csv` — permutation feature importance
- `best_model.joblib`, `all_trained_models.joblib` — saved model artifacts
- `project_summary.txt` — experiment summary
- `requirements.txt` — Python dependencies

### Target classes
`Performance` is derived from final mathematics grade (`G3`): Low (0–9), Medium (10–14), and High (15–20). The notebook excludes `G1`, `G2`, and `G3` as predictors to reduce direct target leakage.

### Reported test-set results
| Model | Accuracy | Macro F1 |
|---|---:|---:|
| Logistic Regression | 53.16% | 48.86% |
| Support Vector Machine | 49.37% | 35.81% |
| Gaussian Naive Bayes | 26.58% | 26.47% |

### Cross-validation results
| Model | Mean Accuracy | Mean Macro F1 |
|---|---:|---:|
| Logistic Regression | 48.39% | 45.64% |
| Support Vector Machine | 55.05% | 38.90% |
| Gaussian Naive Bayes | 30.04% | 28.83% |

These values are reproduced from the supplied result files and have not been independently rerun during repository preparation.

### Run
The notebook is authored for Google Colab and contains Colab-specific upload/download operations. Open it in [Google Colab](https://colab.research.google.com/) and run cells in order. Install packages locally with `pip install -r requirements.txt` (Colab-specific cells may need adaptation for local execution).

### Dataset
UCI Student Performance dataset: https://archive.ics.uci.edu/dataset/320/student+performance

### Notes
This is an educational baseline using 395 records; its results are moderate and should not be interpreted as a production student-assessment system. Add approved author names and institutional affiliation before presenting the repository as a final submission. Review data licensing/attribution before redistribution.
