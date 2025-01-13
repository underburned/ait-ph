# Artificial intelligence technologies  

© Petrov M.V., Senior Lecturer at the Department of Supercomputers and General Informatics, Samara University

## Lab 3: Classification *kNN*

[Lecture](../lectures/lecture_3/lecture_3_en.md)

1. Load data into `pandas.DataFrame` (any data source: CSV, JSON, Excel file, HTML table, etc.).
Built-in datasets in `sklearn` also can be converted into DataFrame object: (see [how-to](https://stackoverflow.com/questions/38105539/how-to-convert-a-scikit-learn-dataset-to-a-pandas-dataset)).  
   > TYou may need to use two datasets: one for binary classification, and the other for multiclass classification.  

2. Binary classification:
   - Provide a description of the dataset.
   - Perform data preprocessing (get rid of `null`, remove some features, etc.) &ndash; "clean up the data".
   - Encode categorical features if necessary.
   - Choose some value of the hyperparameter $k$ of the algorithm $kNN$.
   - Split the data into training and test samples.
     > Use the same split (performed only once) for all subsequent manipulations.
   - Perform binary classification.
   - Calculate the metrics: $accuracy$, $precision$, $recall$, $\textit{f-measure}$, also print out `classification_report`.
   - Normalize the data (by `StandardScaler`or `MinMaxScaler`).
   - Perform binary classification.
   - Calculate the metrics: $accuracy$, $precision$, $recall$, $\textit{f-measure}$, also print out `classification_report`.
   - Compare metrics based on data without normalization and using normalization.  

3. Optional task.
   > Next, we use normalized data.
   - Plot `сorrelation heatmap` and/or use `corr()` method. Select the most important features heuristically or based on some calculations (***see [note](#note)***).
   - Perform binary classification with filtered out features.
   - Calculate the metrics: $accuracy$, $precision$, $recall$, $\textit{f-measure}$, also print out `classification_report`.
   - Compare metrics "before" and "after" filtration, make conclusions.
     > Obviously, the desired results are improved metrics.
   - Iterate through the values of the hyperparameter $k$ in some range using cross-validation on the data
     > data &ndash; original data before splitting and using normalization
   
     with filtered out features. Plot a graph of the dependence of *train/test accuracy* on the value of $k$.  

4. Multiclass classification:
   - Provide a description of the dataset.
   - Perform data preprocessing (get rid of `null`, remove some features, etc.) &ndash; "clean up the data".
   - Encode categorical features if necessary.
   - Choose some value of the hyperparameter $k$ of the algorithm $kNN$.
   - Split the data into training and test samples.
     > Use the same split (performed only once) for the data without feature filtering and using filtering.
   - Perform multiclass classification.
   - Calculate the metrics: $accuracy$, $precision$, $recall$, $\textit{f-measure}$, also print out `classification_report`.  

5. Optional task.
   - Plot `сorrelation heatmap` and/or use `corr()` method. Select the most important features heuristically or based on some calculations (***see [note](#note)***).
   - Perform multiclass classification with filtered out features.
   - Calculate the metrics: $accuracy$, $precision$, $recall$, $\textit{f-measure}$, also print out `classification_report`.
   - Compare metrics "before" and "after" filtration, make conclusions.
     > Obviously, the desired results are improved metrics.
   - Iterate through the values of the hyperparameter $k$ in some range using cross-validation on the data
     > data &ndash; original data before splitting and using normalization

     with filtered out features. Plot a graph of the dependence of *train/test accuracy* on the value of $k$.
   - For the best classifier: print out metrics, `classification_report`, generate [confusion matrix](https://scikit-learn.org/stable/auto_examples/model_selection/plot_confusion_matrix.html) (it's like a matrix $TN$ / $TP$ / $FN$ / $FP$, only extended for multiclass classification, in order to understand which way the classifier is more likely to make mistakes).

### Note

One of the variants for filtering features in terms of importance (aka `feature importance`): 
- In the correlation matrix $M_{corr}$, zero the elements of the main diagonal.
- Set the threshold value $T_{corr}$ - the correlation value of one feature with another.
- Filter out $abs(M_{corr})$ by threshold $T_{corr}$.
- Group the filtered values by each feature (calculate the sum or average, for example), we get $F$ - a "list of features", of the type `Series`: the index is the name of the feature, the value is `feature importance`.
- Sort $F$ in descending order: $F_{sorted} = sort(F)$.
- Set the threshold value $T_{filter}$, for example $T_{filter} = 0$. You can plot a graph.
- $F_{sorted}[F_{sorted} > T_{filter}]$ - the required list of features. You can use $F_{sorted}.index$ for filtering dataframe out by feature.

Sources:
 - [Find high correlations in a large coefficient matrix](https://stackoverflow.com/a/61956415)
 - [Returning the highest and lowest correlations from a correlation matrix in pandas](https://stackoverflow.com/a/55731198)
 - [pandas.DataFrame.lt](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.lt.html)