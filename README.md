# Boilerplate Todo-App for FastAPI, MongoDB, Motor Projects

## Pre-Requisites
* Python 3.11+
* [Poetry](https://python-poetry.org/docs/#installation) installed
* Docker installed

## Getting Started

```
cd docker
docker-compose up --build
```

open http://localhost:8000/

## Development

#### Using Tilt (recommended)

* Install [Tilt](https://docs.tilt.dev/)

```bash
tilt up
```

Tilt will run `./docker/docker-compose.yaml`, observes changes at `./todoapp` and automatically rebuilds the containers.

Clean up:

```bash
tilt down
```

#### Not using Tilt
Rename the `.env.sample` file to `.env` within the project folder or export the `MONGODB_URI` environment variable manually with `$ export MONGODB_URI=<YOUR_URI>`. The application can be started in development mode via Poetry.

```bash
poetry install
poetry run start
```

open http://localhost:8001

## Running tests locally using Tox

If you want to run tests and checks locally in an isolated environment. Useful if you want to make sure that all tests pass before passing new code to a CI/CD pipeline.

Enter poetry shell where all the dependencies are available:

```bash
poetry shell
```

Run all tests and stylechecks.

```bash
tox
```

Run tests and stylechecks seperately.

```bash
tox -e test_app
tox -e checks
```

## Credits

* [`Py-Pkgs`](https://py-pkgs.org)
* [FastAPI Best Practices](https://github.com/zhanymkanov/fastapi-best-practices)
