# reusables

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
