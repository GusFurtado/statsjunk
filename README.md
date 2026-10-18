<p align="center">
  <a href="https://www.gustavofurtado.com/statsjunk/"><img src="https://www.gustavofurtado.com/assets/img/projects/statsjunk.png" alt="statsjunk" width="640"></a>
</p>

<p align="center">
  <b>A collection of statistical odds and ends.</b>
</p>

<p align="center">
  <a href="https://pypi.org/project/statsjunk/"><img src="https://img.shields.io/pypi/v/statsjunk" alt="PyPI"></a>
  <a href="https://pypi.org/project/statsjunk/"><img src="https://img.shields.io/pypi/pyversions/statsjunk" alt="Python versions"></a>
  <a href="https://pepy.tech/projects/statsjunk"><img src="https://static.pepy.tech/badge/statsjunk/month" alt="Downloads"></a>
  <a href="https://github.com/GusFurtado/statsjunk/actions/workflows/test.yml"><img src="https://github.com/GusFurtado/statsjunk/actions/workflows/test.yml/badge.svg" alt="Tests"></a>
  <a href="https://github.com/GusFurtado/statsjunk/blob/main/LICENSE"><img src="https://img.shields.io/pypi/l/statsjunk" alt="License"></a>
</p>

<p align="center">
  <b><a href="https://www.gustavofurtado.com/statsjunk/">Documentation</a></b>
</p>

Framework-free Python functions for common statistical tasks. Every function takes plain arrays
and returns a typed [Pydantic](https://docs.pydantic.dev/) result model; invalid input raises
`ValueError` instead of failing silently.

## Installation

```sh
pip install statsjunk
```

## What's inside

- **`correlation`**: Pearson and Spearman correlation with confidence intervals, and the Fisher z-transformation.
- **`regression`**: simple and multiple linear regression, with standardized coefficients and VIFs.
- **`spatial`**: global Moran's I spatial autocorrelation.
- **`elections`**: Laakso-Taagepera effective number of parties.
- **`samplesize`**: minimum sample size for prediction models, a port of R's [`pmsampsize`](https://cran.r-project.org/package=pmsampsize).

See the [API reference](https://www.gustavofurtado.com/statsjunk/reference/correlation/) for every function.
