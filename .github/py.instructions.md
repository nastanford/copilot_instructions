---
applyTo: "python/**"
---
# Python Project Coding Standards

- Use 2 spaces per indentation level (enforced by `.editorconfig`).
- Follow [PEP 8](https://www.python.org/dev/peps/pep-0008/) for code style and formatting.
- Use [Black](https://black.readthedocs.io/en/stable/) for automatic code formatting where possible.
- Use [isort](https://pycqa.github.io/isort/) for import sorting.
- Use [flake8](https://flake8.pycqa.org/en/latest/) for linting.
- Use type hints and [mypy](http://mypy-lang.org/) for static type checking when practical.
- Write docstrings for all public modules, classes, functions, and methods (use [Google style](https://google.github.io/styleguide/pyguide.html#38-comments-and-docstrings) or [PEP 257](https://www.python.org/dev/peps/pep-0257/)).
- Prefer virtual environments (venv, pipenv, poetry) for dependency management.
- Store dependencies in `requirements.txt` or `pyproject.toml`.
- Place tests in a `tests/` directory, mirroring the source structure.
- Use pytest for testing unless otherwise specified.
- Avoid wildcard imports (`from module import *`).
- Use logging instead of print statements for production code.
- Sensitive data (API keys, passwords) must not be hardcoded or committed.
- Use environment variables for configuration/secrets.
- Document setup and usage in `README.md`.
