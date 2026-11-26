# About

## License

statsjunk is released under the
[MIT License](https://github.com/GusFurtado/statsjunk/blob/main/LICENSE).

## Credits

Built on [NumPy](https://numpy.org), [SciPy](https://scipy.org) and
[Pydantic](https://docs.pydantic.dev/). The `samplesize` module implements the criteria of Riley et al., the same ones
R's [`pmsampsize`](https://cran.r-project.org/package=pmsampsize) implements. Each function's reference page
cites the paper it implements.

## Contributing

The project uses [uv](https://docs.astral.sh/uv/).

```bash
git clone https://github.com/GusFurtado/statsjunk
cd statsjunk
uv sync --dev
```

Before opening a pull request, make sure the checks CI runs pass:

```bash
uv run ruff check .
uv run ruff format --check .
uv run pytest
```

New functions take plain arrays, return a Pydantic model and raise `ValueError` on invalid
input, and their docstring cites the paper they implement. This site is built with
[MkDocs Material](https://squidfunk.github.io/mkdocs-material/) and
[mkdocstrings](https://mkdocstrings.github.io/); preview it with
`uv run --group docs mkdocs serve`.
