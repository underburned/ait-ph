# Artificial intelligence technologies  

© Petrov M.V., Senior Lecturer at the Department of Supercomputers and General Informatics, Samara University

## Lab 5: Linear regression

Lecture EN TBD:
- [Linear Models @ sklearn](https://scikit-learn.org/stable/modules/linear_model.html)
- [LinearRegression @ sklearn](https://scikit-learn.org/1.6/modules/generated/sklearn.linear_model.LinearRegression.html)
- [Ridge @ sklearn](https://scikit-learn.org/1.6/modules/generated/sklearn.linear_model.Ridge.html)
- [Lasso @ sklearn](https://scikit-learn.org/1.6/modules/generated/sklearn.linear_model.Lasso.html)
- [ElasticNet @ sklearn](https://scikit-learn.org/1.6/modules/generated/sklearn.linear_model.ElasticNet.html)
- [Recursive Feature Elimination @ sklearn](https://scikit-learn.org/1.6/modules/generated/sklearn.feature_selection.RFE.html)

[Lecture RU](../lectures/lecture_5/lecture_5.ipynb)

1. Load data into `pandas.DataFrame` (any data source: CSV, JSON, Excel file, HTML table, etc.).  
   > The main requirement for the dataset that you are using is that there must be at least numerical features. If there is no categorical features then skip the step with categorical features temporary removal in 2.  
2. Dataset and data preprocessing, stage 1:
   - Provide a description of the dataset.
   - Perform data preprocessing (get rid of `null`, remove some features, etc.) &ndash; "clean up the data".
   - Normalize the numerical data.
   - Visualize `heatmap` correlation matrix.
   - Visualize the relationship between the `target` variable and each of the features (using `srs.pairplot` or `pandas.plotting.scatter_matrix`). It is best to plot a pairwise distribution diagram between the target and each of the features separately (the example with `sns.FacetGrid` in the lecture).
   - Split the data into training and test samples.
     > Categorical features must be temporarily removed from the training and test sample dataframes (save the original ***splitted dataframes*** for stage 2).
3. OLS method (ordinary least squares):
   - Train a linear regression model `LinearRegression`.
   - Calculate the metrics $MSE$, $MAE$ и $R^2$ using test sample.
   - Print out `model.coef_` and `model.intercept_`.
   - Plot a graph (`barh`) with the importance of the coefficients for the corresponding features (the coefficients are arranged from top to bottom in descending order, and the names of the corresponding features are labeled along the vertical axis).
4. For each type of regression (`Ridge`, `LASSO`, `Elastic Net`):
   - Using `GridSearchCV`, search for the best regularization parameters values (`alpha` for `Ridge` and `LASSO`, `alpha` and `l1_ratio` for `Elastic Net`)
   - Print out the hyperparameter values, regression coefficients (`model.coef_` and `model.intercept_`) and the values of the metrics on the test set for the best model ($MSE$, $MAE$ and $R^2$).
   - Plot a graph (`barh`) with the importance of the coefficients for the corresponding features (the coefficients are arranged from top to bottom in descending order, and the names of the corresponding features are labeled along the vertical axis).  
   
   > Save the best models for stage 2.  
   > Stage 2 &ndash; optional tasks 5 and 6, part of 7th task.
5. Dataset and data preprocessing, stage 2:
   - Use dataframes after splitting into training and test samples from stage 1 with categorical features.
     > Do not split data again, use only the splitted data from stage 1.
   - Encode categorical features in training and test samples.
6. Regressions, stage 2:
   - Train `LinearRegression`, the best models of `Ridge`, `LASSO`, `Elastic Net` on a training set with categorical features.
   - Print out the hyperparameter values, regression coefficients (`model.coef_` and `model.intercept_`) and the values of the metrics on the test set ($MSE$, $MAE$ and $R^2$).
   - Compare metrics with and without categorical features for each of the models.
   - Choose the best model.
   - Plot a graph (`barh`) with the importance of the coefficients for the corresponding features (the coefficients are arranged from top to bottom in descending order, and the names of the corresponding features are labeled along the vertical axis).
   - Perform feature filtering using `Recursive Feature Elimination`.
   - Plot a graph (`barh`) with the importance of the coefficients for the corresponding features (the coefficients are arranged from top to bottom in descending order, and the names of the corresponding features are labeled along the vertical axis).
   - Print out the values of the metrics on the test set ($MSE$, $MAE$ и $R^2$).
7. Make a conclusion:
   - The best regressor trained on data without categorical features (metric values on the test set).
   > Next is the optional part.
   - The best regressor trained on data with categorical features (metric values on the test set).
   - Conclusion about the results of using `Recursive Feature Elimination` (better or worse &ndash; metric values).