# Launch the AssociationExplorer2 Shiny Application

This function launches the AssociationExplorer2 Shiny application in
your default web browser. The app provides interactive tools for
exploring statistical associations, correlation networks, bivariate
visualizations, and summary tables, with optional support for survey
weights and range-based filtering of association strengths.

## Usage

``` r
run_associationexplorer(...)
```

## Arguments

- ...:

  Additional arguments passed to
  [`shiny::runApp()`](https://rdrr.io/pkg/shiny/man/runApp.html), such
  as `port` or `launch.browser`.

## Value

The function is called for its side effect of launching the app.

## Examples

``` r
if (interactive()) {
  run_associationexplorer()
}
```
