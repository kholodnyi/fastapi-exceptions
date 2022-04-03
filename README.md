# [FastAPI](https://fastapi.tiangolo.com/) exceptions

## Introduction

`fastapi-exceptions` is a set of standard http exceptions based on starlette exceptions.
## Installation

```shell
> pip install fastapi-exceptions
```

## Usage

Instead of duplication of exceptions codes and their details for standard cases:

```python
from fastapi import HTTPException
from starlette import status

# some app logic ...
    raise HTTPException(
        status_code=status.HTTP_401_UNAUTHORIZED,
        detail='Authentication credentials were not provided',
    )
```

you can simply import exceptions and use wherever you need:
```python
from fastapi_exceptions.exceptions import NotAuthenticated

# some app logic ...
    raise NotAuthenticated()
```

and, of course, modify details if needed:
```python
# some app logic ...
    raise NotAuthenticated(detail='No authentication header')
```