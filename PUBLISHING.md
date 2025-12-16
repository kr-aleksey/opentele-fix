# Publishing opentele-py313 to PyPI

## Prerequisites

Install build tools:
```bash
pip install build twine
```

## Build Package

1. Clean previous builds:
```bash
rm -rf dist/ build/ *.egg-info
```

2. Build the package:
```bash
python -m build
```

This will create two files in `dist/`:
- `opentele-py313-1.15.2.tar.gz` (source distribution)
- `opentele_py313-1.15.2-py3-none-any.whl` (wheel distribution)

## Test Package Locally

Before publishing, test the package:
```bash
pip install dist/opentele_py313-1.15.2-py3-none-any.whl
```

Test import:
```bash
python -c "from opentele.td import TDesktop; print('Success')"
```

## Publish to PyPI

### Option 1: Test PyPI (Recommended First)

Upload to Test PyPI:
```bash
python -m twine upload --repository testpypi dist/*
```

Test installation:
```bash
pip install --index-url https://test.pypi.org/simple/ opentele-py313
```

### Option 2: Production PyPI

Upload to production PyPI:
```bash
python -m twine upload dist/*
```

You'll be prompted for your PyPI credentials:
- Username: Your PyPI username or `__token__`
- Password: Your password or API token

## Using API Token (Recommended)

1. Generate token at https://pypi.org/manage/account/token/
2. Create `~/.pypirc`:
```ini
[pypi]
username = __token__
password = pypi-YOUR_TOKEN_HERE

[testpypi]
username = __token__
password = pypi-YOUR_TEST_TOKEN_HERE
```

3. Upload:
```bash
python -m twine upload dist/*
```

## Verify Publication

After publishing, verify:
```bash
pip install opentele-py313
python -c "from opentele.td import TDesktop; print('Success')"
```

## Notes

- The package is named `opentele-py313` on PyPI
- But imports still use `opentele` (e.g., `from opentele.td import TDesktop`)
- This ensures compatibility with existing code while avoiding conflicts with the original package
