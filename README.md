# Python Poetry mono-repo

This is an example of how to organize a repo containing multiple independent services (`service1` and `service2`) and also a common library shared between the services (`common`).

Each module is placed under `python_monorepo` in its own folder, with its own `pyproject.toml` specifying dependencies. 
The services specify their dependence on the common library with a [path dependency](https://python-poetry.org/docs/dependency-specification/#path-dependencies).

## Local development
To allow ease of development, a `pyproject.toml` is placed at the root of the project, referencing all sub-modules as dependencies. This allows your editor to use one virtual environment for all the modules. 

Install locally with
```shell
poetry install
```
and run e.g.
```
poetry run python python_monorepo/service1/service1/main.py
```
