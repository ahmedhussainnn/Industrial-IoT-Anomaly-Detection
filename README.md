# Industrial IoT Anomaly Detection

This project investigates the use of machine learning for classifying operational states from Industrial Internet of Things (IIoT) sensor data.

The implementation compares Random Forest and Logistic Regression using sensor measurements including temperature, gas readings and flame activity.

## Project Objectives

- Explore and analyse Industrial IoT sensor data
- Identify relevant features for operational-state classification
- Train and evaluate supervised machine-learning models
- Compare Random Forest with a Logistic Regression baseline
- Analyse class-level performance and feature importance
- Consider the limitations of applying the model to real-time industrial monitoring

## Dataset

The analysed dataset contains 4,000 observations and 14 original columns. Seven sensor-derived predictors were selected:

- `gas_raw`
- `temp_c`
- `flame`
- `gas_avg`
- `temp_avg`
- `dGas`
- `dTemp`

The prediction target is `final_state`, consisting of four operational classes.

## Machine Learning Models

### Random Forest
- 100 estimators
- Balanced class weighting
- Stratified train-test split
- Random state: 42

### Logistic Regression
- StandardScaler preprocessing
- Balanced class weighting
- Used as a baseline classifier

## Results

| Model | Test Accuracy |
|---|---:|
| Random Forest | 98.38% |
| Logistic Regression | 95.88% |

Random Forest achieved a macro F1-score of 0.97 and weighted F1-score of 0.98.

Feature-importance analysis identified `temp_avg` and `temp_c` as the strongest predictors in the Random Forest model.

## Evaluation

Model performance was evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrix
- Feature importance

## Implementation

The complete analysis is available in:

`IoT_Anomaly_detection.ipynb`

The notebook contains data inspection, exploratory analysis, preprocessing, model training, evaluation and visualisation.

## Technologies

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter/Google Colab

## Limitations

The current implementation evaluates supervised classification on a static labelled dataset. It should therefore be regarded as a prototype for the classification component of a future real-time Industrial IoT anomaly-detection pipeline rather than a complete streaming deployment.
