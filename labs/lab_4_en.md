# Artificial intelligence technologies  

© Petrov M.V., Senior Lecturer at the Department of Supercomputers and General Informatics, Samara University

## Lab 4: Classification. Decision trees

[Lecture](../lectures/lecture_4/lecture_4_en.md)

1. Load data into `pandas.DataFrame` (any data source: CSV, JSON, Excel file, HTML table, etc.).  
2. Dataset and data preprocessing:
   - Provide a description of the dataset.
   - Perform data preprocessing (get rid of `null`, remove some features, etc.) &ndash; "clean up the data".
   - Encode categorical features if necessary.
   - Choose some value of the hyperparameter $k$ of the algorithm $kNN$.
   - Split the data into training and test samples.
     > Next, we use a training sample, also for metrics calculation.  
3. Decision tree:
   - Using `GridSearchCV`, search for the best `DecisionTreeClassifier` model's hyperparameter values (at least `max_depth`, `max_features`, other parameters are optional).
   - Print out hyperparameter and metrics values for the best `DecisionTreeClassifier` model ($accuracy$, $precision$, $recall$, $\textit{f-measure}$).
   - For the resulting best tree print out `feature_importances`, sorted out in descending order.
   - Filter the features out (by some value of the threshold for the importance of the feature).
   - Search for the best model using `GridSearchCV` on a training sample with filtered out features.
   - Print out the resulting hyperparameters of the best model.
   - Compare metrics before and after filtering out the features of the best models.  
4. Random forest:
   - Using `GridSearchCV`, search for the best `RandomForestClassifier` model's hyperparameter values.
   - Print out hyperparameter values for the best random forest model.
   - Filter the features out.
   - Search for the best model using `GridSearchCV` on a training sample with filtered out features.
   - Print out the resulting hyperparameters of the best model.
   - Compare metrics before and after filtering out the features of the best models.  
5. $kNN$:
   - Using `GridSearchCV`, search for the best `KNeighborsClassifier` model's hyperparameter value (`n_neighbors`).
   - Print out hyperparameter and metric values for the best model.
   - Filter the features out.
   - Search for the best model using `GridSearchCV` on a training sample with filtered out features.
   - Print out the resulting hyperparameters of the best model.
   - Compare metrics before and after filtering out the features of the best models.  
6. Optional task.  
If the metrics values are improved after filtering out the features for at least one of the models, then using the set of filtered out features (the intersection of the sets of filtered out features of each model or the union of the sets, it is not particularly important, the main thing is to describe how the new subset of data is obtained) train best models of `KNeighborsClassifier`, `DecisionTreeClassifier`, `RandomForestClassifier`. Compare the trained classifiers in task (7) using the same set of filtered out features. Otherwise, skip this task.
7. Measurement of the produced models quality :
   - Visualize any resulting decision tree.
     > You need set the value of `feature_names` in sklearn.tree.export_graphviz` for outputting the feature names into the plot, `class_names` &ndash; for outputting class names (before encoding the target feature, you can save the names in a separate array).
   - Compare the best `KNeighborsClassifier`, `DecisionTreeClassifier`, `RandomForestClassifier` models using **test sample**. Print out the metrics: $accuracy$, $precision$, $recall$, $\textit{f-measure}$.