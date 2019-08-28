# omni-docs

ENP.One system and infrastructure documentation, using [MkDocs](https://www.mkdocs.org/)

## Building

1. Install [Pipenv](https://docs.pipenv.org/en/latest/)

   ```shell
   pip install pipenv --user
   ```

2. Synchronize environment

   ```shell
   pipenv sync
   ```

3. Build documentation

   ```shell
   pipenv run mkdocs build
   ```

Built docs are now located in `site/` and can be served as static HTML. See [MkDocs deployment](https://www.mkdocs.org/#deploying)

## Editing/Developing

1. Install [Pipenv](https://docs.pipenv.org/en/latest/)

   ```shell
   pip install pipenv --user
   ```

2. Synchronize environment, with development dependencies

   ```shell
   pipenv sync --dev
   ```

3. Run development server

   ```shell
   pipenv run mkdocs serve
   ```

4. Edit away!

