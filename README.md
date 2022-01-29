# python-build

### `build-and-publish`

A reusable workflow for building and publishing Python packages to PyPI.

#### Example usage

```yaml
name: Release

on:
  release:
    types: [published]

jobs:
  build-and-publish:
    uses: antonagestam/python-build/.github/workflows/release.yaml@main
    with:
      requirements_file: "setup.py"
    secrets:
      pypi_api_token: ${{ secrets.PYPI_API_TOKEN }}
```

### `pre-commit`

A reusable workflow for running [pre-commit] checks in Github Actions.

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
    name: Static analysis
    uses: antonagestam/python-build/.github/workflows/pre-commit.yaml@feature/pre-commit
    with:
      python-version: "3.10"
```
