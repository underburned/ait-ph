# Artificial intelligence technologies  

© Petrov M.V., Senior Lecturer at the Department of Supercomputers and General Informatics, Samara University

## Lecture 4. Decision trees

### Contents

1. [Introduction](#3.1-Introduction)
2. [Определение решающего дерева](#4.2-Определение-решающего-дерева)
3. [Tree construction task](#4.3-Tree-construction-task)
4. [Greedy algorithm for decision tree construction](#4.4-Greedy-algorithm-for-decision-tree-construction)
5. [Branching criteria: general idea](#4.5-Branching-criteria:-general-idea)
6. [Branching criteria for typical tasks](#4.6-Branching-criteria-for-typical-tasks)
7. [Features of the data](#4.7-Features-of-the-data)
8. [Decision trees regularization methods](#4.8-Decision-trees-regularization-methods)
9. [Example](#4.9-Example)
10. [Decision tree main parameters. `DecisionTreeClassifier`](#4.10-Decision-tree-main-parameters.-DecisionTreeClassifier)
11. [Dataset `Rain in Australia`](#4.11-Dataset-Rain-in-Australia)
12. [Data preprocessing](#4.12-Data-preprocessing)
13. [Classification](#4.13-Classification)
14. [Decision trees ensembles](#4.14-Decision-trees-ensembles)
15. [Decision trees pros and cons](#4.15-Decision-trees-pros-and-cons)

### 4.1 Introduction

Guides:
- [Topic 3. Classification, Decision Trees and k Nearest Neighbors @ mlcourse.ai](https://mlcourse.ai/book/topic03/topic03_decision_trees_kNN.html)

> Read: [Decision Tree](https://mlcourse.ai/book/topic03/topic03_decision_trees_kNN.html#decision-tree).  
> 
> 4.2-4.9 chapters are missing here, so skipping to 4.10.

### 4.10 Decision tree main parameters

See [DecisionTreeClassifier @ sklearn](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html): `max_depth`, `max_features`, `min_samples_leaf`.

### 4.11 Dataset `Rain in Australia`

Dataset [Rain in Australia](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package) comprises about 10 years of daily weather observations from numerous locations across Australia.

`RainTomorrow` is the target variable to predict. It answers the crucial question: will it rain the next day? (Yes or No).

| Feature       | Description                                                                                            | Units               |
|---------------|--------------------------------------------------------------------------------------------------------|---------------------|
| Location      | The common name of the location of the weather station                                                 |                     |
| MinTemp       | Minimum temperature in the 24 hours to 9am. Sometimes only known to the nearest whole degree.          | degrees Celsius     |
| MaxTemp       | Maximum temperature in the 24 hours from 9am. Sometimes only known to the nearest whole degree.        | degrees Celsius     |
| Rainfall      | Precipitation (rainfall) in the 24 hours to 9am. Sometimes only known to the nearest whole millimetre. | millimetres         |
| Sunshine      | Bright sunshine in the 24 hours to midnight                                                            | hours               |
| WindGustDir   | Direction of strongest gust in the 24 hours to midnight                                                | 16 compass points   |
| WindGustSpeed | Speed of strongest wind gust in the 24 hours to midnight                                               | kilometres per hour |
| WindDir9am    | Wind direction averaged over 10 minutes prior to 9 am                                                  | compass points      |
| WindDir3pm    | Wind direction averaged over 10 minutes prior to 3 pm                                                  | compass points      |
| WindSpeed9am  | Wind speed averaged over 10 minutes prior to 9 am                                                      | kilometres per hour |
| WindSpeed3pm  | Wind speed averaged over 10 minutes prior to 3 pm                                                      | kilometres per hour |
| Humidity9am   | Relative humidity at 9 am                                                                              | percent             |
| Humidity3pm   | Relative humidity at 3 pm                                                                              | percent             |
| Pressure9am   | Atmospheric pressure reduced to mean sea level at 9 am                                                 | hectopascals        |
| Pressure3pm   | Atmospheric pressure reduced to mean sea level at 3 pm                                                 | hectopascals        |
| Cloud9am      | Fraction of sky obscured by cloud at 9 am                                                              | eighths             |
| Cloud3pm      | Fraction of sky obscured by cloud at 3 pm                                                              | eighths             |
| Temp9am       | Temperature at 9 am                                                                                    | degrees Celsius     |
| Temp3pm       | Temperature at 3 pm                                                                                    | degrees Celsius     |
| RainToday     | The rain for that day was 1mm or more                                                                  | Yes or No           |
| RainTomorrow  | The rain for that day was 1mm or more. The target variable to predict.                                 | Yes or No           |

### 4.12 Data preprocessing

Code block in chapter 4.12 of [lecture 4 in russian](lecture_4.ipynb) produces dataframe object `df_clean` with preprocessed data like in [lecture 3 in russian](../lecture_3/lecture_3.ipynb), splits data into train and test samples. Data is ready for classification.

### 4.13 Classification

See code blocks in chapter 4.13 of [lecture 4 in russian](lecture_4.ipynb). Steps:
- Calling `.fit()`, `.predict()`; `accuracy_score` for test sample
- `GridSearchCV` example (see [sklearn.model_selection.GridSearchCV](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html))
- Printing features importance from best estimator
- Visualizing the resulting decision tree
  > The installation of [Graphviz](https://graphviz.org/download/) is needed.
- Filtering out features by median value
- Running `GridSearchCV` for the filtered dataframe
- Printing accuracy score for the original and filtered out classified data

### 4.14 Decision trees ensembles

See [sklearn.ensemble.RandomForestClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html) and code blocks in chapter 4.14 of [lecture 4 in russian](lecture_4.ipynb).

### 4.15 Decision trees pros and cons

TBD