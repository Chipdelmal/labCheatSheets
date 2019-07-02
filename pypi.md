# Pypi


To update the package at Pypi, change the version number in **setup.py** and run the following:

```bash
python3 setup.py sdist bdist_wheel
twine check dist/*
python -m twine upload dist/PKG_NAME-PKG_VERSION.tar.gz --skip-existing
```

Updating the package in TestPypi:

```bash
python3 setup.py sdist bdist_wheel
twine check dist/*
python3 -m twine upload --repository-url https://test.pypi.org/legacy/ dist/PKG_NAME-PKG_VERSION.tar.gz  --skip-existing
```
