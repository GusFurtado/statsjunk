<p align="center">
  <img class="hero" src="https://www.gustavofurtado.com/assets/img/projects/statsjunk.png" alt="statsjunk" width="100%">
</p>

**A collection of statistical odds and ends.**

Framework-free Python functions for common statistical tasks: correlation, regression,
spatial autocorrelation, electoral fragmentation indices, and prediction-model sample size
calculations. Every function takes plain arrays and returns a typed
[Pydantic](https://docs.pydantic.dev/) result model; invalid input raises `ValueError` rather
than failing silently or returning `NaN`.

[![PyPI](https://img.shields.io/pypi/v/statsjunk)](https://pypi.org/project/statsjunk/)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![Downloads](https://static.pepy.tech/badge/statsjunk/month)](https://pepy.tech/projects/statsjunk)
[![License](https://img.shields.io/pypi/l/statsjunk)](about.md#license)

## Features

- **Plain arrays in, typed results out**: lists or NumPy arrays go in, and a Pydantic model
  with named fields comes back, so results are easy to read, validate and serialize.
- **Loud failures**: invalid input raises `ValueError` with a message, never a silent `NaN`.
- **Intervals, not just estimates**: correlations come with confidence intervals and p-values,
  regressions with standardized coefficients and VIFs.
- **Every method cites its paper**: the reference for each function names the publication it
  implements.
- **Light**: NumPy, SciPy and Pydantic are the only dependencies.

## Example

```python
from statsjunk import compute_laakso_taagepera, compute_pearson_correlation

x = [2.1, 3.4, 1.9, 4.8, 3.9, 5.2]
y = [1.0, 1.9, 1.2, 2.8, 2.0, 3.1]
r = compute_pearson_correlation(x, y)
print(f"r = {r.r:.3f}, 95% CI [{r.low:.3f}, {r.high:.3f}], p = {r.pvalue:.4f}")
# r = 0.984, 95% CI [0.856, 0.998], p = 0.0004

parties = compute_laakso_taagepera([0.42, 0.31, 0.15, 0.12])
print(f"{parties.effective_number:.2f} effective parties")
# 3.23 effective parties
```

## Where to go next

- [Installation](installation.md): one `pip install`, no optional extras
- [Quick Start](quickstart.md): run a correlation and a sample-size calculation in a few lines
- [API Reference](reference/correlation.md): every public function and class, with the paper it implements
- [About](about.md): license, credits and contributing

## Modules

One folder per statistical domain, one module per technique inside it. Everything is also
re-exported from the top-level `statsjunk` package, so `from statsjunk import compute_pearson_correlation`
always works regardless of where a function actually lives.

| Module | Description |
|---|---|
| [`correlation`](reference/correlation.md) | Pearson and Spearman correlation with confidence intervals, plus the shared Fisher z-transformation |
| [`regression`](reference/regression.md) | Simple and multiple linear regression, with standardized coefficients and VIFs |
| [`spatial`](reference/spatial.md) | Global Moran's I spatial autocorrelation |
| [`elections`](reference/elections.md) | Laakso-Taagepera effective number of parties/candidates |
| [`samplesize`](reference/samplesize.md) | Minimum sample size for continuous, binary, and survival prediction models (the criteria of Riley et al., the same ones R's [`pmsampsize`](https://cran.r-project.org/package=pmsampsize) implements) |
