# Changelog

## covr2 (development version)

- Fix a generational garbage-collection bug when replacing traced
  functions in place, without permanently retaining their bodies or
  environments ([\#640](https://github.com/munoztd0/covr2/issues/640)).

- Tracing a package is faster, as parse data now keeps text only for
  terminal tokens ([@erkurtharun](https://github.com/erkurtharun),
  [\#644](https://github.com/munoztd0/covr2/issues/644)).

- `merge_coverage()` is much faster for packages with many traces
  ([@erkurtharun](https://github.com/erkurtharun),
  [\#643](https://github.com/munoztd0/covr2/issues/643)).

- With `options(covr2.record_tests = TRUE)`, merging coverage now
  correctly renumbers the test indices of traces that are absent from
  the first coverage object
  ([\#643](https://github.com/munoztd0/covr2/issues/643)).

- Fix compilation of the `TestCompiled` test package on R 4.6 by using
  public `REAL()` and `INTEGER()` accessors instead of the non-API
  `DATAPTR()`.

- Fix a rare edge case where `count_test` was called before
  `.current_test` has been initialized leading to crash
  ([@maksymiuks](https://github.com/maksymiuks),
  [\#631](https://github.com/munoztd0/covr2/issues/631)).

- Fix rare error in `clean_coverage_tests` where `NA` were being
  compared in `if` condition
  ([@maksymiuks](https://github.com/maksymiuks),
  [\#631](https://github.com/munoztd0/covr2/issues/631)).
