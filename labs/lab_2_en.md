# Artificial intelligence technologies  

© Petrov M.V., Senior Lecturer at the Department of Supercomputers and General Informatics, Samara University

## Lab 2: Data visualization

[Lecture](../lectures/lecture_2/lecture_2_en.md)

1. Load data into `pandas.DataFrame` (any data source: CSV, JSON, Excel file, HTML table, etc.).
Built-in datasets in `sklearn` also can be converted into DataFrame object: (see [how-to](https://stackoverflow.com/questions/38105539/how-to-convert-a-scikit-learn-dataset-to-a-pandas-dataset)).  
   > The main requirement for the dataset that you are using is that there must be at least a couple of numeric columns (numerical features) and at least one categorical column (feature) with low cardinality.  

2. Provide a description of the dataset.  

   *Example.*  
   Dataset [Rain in Australia](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package) comprises about 10 years of daily weather observations from numerous locations across Australia.

   `RainTomorrow` is the target variable to predict. It answers the crucial question: will it rain the next day? (Yes or No).  

   | Feature  | Description | Units           |
   |----------|-----------------| ----------- |  
   | Location  | The common name of the location of the weather station |  |  
   | MinTemp   | Minimum temperature in the 24 hours to 9am. Sometimes only known to the nearest whole degree. | degrees Celsius |  
   | Sunshine  | Bright sunshine in the 24 hours to midnight | hours |  

3. `matplotlib`:  
   - Display several plots of different types using `matplotlib`.  
   - Display several sub-plots on a single plot using `.subplot`.
   
   > - The plots should be of different types.  
   > - The axes must be signed in at least one plot.  
   > - The title must be set in all plots.  

4. *Display interactive plot with slider (**optional**).*
   > - *It is not necessary to generate a complex and information-overloaded interactive plot, use just one or two numerical features in the context of another feature, at least add a slider. The presence of other graphical controls (buttons, etc.) is optional.*  

5. `pandas`:  
   - Display three different types of plots using `pandas.DataFrame.plot` / `Series.plot`.  
   
   > - There should be one `boxplot` among the plots (it is necessary to use the `by` parameter to display the relationship between a numeric variable and some other one).  
   > - Plots should be constructed using both the `DataFrame`'s and `Series`'s methods. Both variants need to be demonstrated.  

6. `seaborn`:  
   - Plot `.pairplot` on any dataset, analyze the relationship of a set of numerical features.  
   - Plot `.jointplot`, analyze the relationship of two specific numerical features.  
   - Plot `.boxplot` and/or `.violinplot` on any dataset, analyze a numerical feature in the context of a categorical one.  
   - Plot `.heatmap` &ndash; graph of pairwise correlation of all numerical features.
   
     > Categorical features must be removed from the dataframe before plotting.  

7. `scipy.stats`:  
   - Display Q-Q plot (and a histogram) for one of the numerical features in order to check whether its distribution corresponds to a normal distribution.  

8. `plotly`:  
   - Display several plots of different types.  
   - Display several sub-plots on a single plot.  

9. *Display interactive plot using `plotly` (**optional**)*.  
   
     > *`Dash` usage is optional.*  

### Recommendations

> It is advisable to apply creative skills to change the style of displaying graphs.