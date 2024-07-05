# Exploring Online Learning Success By The Analysis Of Machine Learning Models

This project aims to explore and analyze factors influencing online learning success using various machine learning models. The dataset contains various features such as discipline, expected hours per week, course length, and learner type, which are used to predict whether a learner viewed the course content.

## Table of Contents

- [Installation](#installation)
- [Dataset](#dataset)
- [Preprocessing](#preprocessing)
- [Models Used](#models-used)
- [Evaluation](#evaluation)
- [Feature Importance](#feature-importance)
- [Clustering Analysis](#clustering-analysis)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Installation

To run this project, you need to have Python installed along with the following libraries:

```bash
pip install pandas scikit-learn numpy shap matplotlib
```

## Dataset

The dataset used in this project should be named `dataset.csv` and should be placed in the root directory of the project. The dataset contains the following columns (including but not limited to):

- `course_id_DI`
- `userid_DI`
- `expected_hours_week`
- `discipline`
- `primary_reason`
- `learner_type`
- `LoE_DI`
- `registered`
- `explored`
- `grade`
- `grade_reqs`
- `completed_%`
- `course_reqs`
- `nevents`
- `ndays_act`
- `ncontent`
- `nforum_posts`
- `course_length`
- `viewed`

## Preprocessing

1. **Removing Anonymous and Indicative Features**:
    - Columns `course_id_DI` and `userid_DI` are removed.
  
2. **Handling Missing Values**:
    - Rows with missing values in the `expected_hours_week` column are dropped.
  
3. **Converting Expected Hours to Numeric**:
    - The `expected_hours_week` column values are converted to numeric using a regex to extract numeric values.
  
4. **Encoding Nominal Features**:
    - Nominal features like `discipline`, `primary_reason`, `learner_type`, and `LoE_DI` are encoded using `LabelEncoder`.
  
5. **Normalizing Features**:
    - Features such as `expected_hours_week`, `course_length`, `nevents`, `ndays_act`, `ncontent`, and `nforum_posts` are normalized using `MinMaxScaler`.

## Models Used

The following machine learning models are used to analyze the data:

1. **Linear Regression**
2. **Logistic Regression**
3. **Decision Tree Regressor**
4. **Random Forest Regressor**
5. **AdaBoost Regressor**

## Evaluation

The performance of the models is evaluated using metrics like Mean Squared Error (MSE), R-squared (for regression models), and accuracy (for the logistic regression model).

## Feature Importance

The SHAP (SHapley Additive exPlanations) values are used to interpret the impact of each feature on the prediction.

## Clustering Analysis

KMedoids clustering is applied to identify patterns among the learners based on influential features (`discipline` and `learner_type`).

## Results

The performance of each model is recorded, and the best model is determined based on R-squared or accuracy. The SHAP values provide insights into the factors influencing online learning performance. Clustering analysis reveals distinct groups of learners.

