# p6-template-pipenv

[![Build Status](https://github.com/pgollucci/p6-template-pipenv/actions/workflows/build.yml/badge.svg)](https://github.com/pgollucci/p6-template-pipenv/actions/workflows/build.yml)
[![PR Lint](https://github.com/pgollucci/p6-template-pipenv/actions/workflows/pull-request-lint.yml/badge.svg)](https://github.com/pgollucci/p6-template-pipenv/actions/workflows/pull-request-lint.yml)
[![Coverage Status](https://codecov.io/gh/pgollucci/p6-template-pipenv/branch/main/graph/badge.svg)](https://codecov.io/gh/pgollucci/p6-template-pipenv)

A concise Python project template using Pipenv (via the `uv` wrapper) with built-in support for:
- Testing (pytest + coverage)
- Linting & formatting (flake8, pylint, black, isort, pydocstyle, yamllint, bandit)
- Pre-commit hooks
- GitHub Actions CI
- Automated dependency upgrades

## Table of Contents

- [p6-template-pipenv](#p6-template-pipenv)
  - [Table of Contents](#table-of-contents)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Usage](#usage)
  - [Development](#development)
    - [Running Tests](#running-tests)
    - [Pre-commit Hooks](#pre-commit-hooks)
  - [Continuous Integration](#continuous-integration)
  - [Contributing](#contributing)
  - [License](#license)

## Prerequisites

- Python 3.14.0
- [uv](https://pypi.org/project/uv/) (wrapper for pipenv and other tools)  
- Git  

## Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/pgollucci/p6-template-pipenv.git
cd p6-template-pipenv
pip install uv
uv sync --dev
```

## Usage

This template includes a sample script at `bin/script.py`. Get help:

```bash
uv run python bin/script.py -- --help
```

Run with verbosity or debug:

```bash
uv run python bin/script.py -- --verbose
uv run python bin/script.py -- --debug
```

## Development

### Running Tests

Run all tests with coverage:

```bash
uv run pytest
```


### Pre-commit Hooks

All checks are configured via `.pre-commit-config.yaml`. To run manually:

```bash
uv run pre-commit run --all-files
```

## Continuous Integration

See `.github/workflows/` for:

- **build.yml**: runs tests, linting, formatting on push & PR
- **pull-request-lint.yml**: enforces semantic PR titles
- **upgrade-main.yml**: scheduled dependency updates
- **auto-approve.yml**: auto-approves PRs from core authors
- **diag.yml**: diagnostics troubleshooting

## Contributing

Contributions are welcome! Please:

1. Fork the repo  
2. Create a feature branch  
3. Run tests and linters locally  
4. Submit a pull request with a descriptive title  

Refer to the [pull request template](.github/pull_request_template.md).

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
