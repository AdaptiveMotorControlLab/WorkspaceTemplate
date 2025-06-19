
# Code & Data Guidelines

The is a hub for discussions and best practices on code management! The goal is someone can fork/clone this [template repo](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-template-repository) and start a new project easily. This was written by Mackenzie Mathis, and I thank my lab and the open-source community for many lessons learned.

## Overview

This repository is a work-in-progress template for structuring coding projects with clean, reproducible, and collaborative workflows. It includes tools and practices that streamline development, documentation, testing, and deployment.

### Core Components

1. **Code Organization**

   * Make a clear folder structure for modules, tests, and configs; try to keep this across project/s
   * Naming conventions and modular design principles, [here are useful standards](https://dmeg.cessda.eu/Data-Management-Expert-Guide/2.-Organise-Document/File-naming-and-folder-structure) to consider.

#### Recommended Directory Structure

```bash
project_name/
├── README.md
├── LICENSE
├── pyproject.toml
├── setup.cfg
├── .gitignore
├── .pre-commit-config.yaml
├── _toc.yml
├── docker/
│   └── Dockerfile
├── examples/
│   └── basic_usage.ipynb
├── placeholder (project_name)/   # Main package code
│   ├── __init__.py
│   ├── module_example.py
    ├── version.py
│   └── utils/
│       └── helpers.py
├── tests/
│   ├── __init__.py
│   ├── test_module1.py
│   └── conftest.py
├── docs/             # JupyterBook documentation
│   ├── _config.yml
│   └── index.md
└── .github/
    └── workflows/
        └── codespell.yml
        └── publish-book.yml
```

2. **Documentation**

   * [JupyterBook](https://jupyterbook.org/en/stable/intro.html) setup for comprehensive, interactive project documentation!
   * Here are [guidelines for writing readable and maintainable docstrings](https://www.datacamp.com/tutorial/docstrings-python) - this is as important as documentation!

3. **Code Formatting & Linting**

   * Formatted code makes your life and those who use/review your code easier. Standardized formatting with tools like `black` and `isort` (see the provided `.pre-commit-config.yaml`).
   * [Pre-commit hooks](https://pre-commit.com/) to automate checks before pushing code! Follow their quick Guide to do this, but in short:

   (1) install it in your dev env
   ```python
      pip install pre-commit
   ```
   (2) install the git hooks:
   ```python
   pre-commit install
   ```
   (3) Just run it on your code BEFORE you git push:
   ```python
   pre-commit run --all-files
   ```
4. **Continuous Integration**

   * Use GitHub Actions for automated testing and code quality checks
   * This template repo gies you built-in `codespell`, `publish-book` and `pre-commit` validations (go to actions in your repo to follow the guidelines to set up/also chatGPT can help ;)

5. **Containerization**

   * Docker setup for consistent development and deployment environments - this is not just an after thought, use Docker to develop and share your code!
   * Examples of `Dockerfile` and `docker-compose.yml` configurations (coming)
   * You are welcome/encouraged to use our containers: https://hub.docker.com/u/mmathislab

6. **Data Workflow Integration**

   * [DataJoint](https://www.datajoint.com/) examples for managing and querying scientific data pipelines - these are a must; use minimally for data + meta data storage, and use it to automate things you do daily (preprocessing, running DeepLabCut, etc!)
   * [Templates for common workflows and schema management are here!](https://docs.datajoint.com/elements/)


7. **Style Guide for overall code & project management**

   * Tips and practices for code, manuscripts, and figures.


---

Contributions welcome as we refine this template!


## Acknowledgement

Some items in this repo are adapted from [DeepLabCut](https://github.com/DeepLabCut/DeepLabCut), [CEBRA](https://cebra.ai/), and the [Mathis Lab of Adaptive Intelligence](https://github.com/orgs/AdaptiveMotorControlLab). It is under an Apache 2.0 License.
