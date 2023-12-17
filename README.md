# reusables

### `python-publish`

A reusable workflow for building and publishing Python packages to PyPI.

- Builds package with [pypa/build].
- Verifies release tag matches version of built wheel.
- Uploads package to PyPI with [pypa/gh-action-pypi-publish].

[pypa/build]: https://github.com/pypa/build
[pypa/gh-action-pypi-publish]: https://github.com/pypa/gh-action-pypi-publish

#### Example usage

```yaml
name: Release

on:
  release:
    types: [published]

jobs:
  build-and-publish:
    uses: less-action/reusables/.github/workflows/python-publish.yaml@v11
    with:
      requirements_file: "pyproject.toml"
      environment_url: https://pypi.org/p/<your-pypi-project-name>
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
    uses: less-action/reusables/.github/workflows/pre-commit.yaml@v11
    with:
      python-version: "3.12"
```

### `python-test-build`

A reusable workflow for verifying Python package metadata.

#### Example usage

```yaml
name: CI

on:
  push:
    branches:
      - main
  pull_request:

jobs:
  check-build:
    name: Check packaging
    uses: less-action/reusables/.github/workflows/python-test-build.yaml@v11
```
