# Tests

In order for code to be approved and merged, it must pass the following automated checks in the CI pipeline

* [Unit tests](#unit-tests)
* [Formatting](#formatting)
* [Linting](#linting)

For convenience, there is a single script (`/scripts/ci/test.sh`) to run the faster tests (i.e. all except the integration tests). There is a also a pre-push git hook which will run this script which you may find useful to prevent failing builds.

## Formatting

We format code using [black](https://github.com/psf/black) to PEP8 standard.
Code needs to pass format checks and the build will fail if Black identifies any pending formatting changes.

During development formatting can be checked or fixed from the command line by running `black .` from within the project directory, or via integration with your code editor.
Since formatting checking uses static code analysis it can be done outside of a container as long as you have `black` installed in your current python environment.

All of the common editors/IDE's support formatting using black. See [the black docs](https://black.readthedocs.io/en/stable/editor_integration.html)

## Linting

We lint code using [flake8](http://flake8.pycqa.org/en/latest/index.html). The CI build will fail if any violations of the linting rules are found.

We use the default config for linting with the exception of line length (we adhere to Django's recommended 120 character lines).
During development, linting can be done from the command line by running `flake8 .` from within the project directory, or via integration with your code editor.

## Unit Tests

Unit tests are run with [pytest](https://docs.pytest.org/en/latest/) using the `pytest .` command. The tests are found in the `test/` directory inside each of our django apps.

Test fixtures should be created with [factoryboy](https://factoryboy.readthedocs.io/en/latest/) fixtures. See the [factories documentation](./factories.md) for more.

### Coverage

Run `pytest --cov-report html --cov` to generate a coverage report. Open the `htmlcov/index.html` file to view the report.
