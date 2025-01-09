# Artificial intelligence technologies  

© Petrov M.V., Senior Lecturer at the Department of Supercomputers and General Informatics, Samara University

## Lecture 2. Data visualization

### Contents

1. [Libraries](#2.1-Libraries)
2. [Dataset](#2.2-Dataset)
3. [Data preprocessing](#2.3-Data-preprocessing)
4. [Interactive plot in `matplotlib`](#2.4-Interactive-plot-in-matplotlib)
5. [Interactive plot in `plotly`](#2.5-Interactive-plot-in-plotly)
6. [Plotting by `pandas`](#2.6-Plotting-by-pandas)
7. [Plotting by `seaborn`](#2.7-Plotting-by-seaborn)
8. [Different plot examples](#2.8-Different-plot-examples)
9. [Export plot in raster and vector formats](#2.9-Export-plot-in-raster-and-vector-formats)
10. [`plotly` `Dash`](#2.10-plotly-Dash)

### 2.1 Libraries

- [matplotlib](https://matplotlib.org/) &ndash; Python 3 library for data visualization.
- [seaborn](https://seaborn.pydata.org/index.html) &ndash; Python 3 library for statistical data visualization.
   Based on `matplotlib` and using data structures in `pandas`.
- [plotly](https://plotly.com/python/) &ndash; Python 3 library for data visualization.
   - [Dash](https://dash.plotly.com/) framework.

`matplotlib` tutorials:
- [Quick start guide](https://matplotlib.org/stable/users/explain/quick_start.html)
- [Pyplot tutorial](https://matplotlib.org/stable/tutorials/pyplot.html)
- [Examples](https://matplotlib.org/stable/gallery/index.html)
- [Interactive Plotting in IPython](https://ipython.readthedocs.io/en/stable/interactive/plotting.html)
- [Enable interactive mode - matplotlib.pyplot.ion](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.ion.html)

`seaborn` tutorials:
- [Tutorial](https://seaborn.pydata.org/tutorial.html)
- [Visualizing categorical data](https://seaborn.pydata.org/tutorial/categorical.html)

`plotly` tutorials:
- [Plotly Tutorial for Beginners @ Kaggle](https://www.kaggle.com/code/kanncaa1/plotly-tutorial-for-beginners)
- [Plotly tutorial @ GeeksforGeeks](https://www.geeksforgeeks.org/python-plotly-tutorial/)
- [Plotly Python Open Source Graphing Library Fundamentals](https://plotly.com/python/plotly-fundamentals/)

`pandas` tutorials:
- [pandas.DataFrame.plot](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.plot.html)
- [Chart visualization](https://pandas.pydata.org/pandas-docs/stable/user_guide/visualization.html)

Guides:
- [Visual data analysis in Python. Part 1. Visualization: from Simple Distributions to Dimensionality Reduction @ mlcourse.ai](https://mlcourse.ai/book/topic02/topic02_visual_data_analysis.html)
- [Visual data analysis in Python. Part 2. Overview of Seaborn, Matplotlib and Plotly libraries @ mlcourse.ai](https://mlcourse.ai/book/topic02/topic02_additional_seaborn_matplotlib_plotly.html)

### 2.2 Dataset

[Goodreads Books - 31 Features](https://www.kaggle.com/datasets/austinreese/goodreads-books).

### 2.3 Data preprocessing

See code blocks in chapter 2.3 of [lecture 2 in russian](lecture_2.ipynb). Steps:
- Dropping irrelevant features &ndash; columns in our dataframe
- Parsing publishing year: drop NaN and extracting year using regular expression, adding new feature `year_published`
- Removing brackets in `series` column using regular expression
- Adding new feature `books_in_series_count` from `books_in_series` feature
- Adding new feature `awards_count` from `awards` feature
- Printing the most awarded book title and awards count
- Transforming string data in `author` feature into list of strings
- Adding new feature `genre` from `genre_and_votes` feature by transforming data (extracting genre names only) and renaming `genre_and_votes` into `genre` (in-place)

> Read:
> - [Visual data analysis in Python. Part 1. Visualization: from Simple Distributions to Dimensionality Reduction @ mlcourse.ai](https://mlcourse.ai/book/topic02/topic02_visual_data_analysis.html)
> - [Visual data analysis in Python. Part 2. Overview of Seaborn, Matplotlib and Plotly libraries @ mlcourse.ai](https://mlcourse.ai/book/topic02/topic02_additional_seaborn_matplotlib_plotly.html)

### 2.4 Interactive plot in `matplotlib`

See code blocks in chapter 2.4 of [lecture 2 in russian](lecture_2.ipynb). Data are grouped by publishing year (DataFrameGroupBy object), using `.agg()` function we aggregate data in `rating_count`, `five_star_ratings`, `four_star_ratings`, `three_star_ratings`, `two_star_ratings` and `one_star_ratings` using `sum` function. Important code lines are commented out. Interactive plot contains clickable buttons, clickable data series labels in the legend and slider for year value setting.

### 2.5 Interactive plot in `plotly`

See code blocks in chapter 2.5 of [lecture 2 in russian](lecture_2.ipynb). Plot has same functionality as interactive plot in `matplotlib`, but is much simpler in terms of code complexity and prettier in visualization style.

### 2.6 Plotting by `pandas`

`.hist()` example by calling from DataFrame object in chapter 2.6 of [lecture 2 in russian](lecture_2.ipynb).

### 2.7 Plotting by `seaborn`

Boxplot in `seaborn`, styling each subplot example in chapter 2.7 of [lecture 2 in russian](lecture_2.ipynb).

### 2.8 Different plot examples

See code blocks in chapter 2.8 of [lecture 2 in russian](lecture_2.ipynb).

- Adding new feature `series_type` based on books count in `series`
- `.explode()` example
- `.value_counts()` example
- `seaborn.countplot` example
- `seaborn.pairplot` example
- `seaborn.heatmap` example
- `seaborn.violinplot` example
- several interactive plots
- `scipy.stats.probplot` example (QQ plot)

### 2.9 Export plot in raster and vector formats

See code blocks in chapter 2.9 of [lecture 2 in russian](lecture_2.ipynb).

### 2.10 `plotly` `Dash`

See code blocks in chapter 2.10 of [lecture 2 in russian](lecture_2.ipynb).