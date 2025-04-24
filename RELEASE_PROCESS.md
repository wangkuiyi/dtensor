# Release Process for dtensor

This document outlines the process for releasing new versions of the `dtensor` package to PyPI.

## Prerequisites

1. Create a PyPI account at <https://pypi.org/account/register/>
2. Create an API token at <https://pypi.org/manage/account/token/>
3. Add the token to your GitHub repository secrets as `PYPI_API_TOKEN`

## Release Process

### Automated Release using GitHub Actions

1. Update the version number in `pyproject.toml`
2. Push changes to GitHub
3. Create a new release on GitHub:
   - Go to the repository's "Releases" section
   - Click "Draft a new release"
   - Tag version: Create a new tag following semantic versioning (e.g., `v0.0.2`)
   - Release title: Same as the tag or a descriptive name
   - Description: Add release notes and changes
   - Click "Publish release"

4. The GitHub Actions workflow will automatically:
   - Build the package
   - Run checks
   - Publish to PyPI if all checks pass

### Manual Release (if needed)

If you need to release manually, run the following commands:

```bash
# Install required tools
pip install build twine

# Build the package
python -m build

# Check the package
twine check dist/*

# Upload to PyPI (you'll need your PyPI credentials)
twine upload dist/*
```

## Troubleshooting

- If the GitHub Action fails, check the workflow logs for details
- Ensure your PyPI token is correctly configured in the repository secrets
- Verify that all required metadata is present in the `pyproject.toml` file
