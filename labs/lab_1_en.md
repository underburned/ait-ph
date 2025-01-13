# Artificial intelligence technologies  

© Petrov M.V., Senior Lecturer at the Department of Supercomputers and General Informatics, Samara University

## Lab 1: Pandas

[Lecture](../lectures/lecture_1/lecture_1_en.md)

1. Load data into `pandas.DataFrame` (any data source: CSV, JSON, Excel file, HTML table, etc.).
Built-in datasets in `sklearn` also can be converted into DataFrame object: (see [how-to](https://stackoverflow.com/questions/38105539/how-to-convert-a-scikit-learn-dataset-to-a-pandas-dataset)).  
   > The main requirement for the dataset that you are using is that there must be numeric columns (numerical features).  

2. Provide a description of the dataset.  

   *Example.*  
   Dataset [Rain in Australia](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package) comprises about 10 years of daily weather observations from numerous locations across Australia.

   `RainTomorrow` is the target variable to predict. It answers the crucial question: will it rain the next day? (Yes or No).  

   | Feature  | Description | Units           |
   |----------|-----------------| ----------- |  
   | Location  | The common name of the location of the weather station |  |  
   | MinTemp   | Minimum temperature in the 24 hours to 9am. Sometimes only known to the nearest whole degree. | degrees Celsius |  
   | Sunshine  | Bright sunshine in the 24 hours to midnight | hours |  

3. Perform the following operations on the dataframe:  
   - `.head()`.
   - `.describe()`.
   - Reading the value of a specific cell (with a specific index from a specific column).
   - Filtering rows out by index range.
   - Filtering a dataset out based on a condition.
   - Handling missing values:
      + dropping rows with missing values;
      + filling in the missing values with the average value in the column (feature).  
     > If there are no missing values, generate them, than drop them or fill in with the average value in the column.
   - Creating a new column (feature) calculated based on the values of other columns:
      + using an expression based on the available columns;
      + using `DataFrame.apply`;
      + using `Series.apply`.
   - Sorting dataframe by any of the features.
   - Calculation of several statistics by column (use the built-in aggregate functions &ndash; any to choose from).
   - Printing out values count of any feature or a set of features using `.value_counts()`.
   - Printing out unique values of any feature using `.unique()`.
   - Removing current index and creating new index based on different column which is best suited for it &ndash; see 
[reset_index](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.reset_index.html) and 
[set_index](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.set_index.html).  

4. Demonstrate the usage of `.groupby`, calculate aggregate functions for one or more columns based on the groupings in `groupby` (`.groupby` creates `DataFrameGroupBy` object which has `.agg()` function).  

5. Reshaping data $1D\rightarrow2D$ using `.pivot` (you cant use the results of aggregates obtained earlier using `.groupby` (group by two columns).  

6. Reshaping data $1D\rightarrow2D$, connected to grouping/aggregation (in a word, a pivot table): `.pivot_table`. Group only by categorical or numerical features with low cardinality.
   > If numerical feature has high cardinality then you need to reduce the range of unique values. For example, you can compute histogram as in task (8).  

7. Calculate the quantiles of the distribution of a numerical feature (using `numpy.quantile` or `numpy.percentile`).  

8. Calculate (text form) the histogram of any numerical feature (using `numpy.histogram`). The histogram values can be used as a roughened numeric feature for tasks (5) or (6).  

9. Iterate the `DataFrame` object by rows using `.iterrows()` and perform any operation with the data inside the loop.  

10. Create `DataFrame` object with `MultiIndex` in any way: using the constructor (there are many types of constructors for `MultiIndex` generation from scratch), using `read_sql` / `read_csv` / `read_excel`, `read_*`, using `pivot_table`, using `groupby`, etc..  
    - Rearrange the index levels.
    - Transpose a table (or create a new one) with `MultiIndex`.
    - Delete one of the index levels or add a new index level (you can initialize it with a constant value) &ndash; see documentation.  

11. Demonstrate the usage of `.merge`.  

12. Demonstrate the usage of `.concat` or `append`.  

### Remarks

> Some people use `.pivot` and `.pivot_table` incorrectly or in the wrong context, resulting in nonsense.
> - `.pivot` is needed in order to present the results of a two-level grouping in the form of a two-dimensional table, where one of the grouping levels goes into rows, the other into columns.
> - `.pivot_table` is needed for the same purpose, but it knows how to group/aggregate data by itself, and not just drag cells across a two-dimensional table.

> You can generate dataset with random values for tasks (10) - (12).