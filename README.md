# omni-docs

ENP.One system and infrastructure documentation, written using [MkDocs](https://www.mkdocs.org/)

* [building](#building)
* [editing](#editing)

## building

1. Install [Pipenv](https://docs.pipenv.org/en/latest/)
2. Synchronize environment
3. Build documentation

```shell
# Install pipenv
pip install pipenv --user
# Synchronize
pipenv sync
# Build docs
pipenv run mkdocs build
```

The docs are now located in the `site/` directory and can be served as static HTML. See [MkDocs deployment](https://www.mkdocs.org/#deploying)

## editing

1. Install [Pipenv](https://docs.pipenv.org/en/latest/)
2. Synchronize environment, with development dependencies
3. Run development server

```shell
# Install pipenv
pip install pipenv --user
# Synchronize, with dev deps
pipenv sync --dev
# Run dev server
pipenv run mkdocs serve
```

The development server is available at http://localhost:8000 and will automatically refresh with any changes made to the local files.