# python-build

A reusable workflow for building and publishing Python packages to PyPI.

### Example usage

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
      PYPI_API_TOKEN: ${{ secrets.PYPI_API_TOKEN }}
```
