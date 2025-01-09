# Artificial intelligence technologies  

© Petrov M.V., Senior Lecturer at the Department of Supercomputers and General Informatics, Samara University

## Lecture 3. Classification. Metrics

### Contents

1. [Introduction](#3.1-Introduction)
2. [$k$-nearest neighbors method](#3.2-k-nearest-neighbors-method)
3. [Dataset `Rain in Australia` for binary classification](#3.3-Dataset-Rain-in-Australia-for-binary-classification)
4. [Data preprocessing](#3.4-Data-preprocessing)
5. [Encoding categorical data](#3.5-Encoding-categorical-data)
6. [Data preprocessing (continuation)](#3.6-Data-preprocessing-(continuation))
7. [Training and prediction](#3.7-Training-and-prediction)
8. [Model quality evaluation](#3.8-Model-quality-evaluation)
9. [Evaluation metrics for binary classification](#3.9-Evaluation-metrics-for-binary-classification)

### 3.1 Introduction

Guides:
- [Topic 3. Classification, Decision Trees and k Nearest Neighbors @ mlcourse.ai](https://mlcourse.ai/book/topic03/topic03_decision_trees_kNN.html)

> Read: classification task (problem) definition.

### 3.2 $k$-Nearest Neighbors Method

> Read: k-nearest neighbors method description in [Topic 3. Classification, Decision Trees and k Nearest Neighbors @ mlcourse.ai](https://mlcourse.ai/book/topic03/topic03_decision_trees_kNN.html).

See code blocks in chapter 3.2 of [lecture 3 in russian](lecture_3.ipynb): method's demo by using iris dataset from `sklearn`.

### 3.3 Dataset [Rain in Australia](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package) for binary classification

#### Dataset description

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

### 3.4 Data preprocessing

See code blocks in chapter 3.4 of [lecture 3 in russian](lecture_3.ipynb). Steps:
- Dropping NaN in `RainTomorrow`
- Categorical data preprocessing, stage 1:
  - Populating array `cat_cols` with categorical feature names
  - Filtering `Null` values in `cat_cols`: creating `cat_null`
  - Filling `Null` values in `cat_cols` with `.mode()`: see [pandas.DataFrame.mode](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.mode.html)
  - > Feature cardinality &ndash; unique values count
  - Printing cardinality of `cat_cols` features
  - Splitting `Date` feature into `Year`, `Month` and `Day` features, removing `Date`
  - Printing `Location` feature cardinality.

### 3.5 Encoding categorical data

Encoding categorical features into numerical.  
See:
- [Label encoder @ sklearn](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.LabelEncoder.html)
- [Label encoder in pandas &ndash; pandas.factorize() @ pandas](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.LabelEncoder.html)
- [One-hot encoder @ sklearn](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.LabelEncoder.html)
- [One-hot encoder in pandas &ndash; pandas.get_dummies() @ pandas](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.LabelEncoder.html)  
>  ***Don't use label encoder for input features encoding!***

See code blocks in chapter 3.5 of [lecture 3 in russian](lecture_3.ipynb): encoding categorical features into numerical examples.

### 3.6 Data preprocessing (continuation)

Categorical and numerical data preprocessing.  
See code blocks in chapter 3.6 of [lecture 3 in russian](lecture_3.ipynb). Steps:
- Populating array `num_cols` with numerical feature names
- Fill missing numerical data with median values
- Encoding categorical features with `One-Hot Encoder`, dropping categorical features afterwards:
  - `Location` feature
  - `WindGustDir`, `WindDir9am`, `WindDir3pm` features
- Encoding string features `RainToday` and `RainTomorrow` into binary (zeros and ones) manually
- Visualizing outliers with `seaborn.boxplot`
- Numerical data normalization with `sklearn.preprocessing.MinMaxScaler()`
- Removing outliers
  > See: [Interquartile range](https://en.wikipedia.org/wiki/Interquartile_range).  

  Find in code blocks methods `get_bounds()` and `clean_data()`
- Split dataframe into $X$ (input features) and $y$ (target value &ndash; `RainTomorrow` feature)

### 3.7 Training and prediction

See code blocks in chapter 3.7 of [lecture 3 in russian](lecture_3.ipynb). Steps:
- KNeighborsClassifier init
- Split $X$, $y$ into train and test samples
- Fit data into classifier

### 3.8 Model quality evaluation

See code blocks in chapter 3.8 of [lecture 3 in russian](lecture_3.ipynb). Steps:
- Printing classifier's accuracy score
- Plotting the train/test accuracy against the value of hyperparameter $k$
- Cross-validation
  > Read [3.1. Cross-validation: evaluating estimator performance @ sklearn](https://scikit-learn.org/stable/modules/cross_validation.html#cross-validation)  
  > 
  > See [sklearn.model_selection.cross_val_score](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.cross_val_score.html) and [sklearn.model_selection.StratifiedKFold](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.StratifiedKFold.html)

### 3.9 Evaluation metrics for binary classification

Guide:
- [20 Evaluation Metrics for Binary Classification (And When to Use Them)](https://neptune.ai/blog/evaluation-metrics-binary-classification)

See code blocks in chapter 3.9 of [lecture 3 in russian](lecture_3.ipynb).