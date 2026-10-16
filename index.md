# covr2

**Code coverage without the unnecessary suffering.**

## Why covr2?

Because I was tired of fighting `covr`…

My code passes locally. It passes in CI/CD across different operating
systems and R versions. Everything works. Then coverage fails.

No useful message. No report. No clue. Just failure, followed by another
round of tedious debugging to figure out what the hell happened.

`covr` modifies your code’s AST to instrument it for coverage. Sometimes
that instrumentation breaks perfectly valid code, yet you’re left
debugging your code instead of the coverage tool. Even the original
maintainers acknowledge that instrumentation can change program
behaviour. That’s understandable. **What’s not understandable is
throwing away the entire report when something goes wrong.**

## The goal

`covr2` aims to make coverage reporting robust by default.

- **Fail gracefully.** When instrumentation or tests encounter errors,
  preserve whatever coverage results can still be collected and report
  what went wrong.
- **Keep what works.** Retain the familiar `covr` workflow and coverage
  reports.
- **Make CI/CD painless.** Generate coverage reports and badges, ready
  for publication to GitHub Pages.
- **Reduce configuration.** Provide the reporting dependencies,
  including `DT` and `htmltools`, out of the box. No more assembling
  three scripts and half a dozen dependencies just to publish a coverage
  report.

The philosophy is simple: coverage tools should help developers, not
create another debugging project.

If your tests pass but coverage instrumentation breaks, you should get
useful diagnostics and whatever results remain available—not an empty
directory and another afternoon wasted.

**Less debugging the coverage tool. More developing software.**

# Installation

``` r

install.packages("covr2")

# For devel version
devtools::install_github("munoztd0/covr22")
```

``` r

usethis::use_github_action("test-coverage")
```

# Usage

For local development a coverage report can be used to inspect coverage
for each line in your package. *Note* requires the
[DT](https://github.com/rstudio/DT) package to be installed.

``` r

library(covr2)

# If run with no arguments implicitly calls `package_coverage()`
report()
```
