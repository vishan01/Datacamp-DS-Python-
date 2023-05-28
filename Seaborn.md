# Introduction to Seaborn

Seaborn is a powerful data visualization library in Python that provides a high-level interface for creating informative and attractive statistical graphics. It is built on top of Matplotlib, another popular plotting library. Seaborn is particularly useful for working with structured datasets and producing visually appealing visualizations.

## Advantages of Seaborn
1. **Easy to use:** Seaborn provides a simple and intuitive API for creating various types of plots, allowing users to quickly generate visualizations with just a few lines of code.
2. **Works well with pandas:** Seaborn seamlessly integrates with Pandas, a popular data manipulation library in Python. This integration makes it easy to visualize Pandas DataFrames and Series directly using Seaborn functions.
3. **Built on top of Matplotlib:** Seaborn enhances Matplotlib's capabilities by providing a higher-level interface and introducing additional plot types and styles. It takes advantage of Matplotlib's functionality while simplifying the code required to create visually appealing plots.

## Getting Started

To use Seaborn, you need to import it along with Matplotlib:

```python
import seaborn as sns
import matplotlib.pyplot as plt
```

## Scatter Plot

Scatter plots are useful for visualizing the relationship between two continuous variables. Seaborn provides a convenient function for creating scatter plots:

```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.scatterplot(x, y)
plt.show()
```

## Count Plot

Count plots are used to display the frequency of categorical variables. Seaborn's `countplot()` function is specifically designed for this purpose:

```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.countplot(x='category')
plt.show()
```

## Working with DataFrames

Seaborn integrates well with Pandas DataFrames, allowing you to easily visualize data from structured datasets:

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

df = pd.DataFrame(data)
sns.countplot(x='key', data=df)
plt.show()
```

## Tidy Dataframes

Seaborn works best with tidy dataframes, which follow the principles of tidy data. Tidy data is organized in a way that each variable has its own column, each observation has its own row, and each value has its own cell. Seaborn's plotting functions are optimized for working with this tidy data format.

## Adding a Third Variable with Hue

You can enhance your plots by incorporating a third variable using the `hue` parameter. It allows you to differentiate data points based on a categorical variable:

```python
import matplotlib.pyplot as plt
import seaborn as sns

sns.scatterplot(x, y, data=df, hue='variable')
plt.show()
```

## Adjusting Hue Order

You can control the order of the hue levels using the `hue_order` parameter. It allows you to specify the desired order of the categories:

```python
sns.scatterplot(x, y, data=df, hue='variable', hue_order=['level1', 'level2'])
plt.show()
```

## Customizing Hue Colors

You can assign custom colors to the hue levels by providing a dictionary of colors using the `palette` parameter:

```python
hue_colors = {'key1': 'color1', 'key2': 'color2'}
sns.scatterplot(x, y, data=df, hue='variable', palette=hue_colors)
plt.show()
```

Note: The specific colors can be specified using Matplotlib's color codes, such as named colors, RGB values, or hexadecimal color codes.

## Hue in Different Plot Types

The `hue` parameter is available in various other plot types provided by Seaborn, allowing you to incorporate an additional

 categorical variable for differentiation.
﻿# Introduction to Relational Plots and Subplots

## Relational Plot

A relational plot is used to visualize the relationship between two variables, x and y.

### Introducing `relplot()`

Instead of using a scatter plot, we can use the `relplot()` function from the seaborn library for general relational plots.

To use `relplot()`, we need to import the seaborn library:
```python
import seaborn as sns
```

#### Basic usage:
```python
sns.relplot(x, y, data, kind="scatter")
```

#### Subplots:
We can also create subplots using the `col` or `row` parameter:
```python
sns.relplot(x, y, data, kind, col or row)
```

#### Wrapping columns:
To wrap the columns in the subplot, we can use `col_wrap` parameter:
```python
sns.relplot(x, y, data, kind, col, col_wrap)
```

#### Order of columns:
To specify the order of the columns, we can use the `col_order` parameter:
```python
sns.relplot(x, y, data, kind, col, col_wrap, col_order)
```

### Customizing Scatter Plot

We can customize the scatter plot by adjusting the size, style, and transparency of the data points.

#### Deciding the size of the point:
To change the size of the points based on a variable, we can use the `size` parameter:
```python
sns.relplot(x, y, data, kind, size="variable name")
```

#### Deciding the style of the point:
To change the style of the points based on a variable, we can use the `style` parameter:
```python
sns.relplot(x, y, data, kind, style="variable name")
```

#### Adjusting the transparency of the point:
To control the transparency of the points, we can use the `alpha` parameter. The range of the `alpha` variable is [0, 1]:
```python
sns.relplot(x, y, data, kind, alpha=variable)
```

## Introduction to Line Plots

A line plot is useful for tracking the same variable over time or displaying the mean values.

### Line Plot

We can use the `line` option in `relplot()` to create a line plot:
```python
sns.relplot(x, y, data, kind="line")
```

### Subgrouping in Line Plots

We can subgroup the lines in a line plot using the `hue` or `style` parameters:
```python
sns.relplot(x, y, data, kind="line", hue, style)
```

### Creating Markers Across the Line

To create markers across the line, we can use the `markers` parameter:
```python
sns.relplot(x, y, data, kind="line", hue, markers)
```

### Ignoring Dash Lines

If we want to ignore the dash lines representing confidence intervals, we can use the `dashes=False` parameter:
```python
sns.relplot(x, y, data, kind="line", style, dashes=False)
```

### Replacing Confidence Interval with Standard Deviation

To replace the confidence interval with standard deviation, we can use the `ci="sd"` parameter:
```python
sns.relplot(x, y, data, kind="line", ci="sd")
```

These features and options in seaborn can be used to create insightful relational plots and subplots to visualize and analyze the relationships between variables.
