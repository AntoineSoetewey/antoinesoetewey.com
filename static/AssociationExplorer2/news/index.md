# Changelog

## AssociationExplorer2 0.1.6

### pkgdown

- Added pkgdown configuration and GitHub Actions workflow for site
  builds.
- Updated ignored files to exclude pkgdown outputs and site artifacts.
- Added the public pkgdown website URL to the package metadata.
- No functional changes to the package code or Shiny application.

## AssociationExplorer2 0.1.1 to 0.1.5

### Maintenance release (CRAN resubmission)

- Updated the `Title` field in the DESCRIPTION file to meet CRAN Title
  Case requirements.
- Revised the `Authors@R` field to remove deprecated comment elements.
- Updated the `inst/CITATION` file to use
  [`bibentry()`](https://rdrr.io/r/utils/bibentry.html) instead of the
  deprecated [`citEntry()`](https://rdrr.io/r/utils/citEntry.html).
- Clarified CSV input format requirements in the user interface and
  documentation (comma-separated values and dot decimals).
- No functional changes to the package code or Shiny application.

## AssociationExplorer2 0.1.0

### Initial CRAN release

- First published version of the **AssociationExplorer2** package.
- Provides an interactive Shiny application for exploring statistical
  associations.
- Includes:
  - Correlation networks for numeric–numeric, numeric–categorical, and
    categorical–categorical associations.
  - Bivariate visualizations (scatter plots, mean plots, contingency
    tables).
  - Support for **survey weights** in applicable computations \[see
    <https://github.com/AntoineSoetewey/AssociationExplorer2/commit/72725331a2b461f534355eb4b65051e088efb471>\].
  - **Range-based filtering** of association strengths (minimum and
    maximum thresholds) \[see
    <https://github.com/AntoineSoetewey/AssociationExplorer2/commit/ed89fc139b4d3c2e818a25a7a98c9d48b720f386>\].
  - Data upload interface supporting CSV and Excel files.
- Includes a small demonstration dataset for testing and illustration.
- Provides the
  [`run_associationexplorer()`](https://antoinesoetewey.com/associationexplorer2/reference/run_associationexplorer.md)
  function to launch the application.
