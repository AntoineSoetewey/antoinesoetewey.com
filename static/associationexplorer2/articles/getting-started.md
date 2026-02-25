# Getting started

AssociationExplorer2 helps you explore associations between variables
with an interactive Shiny interface. This short tutorial covers a
typical first workflow.

## 1) Install and launch

``` r

install.packages("AssociationExplorer2")
library(AssociationExplorer2)
run_associationexplorer()
```

## 2) Load data

In the app, either:

- upload your own CSV or Excel file, or
- start with the included demonstration data.

For CSV files, use comma separators and dot decimals.

## 3) Choose analysis variables

Select the variables you want to explore and, if needed, a survey-weight
variable. The app automatically adapts visualizations to variable types
(numeric or categorical).

## 4) Adjust association filters

Use the minimum and maximum association thresholds to focus on weak,
moderate, or strong relationships depending on your objective.

## 5) Read the outputs

Use the network view to identify the strongest links, then inspect
bivariate plots and summary tables to interpret the relationships in
more detail.

## Next step

Open the function reference for full details on launching the app:

- [`run_associationexplorer()`](https://antoinesoetewey.com/associationexplorer2/reference/run_associationexplorer.md)
  in the Reference tab

## For more information

If you would like additional background, you can consult:

- the original AssociationExplorer vignette:
  <https://github.com/AntoineSoetewey/AssociationExplorer/blob/main/documentation/vignette.md>
- the accompanying published paper:
  <https://doi.org/10.1016/j.softx.2025.102483>
