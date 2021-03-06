# OpenAPI typed

[![CircleCI](https://circleci.com/gh/meeshkan/openapi-typed-2.svg?style=svg)](https://circleci.com/gh/meeshkan/openapi-typed-2)
[![PyPI](https://img.shields.io/pypi/dm/openapi-typed-2.svg)](https://pypi.org/project/openapi-typed-2/)
[![PyPi](https://img.shields.io/pypi/pyversions/openapi-typed-2)](https://pypi.org/project/openapi-typed-2/)
[![License](https://img.shields.io/pypi/l/openapi-typed-2)](LICENSE)

Python typings for [OpenAPI](https://swagger.io/specification/) using [`dataclass`](https://docs.python.org/3/library/dataclasses.html).

## Installation

Install package from [PyPI](https://pypi.org/project/openapi-typed-2/).

```bash
pip install openapi-typed-2
```

## Usage

```python
from openapi_typed_2 import OpenAPIObject, Info

# Valid OpenAPIObject
openapi_valid = OpenAPIObject(
    openapi="3.0.0",
    info=Info(
        title="My API",
        version="0.0.0")
    )

# Invalid OpenAPIObject
openapi_invalid = OpenAPIObject(
    openap="3.0.0",  # Type-check error, unknown attribute
    info=Info(
        title="My API"  # Type-check error, missing attribute `version`
    )
)
```

## Development

Install development dependencies:

```bash
pip install -e '.[dev]'
```

Do codegen (necessary for type checking and tests):

```bash
python setup.py gen
```


Run tests:

```bash
pytest
# OR
python setup.py test
```

Run type-checks with `mypy`:

```bash
mypy openapi_typed
```

Build package:

```bash
python setup.py dist
```

## Contributing

Thanks for wanting to contribute! We will soon have a contributing page
detaling how to contribute. Meanwhile, feel free to star this repository, open issues and ask for more features and support.

Please note that this project is governed by the [Meeshkan Community Code of Conduct](https://github.com/meeshkan/code-of-conduct). By participating in this project, you agree to abide by its terms.
