# reusables

### `python-publish`

A reusable workflow for building and publishing Python packages to PyPI.

#### Example usage

```yaml
name: Release

on:
  release:
    types: [published]

jobs:
  build-and-publish:
    uses: less-action/reusables/.github/workflows/python-publish.yaml@v1
    with:
      requirements_file: "setup.py"
    secrets:
      pypi_api_token: ${{ secrets.PYPI_API_TOKEN }}
```

### `pre-commit`

A reusable workflow for running [pre-commit] checks.

[pre-commit]: https://pre-commit.com/

#### Example usage

```yaml
name: CI
on:
  push:
    branches:
      - main
  pull_request:

jobs:
  lint:
    uses: less-action/reusables/.github/workflows/pre-commit.yaml@v1
    with:
      python-version: "3.10"
```
