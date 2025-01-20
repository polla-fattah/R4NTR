---
title: Tempo
slug: chapter00
order: 030
mermaid: false
abstract: >
  The tools we use have a profound and devious influence on our thinking habits, and therefore, on our thinking abilities.
  <br>—Edsger W. Dijkstra
---

## Basic Exploratory Analysis

Exploratory Data Analysis (EDA) is an essential first step in understanding the structure and patterns within a dataset. This section delves into the tools and techniques for summarizing, describing, and aggregating data in R. These operations provide a foundation for deeper analysis by giving insights into the dataset's shape, central tendencies, variability, and relationships.


### Summarizing Data

R provides several built-in functions to summarize and explore the structure of datasets. These functions allow you to quickly understand the dimensions, variable types, and contents of your data.

1. **Using `summary()`**

    The `summary()` function generates a comprehensive summary of each column in a data frame or matrix. It provides statistics such as the minimum, maximum, mean, median, and quartiles for numeric data, and counts for categorical data.

    ```r
    # Use the iris dataset
    data("iris")

    # Generate a summary
    print("Summary of the iris dataset:")
    summary(iris)
    ```

    **Output in R Console**:

    ```bash
      Sepal.Length    Sepal.Width     Petal.Length    Petal.Width          Species  
    Min.   :4.300   Min.   :2.000   Min.   :1.000   Min.   :0.100   setosa    :50  
    1st Qu.:5.100   1st Qu.:2.800   1st Qu.:1.600   1st Qu.:0.300   versicolor:50  
    Median :5.800   Median :3.000   Median :4.350   Median :1.300   virginica :50  
    Mean   :5.843   Mean   :3.057   Mean   :3.758   Mean   :1.199                  
    3rd Qu.:6.400   3rd Qu.:3.300   3rd Qu.:5.100   3rd Qu.:1.800                  
    Max.   :7.900   Max.   :4.400   Max.   :6.900   Max.   :2.500                  
    ```

2. **Using `str()`**

    The `str()` function provides an overview of the dataset’s structure, showing the data types and a preview of the contents for each variable.

    ```r
    # Examine the structure of the iris dataset
    print("Structure of the iris dataset:")
    str(iris)
    ```

    **Output in R Console**:

    ```bash
    'data.frame':	150 obs. of  5 variables:
    $ Sepal.Length: num  5.1 4.9 4.7 4.6 5 ...
    $ Sepal.Width : num  3.5 3 3.2 3.1 3.6 ...
    $ Petal.Length: num  1.4 1.4 1.3 1.5 1.4 ...
    $ Petal.Width : num  0.2 0.2 0.2 0.2 0.2 ...
    $ Species     : Factor w/ 3 levels "setosa","versicolor","virginica": 1 1 1 1 1 ...
    ```

3. **Using `head()` and `tail()`**

    The `head()` and `tail()` functions allow you to view the first or last few rows of a dataset, providing a quick snapshot of its content.

    ```r
    # View the first 6 rows
    print("First 6 rows of the iris dataset:")
    head(iris)

    # View the last 6 rows
    print("Last 6 rows of the iris dataset:")
    tail(iris)
    ```

    **Output in R Console**:

    ```bash
    First 6 rows of the iris dataset:
      Sepal.Length Sepal.Width Petal.Length Petal.Width Species
    1          5.1         3.5          1.4         0.2  setosa
    2          4.9         3.0          1.4         0.2  setosa
    3          4.7         3.2          1.3         0.2  setosa
    4          4.6         3.1          1.5         0.2  setosa
    5          5.0         3.6          1.4         0.2  setosa
    6          5.4         3.9          1.7         0.4  setosa

    Last 6 rows of the iris dataset:
        Sepal.Length Sepal.Width Petal.Length Petal.Width   Species
    145          6.7         3.3          5.7         2.5 virginica
    146          6.7         3.0          5.2         2.3 virginica
    147          6.3         2.5          5.0         1.9 virginica
    148          6.5         3.0          5.2         2.0 virginica
    149          6.2         3.4          5.4         2.3 virginica
    150          5.9         3.0          5.1         1.8 virginica
    ```

    By default, the `head()` and `tail()` functions display the first or last 6 rows of a dataset. However, you can customize the number of rows displayed using the `n` argument.

    ```r
    # View the first 3 rows of the dataset
    print("First 3 rows of the iris dataset:")
    head(iris, n = 3)
    ```

    **Output in R Console**:

    ```bash
    First 3 rows of the iris dataset:
      Sepal.Length Sepal.Width Petal.Length Petal.Width Species
    1          5.1         3.5          1.4         0.2  setosa
    2          4.9         3.0          1.4         0.2  setosa
    3          4.7         3.2          1.3         0.2  setosa
    ```


### Calculating Summary Statistics

Summary statistics provide essential information about the central tendency, spread, and variability of data, helping to identify patterns and anomalies. R offers a range of built-in functions to compute these statistics, allowing for detailed exploration of numeric data.

Summary statistics are indispensable for:

- **Data Cleaning**: Detecting anomalies such as outliers or incorrect data entries.
- **Comparative Analysis**: Understanding differences between datasets or groups.
- **Visualization Preparation**: Choosing the right plot or chart based on data distribution.
- **Model Validation**: Assessing assumptions such as normality or variability.

#### Additional Summary Statistics

While mean, median, variance, and standard deviation are common, other statistics can provide valuable insights:

1. **Range**: The difference between the maximum and minimum values.
2. **IQR (Interquartile Range)**: The spread of the middle 50% of the data.
3. **Quantiles**: Dividing data into intervals with equal probabilities.

---

#### Expanded Example: Comprehensive Statistics for a Numeric Column

```r
# Calculate comprehensive statistics for Sepal.Length
sepal_length <- iris$Sepal.Length

mean_val <- mean(sepal_length)
median_val <- median(sepal_length)
var_val <- var(sepal_length)
sd_val <- sd(sepal_length)
range_val <- range(sepal_length)
iqr_val <- IQR(sepal_length)
quantiles <- quantile(sepal_length, probs = c(0.25, 0.5, 0.75))

print(paste("Mean:", mean_val))
print(paste("Median:", median_val))
print(paste("Variance:", var_val))
print(paste("Standard Deviation:", sd_val))
print(paste("Range:", paste(range_val, collapse = " - ")))
print(paste("IQR:", iqr_val))
print("Quantiles:")
print(quantiles)
```

**Output in R Console**:

```bash
[1] "Mean: 5.84333333333333"
[1] "Median: 5.8"
[1] "Variance: 0.685693512304251"
[1] "Standard Deviation: 0.828066127977863"
[1] "Range: 4.3 - 7.9"
[1] "IQR: 1.3"
Quantiles:
  25%   50%   75% 
5.100 5.800 6.400 
```

---

#### Applying Summary Statistics to Multiple Columns

R allows you to compute summary statistics for all numeric columns in a dataset simultaneously using the `summary()` function.

```r
# Summary statistics for the entire iris dataset
print("Summary of the iris dataset:")
summary(iris)
```

**Output in R Console**:

```bash
   Sepal.Length    Sepal.Width     Petal.Length    Petal.Width          Species  
 Min.   :4.300   Min.   :2.000   Min.   :1.000   Min.   :0.100   setosa    :50  
 1st Qu.:5.100   1st Qu.:2.800   1st Qu.:1.600   1st Qu.:0.300   versicolor:50  
 Median :5.800   Median :3.000   Median :4.350   Median :1.300   virginica :50  
 Mean   :5.843   Mean   :3.057   Mean   :3.758   Mean   :1.199                  
 3rd Qu.:6.400   3rd Qu.:3.300   3rd Qu.:5.100   3rd Qu.:1.800                  
 Max.   :7.900   Max.   :4.400   Max.   :6.900   Max.   :2.500                  
```
















### Aggregating Data

Aggregation allows you to compute summary statistics for subsets of your data, often grouped by a categorical variable.

An example on Mean Sepal.Length by Species

```r
# Aggregate Sepal.Length by Species
agg_data <- aggregate(Sepal.Length ~ Species, data = iris, FUN = mean)
print("Mean Sepal.Length by Species:")
print(agg_data)
```

**Output in R Console**:

```bash
      Species Sepal.Length
1      setosa       5.006
2  versicolor       5.936
3   virginica       6.588
```

The `~` symbol in R is used to define a formula, which specifies the relationship between a dependent variable and one or more independent variables. In the context of `aggregate()`, it indicates that the dependent variable (on the left of `~`) should be summarized based on the levels of the independent variable (on the right of `~`).

**Example**:

```r
# Aggregate Sepal.Length by Species
agg_data <- aggregate(Sepal.Length ~ Species, data = iris, FUN = mean)
print("Mean Sepal.Length by Species:")
print(agg_data)
```

**Explanation**:
- `Sepal.Length ~ Species`: Summarize `Sepal.Length` grouped by the levels of `Species`.
- `data = iris`: Specifies the dataset to use.
- `FUN = mean`: Indicates the function to apply (mean in this case).

**Output in R Console**:
```bash
      Species Sepal.Length
1      setosa       5.006
2  versicolor       5.936
3   virginica       6.588
```

To clarify the formula syntax further:
- The left-hand side of `~` (`Sepal.Length`) is the variable to summarize.
- The right-hand side of `~` (`Species`) is the grouping variable.

You can use multiple functions to summarize the data by extending the formula notation.

```r
# Aggregate multiple statistics
agg_multiple <- aggregate(Sepal.Length ~ Species, data = iris, 
                          FUN = function(x) c(mean = mean(x), sd = sd(x)))
print("Mean and SD of Sepal.Length by Species:")
print(agg_multiple)
```

**Output in R Console**:
```bash
      Species Sepal.Length.mean Sepal.Length.sd
1      setosa           5.006         0.3524897
2  versicolor           5.936         0.5161711
3   virginica           6.588         0.6358796
```

This demonstrates how flexible `aggregate()` can be when analyzing data.
