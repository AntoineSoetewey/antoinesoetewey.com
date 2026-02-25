# Contributing to AssociationExplorer2

Thank you for your interest in contributing to
**AssociationExplorer2**!\
Contributions of all kinds are welcome, including bug reports,
suggestions, documentation improvements, and code contributions.

This document describes how to contribute effectively and consistently.

------------------------------------------------------------------------

## How to contribute

### 1. Report issues

If you find a bug, have a question, or want to suggest an improvement,
please open an issue at:

<https://github.com/AntoineSoetewey/AssociationExplorer2/issues>

When reporting a problem, please include:

- A clear description of the issue\
- Steps to reproduce it (if applicable)\
- A minimal reproducible example when possible\
- Your R version and operating system

This helps maintainers diagnose and resolve issues efficiently.

------------------------------------------------------------------------

## 2. Propose enhancements or new features

Feature requests are welcome.\
Before opening a pull request with new functionality, please:

- Open an issue to discuss the proposal\
- Explain the motivation and intended use case\
- Consider whether the feature aligns with the package scope

This avoids duplicated work and ensures additions fit the project.

------------------------------------------------------------------------

## 3. Contributing code

### Fork the repository

If you want to submit code:

1.  Fork the repository\
2.  Create a new branch for your changes\
3.  Commit your work with clear messages\
4.  Open a pull request describing the changes

### Code style

Please follow these guidelines:

- Use **tidyverse style** for R code when reasonable\
- Avoid long lines when possible\
- Include comments where helpful\
- Keep functions focused and maintainable\
- Avoid introducing dependencies unless necessary

### Documentation

For any code change:

- Add or update Roxygen2 comments so documentation is generated
  correctly\
- Update the README or vignettes if user-facing behavior changes

### Tests (optional but appreciated)

If applicable:

- Add tests using `testthat`\
- Ensure all tests pass before submitting changes

------------------------------------------------------------------------

## 4. Running checks locally

Before opening a pull request, please verify that:

``` r

devtools::document()
devtools::check()
```

Completes without errors or warnings.

If you add new files, make sure that .Rbuildignore excludes any
non-package files (e.g., local scripts, temporary data).

------------------------------------------------------------------------

## 5. Code of Conduct

Please be respectful and constructive in discussions. While this project
does not include a formal Code of Conduct file, contributors are
expected to behave professionally and courteously.

------------------------------------------------------------------------

## 6. Licensing

By contributing, you agree that your work will be released under the MIT
license, the same license used by the package.

------------------------------------------------------------------------

Thank you!

Your contributions help improve the project and benefit all users. Thank
you for taking the time to support and enhance AssociationExplorer2!
