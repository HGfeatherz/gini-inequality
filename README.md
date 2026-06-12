# Measuring Inequality in the Iris Dataset Using the Gini Index

Applying the **Gini Index**—a statistic traditionally used to measure wealth inequality—to biological data in order to explore variability and homogeneity within plant populations.

This project was inspired by methods introduced during my PhD (thanks Alan!), where statistical tools from economics and finance were adapted to analyse biological datasets. Rather than measuring inequality in income or wealth, the Gini coefficient can be used to quantify how uniform (or variable) plant traits are within a population.

---

## Overview

The **Gini Index** is a measure of inequality ranging from **0 to 1**:

* **0** = Perfect equality (all observations are identical)
* **1** = Maximum inequality

While commonly applied to economics, the same concept can be used to measure the consistency of biological traits.

In this project, the Gini Index is calculated for the classic **Iris dataset** to determine how homogeneous each morphological characteristic is, both across the entire dataset and within individual species.

---

## Dataset

The project uses the built-in **Iris** dataset in R (again, I like this dataset as its quite digestable and tangible for a wider auidence)

The dataset contains **150 flower samples** from three species:

* Setosa
* Versicolor
* Virginica

Each observation includes four quantitative measurements:

* Sepal Length
* Sepal Width
* Petal Length
* Petal Width

---

## Libraries Used

```r
library(gglorenz)
library(tidyverse)
library(ineq)
library(dplyr)
library(ggplot2)
```

---

## Method

The analysis follows these steps:

1. Load the Iris dataset.
2. Extract the numeric variables.
3. Calculate the Gini coefficient for each morphological measurement.
4. Repeat the analysis separately for each species.
5. Visualise inequality using a Lorenz curve.

---

## Overall Gini Coefficients

| Measurement  | Gini Index |
| ------------ | ---------: |
| Sepal Length |      0.080 |
| Sepal Width  |      0.079 |
| Petal Length |      0.261 |
| Petal Width  |      0.359 |

Looking at the complete dataset alone suggests that petal measurements display greater variability than sepal measurements. However, because the dataset contains three biologically distinct species, these values combine between-species differences with within-species variation.

---

## Species-Level Analysis

Calculating the Gini coefficient separately for each species provides a much clearer picture of trait homogeneity.

### Sepal Length

| Species    |  Gini |
| ---------- | ----: |
| Setosa     | 0.039 |
| Versicolor | 0.049 |
| Virginica  | 0.053 |

### Sepal Width

| Species    |  Gini |
| ---------- | ----: |
| Setosa     | 0.060 |
| Versicolor | 0.063 |
| Virginica  | 0.059 |

### Petal Length

| Species    |  Gini |
| ---------- | ----: |
| Setosa     | 0.063 |
| Versicolor | 0.061 |
| Virginica  | 0.055 |

### Petal Width

| Species    |      Gini |
| ---------- | --------: |
| Setosa     | **0.209** |
| Versicolor |     0.083 |
| Virginica  |     0.076 |

---

## Key Findings

Most morphological traits are highly homogeneous within species, producing relatively low Gini coefficients.

The most notable exception is **Setosa petal width**, which has a substantially higher Gini coefficient than any other measurement. This indicates greater variability in petal width for Setosa compared with the other species.

This demonstrates why analysing each species individually is important—combining multiple biological groups can obscure meaningful patterns.

---

## Visualisation

The project concludes by plotting a **Lorenz Curve** for petal width.

The Lorenz curve compares the observed distribution of measurements against the 45° line representing **perfect equality**.

* Curves close to the diagonal indicate highly uniform measurements.
* Curves that bow further from the diagonal indicate greater variability.
* The area between the curve and the diagonal corresponds to the Gini coefficient.

The Lorenz curve provides an intuitive visual representation of trait homogeneity within each species.

---

## Why This Matters

Although the Gini coefficient is most often associated with economics, it has valuable applications in biology and agriculture.

Potential uses include:

* Assessing uniformity in plant breeding programmes
* Comparing treatment effects in field trials
* Monitoring consistency in agricultural production
* Identifying traits with unusually high variability
* Supporting quality control in horticulture and manufacturing processes

Using measures of inequality in biological datasets offers an alternative perspective that complements traditional descriptive statistics such as the mean and standard deviation.

---

## Running the Project

If you want to give a it a go, clone or copy and paste the notepad, enjoy!

```bash
git clone https://github.com/yourusername/your-repository.git
```


