
---
title: "Workshop 1: Programming Fundamentals"
author: "S. Sumuthuni"
output:
  html_document:
    toc: true
    toc_float: true
    code_folding: show
---

# Introduction

This workshop introduces the fundamental concepts of R programming and the RStudio environment for scientific data analysis. It focuses on developing essential skills in data manipulation, basic coding, and data visualisation to support reproducible and efficient research workflows.

# Run calculations

```{r}
2 + 1
1:30
6 * 2
6 / 2
```

The following are examples of incomplete or incorrect code. They are displayed but not run, so the HTML document can still knit successfully.

```{r, eval=FALSE}
# Incorrect modulo-style expression
6 % 2
```

# Functions and arguments

```{r}
year_old <- 25.7
round(year_old)
floor(year_old)
```

For instance, `round()` has an argument that lets you specify how many decimal places you want.

```{r}
year_old <- 25.765
round(year_old, 2)
```

# Objects and the assignment operator

## Saving a single value

```{r}
coral_count <- 42
coral_count
```

## Saving a vector of fish lengths

```{r}
fish_lengths <- c(124, 152, 98, 221, 146)
fish_lengths
```

## Manipulating objects

```{r}
coral_count + 1
coral_count + coral_count

Coral_Count <- 1   # R is case-sensitive
coral_count + Coral_Count
```

# Object naming rules

These examples are invalid object names, so they are shown without being executed.

```{r, eval=FALSE}
01_age <- 25      # Cannot start an object name with a number
!_age <- 25       # Avoid special symbols
coral count <- 25 # Spaces are not allowed in ordinary object names
```

Spaces can be used only when the object name is enclosed in backticks:

```{r}
`coral count` <- 25
`coral count`
```

# Debugging code

## Field survey data

```{r}
quadrat_area_m2 <- 0.25
number_of_quadrats <- 16
total_area_surveyed <- quadrat_area_m2 * number_of_quadrats
print(total_area_surveyed)
```

# Installing and loading packages

If the packages are installed, they can be loaded as follows:

```{r, message=FALSE, warning=FALSE}
if (requireNamespace("dplyr", quietly = TRUE)) library(dplyr)
if (requireNamespace("ggplot2", quietly = TRUE)) library(ggplot2)
```

# Data types

```{r}
site_name <- "Heron_Island"
transect_depth_m <- 12.5
bleaching_present <- TRUE
```

## Check using `class()`

```{r}
class(site_name)
class(transect_depth_m)
class(bleaching_present)
```

## Check using `str()`

```{r}
str(site_name)
str(transect_depth_m)
str(bleaching_present)
```

# Exercise: rounding numbers

```{r}
years_old <- 25.765
round(years_old, 2)
```

# Data structures

## Vectors

```{r}
fish_lengths <- c(124, 152, 98, 221, 146)
coral_spp <- c("Porites", "Acropora", "Montastrea")

fish_lengths
coral_spp
```

When different data types are combined in an atomic vector, R converts them to a common type:

```{r}
notes_vector <- c("Acropora", 27.5, TRUE)
notes_vector
```

## Lists

A list can store different data types without converting them all to the same type.

```{r}
notes <- list("Acropora", 27.5, TRUE)
notes
notes[[1]]
```

# Data frames and tibbles

```{r}
my_data_frame <- data.frame(
  no = c(1, 2, 3),
  genus = c("Plectropomus", "Scarus", "Pomacentrus"),
  present = c(TRUE, FALSE, TRUE)
)

my_data_frame
str(my_data_frame)
```

# Save the data frame as a CSV file

It is better to save the file using a relative path inside your R project. The following code creates an `output` folder if it does not already exist and saves the CSV there.

```{r}
if (!dir.exists("output")) {
  dir.create("output")
}

write.csv(
  my_data_frame,
  "output/my_data_frame.csv",
  row.names = FALSE
)
```

# Change a column type

Convert the `no` column from numeric to factor:

```{r}
my_data_frame$no <- as.factor(my_data_frame$no)
str(my_data_frame)
```




