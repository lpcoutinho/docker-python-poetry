<!--
 Copyright (c) 2023 Luiz Paulo Coutinho
 
This software is adapted from Joseph Hale and released under the MIT License.
 https://opensource.org/licenses/MIT
-->
# [Python Poetry](https://github.com/python-poetry/poetry) in Docker
Robust, lightweight, configurable `python-poetry` Docker images for any use
case.

*NOTE: This repository is **not** an official project from the creators of
Python Poetry. Hopefully you find it useful anyway!*


## Quickstart
Most of the time, you will be using these images as a base image for your own
Dockerfiles (e.g. devcontainers, building Python applications, etc.)
```Dockerfile
FROM thehale/python-poetry
# Your build steps here.
```

However, you can also download and run the latest `python-poetry` Docker image
by pulling it from DockerHub.
```
docker pull thehale/python-poetry
docker run --rm thehale/python-poetry poetry --version
```

There are tagged images for all the latest stable versions of `python-poetry`
for all versions of Python that Poetry supports (>3.7). You can see the [full
tag list on DockerHub](https://hub.docker.com/r/thehale/python-poetry/tags).

## Build Your Own Image
This repo automatically builds images for the latest stable versions of
`python-poetry` for all supported versions of Python (>3.7).
 - You can see the full build matrix in
   [.github/workflows/docker-image.yml](https://github.com/thehale/docker-python-poetry/blob/master/.github/workflows/docker-image.yml)

However, if you need a combination that isn't automatically built, you can
easily create your own by modifying the command below to contain your preferred
values for `POETRY_VERSION` and `PYTHON_IMAGE_TAG`:
```bash
make build-version \
    POETRY_VERSION="1.1.13" \
    PYTHON_IMAGE_TAG="3.10-slim"
```

## References
https://github.com/orgs/python-poetry/discussions/1879