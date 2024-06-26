# Revisited Magic Admin Python SDK

The (Cool) Magic Admin Python SDK provides convenient ways for developers to interact with Magic API endpoints and an array of utilities to handle [DID Token](https://magic.link/docs/auth/introduction/decentralized-id).

This package has been revisited from the original to support newer versions of python.

## Table of Contents

* [Documentation](#documentation)
* [Quick Start](#quick-start)
* [Development](#development)
* [Changelog](#changelog)
* [License](#license)

## Documentation
See the [Magic doc](https://magic.link/docs/auth/api-reference/server-side-sdks/python)!

## Installation
You can directly install the SDK with:

pip:

```
pip install cool-magic-admin
```


### Prerequisites

- Python 3.9+


## Quick Start
Before you start, you will need an API secret key. You can get one from the [Magic Dashboard](https://dashboard.magic.link/). Once you have the API secret key, you can instantiate a Magic object.

```
from magic_admin import Magic

magic = Magic(api_secret_key='<YOUR_API_SECRET_KEY>')

magic.Token.validate('DID_TOKEN')

# Read the docs to learn more! 🚀
```

Optionally if you would like, you can load the API secret key from the environment variable, `MAGIC_API_SECRET_KEY`.

```
# Set the env variable `MAGIC_API_SECRET_KEY`.

magic = Magic()
```

**Note**: The argument passed to the `Magic(...)` object takes precedence over the environment variable.

### Configure Network Strategy
The `Magic` object also takes in `retries`, `timeout` and `backoff_factor` as optional arguments at the object instantiation time so you can override those values for your application setup.

```
magic = Magic(retries=5, timeout=10, backoff_factor=0.03)
```

## Development
We would love to have you contributing to this SDK. To get started, you can clone this repository and create a virtualenv.

```
make development
```

This will create a virtualenv for all the local development dependencies that the SDK will needs.

Once it is done, you can `source` the virtualenv. It makes your local development easier!

```
source virtualenv_run/bin/activate
```

To make sure your new code works with the existing SDK, run the test against the current supported Python versions.

```
make test
```

To clean up existing virtualenv, tox log and pytest cache, do a

```
make clean
```

This repository is installed with [pre-commit](https://pre-commit.com/). All of the pre-commit hooks are run automatically with every new commit. This is to keep the codebase styling and format consistent.

You can also run the pre-commit manually. You can find all the pre-commit hooks [here](.pre-commit-config.yaml).

```
pre-commit run
```

Please also see our [CONTRIBUTING](CONTRIBUTING.md) guide for other information.

## Changelog
See [Changelog](CHANGELOG.md)

## License
See [License](LICENSE.txt)
