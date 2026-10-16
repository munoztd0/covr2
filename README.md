# covr <img src="man/figures/logo.png" align="right" />

**Code coverage without the unnecessary suffering.**

<!-- badges: start -->


<!-- start badges -->
[![Check 🛠](https://github.com/munoztd0/covr2/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/munoztd0/covr2/actions/workflows/R-CMD-check.yaml)


![GitHub forks](https://img.shields.io/github/forks/munoztd0/covr2?style=social)
![GitHub repo stars](https://img.shields.io/github/stars/munoztd0/covr2?style=social)

![GitHub commit activity](https://img.shields.io/github/commit-activity/m/munoztd0/covr2)
![GitHub contributors](https://img.shields.io/github/contributors/munoztd0/covr2)
![GitHub last commit](https://img.shields.io/github/last-commit/munoztd0/covr2)
![GitHub pull requests](https://img.shields.io/github/issues-pr/munoztd0/covr2)
![GitHub repo size](https://img.shields.io/github/repo-size/munoztd0/covr2)
[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
[![Current Version](https://img.shields.io/github/r-package/v/munoztd0/covr2/main?color=purple&label=package%20version)](https://github.com/munoztd0/covr2/tree/main)
[![Open Issues](https://img.shields.io/github/issues-raw/munoztd0/covr2?color=red&label=open%20issues)](https://github.com/munoztd0/covr2/issues?q=is%3Aissue+is%3Aopen+sort%3Aupdated-desc)

<!-- [![CRAN version](https://www.r-pkg.org/badges/version/covr2)](https://cran.r-project.org/package=covr2) -->

<!-- badges: end -->


## Why covr2?

Because I was tired of fighting `covr`...

My code passes locally. It passes in CI/CD across different operating systems and R versions. Everything works. Then coverage fails.

No useful message. No report. No clue. Just failure, followed by another round of tedious debugging to figure out what the hell happened.

`covr` modifies your code's AST to instrument it for coverage. Sometimes that instrumentation breaks perfectly valid code, yet you're left debugging your code instead of the coverage tool. Even the original maintainers acknowledge that instrumentation can change program behaviour. That's understandable. **What's not understandable is throwing away the entire report when something goes wrong.**

## The goal

`covr2` aims to make coverage reporting robust by default.

- **Fail gracefully.** When instrumentation or tests encounter errors, preserve whatever coverage results can still be collected and report what went wrong.
- **Keep what works.** Retain the familiar `covr` workflow and coverage reports.
- **Make CI/CD painless.** Generate coverage reports and badges, ready for publication to GitHub Pages.
- **Reduce configuration.** Provide the reporting dependencies, including `DT` and `htmltools`, out of the box. No more assembling three scripts and half a dozen dependencies just to publish a coverage report.

The philosophy is simple: coverage tools should help developers, not create another debugging project.

If your tests pass but coverage instrumentation breaks, you should get useful diagnostics and whatever results remain available—not an empty directory and another afternoon wasted.

**Less debugging the coverage tool. More developing software.**

# Installation

```r
install.packages("covr2")

# For devel version
devtools::install_github("munoztd0/covr22")
```

```r
usethis::use_github_action("test-coverage")
```

# Usage

For local development a coverage report can be used to inspect coverage for
each line in your package. *Note* requires the
[DT](https://github.com/rstudio/DT) package to be installed.

```r
library(covr2)

# If run with no arguments implicitly calls `package_coverage()`
report()
```
