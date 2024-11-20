# Python Project Template

Welcome to **python-project-template**! This is a starting point for a new Python project in our organization.

This repository is a template designed to help developers quickly set up a new Python project with best practices and standardized configurations using Cookiecutter. 

## Project Purpose

This template serves as a flexible starting point for creating Python-based projects, whether for application development, data science, or other Python-focused tasks. With this template, users can generate a new project directory structure complete with essential files, configurations, and documentation templates. This allows developers to maintain consistency and quality across multiple projects.

## How It Works

This project template uses **Cookiecutter**, a tool for creating new projects from templates. With Cookiecutter, users can generate a new project by filling out a few prompts, which will then populate predefined values in the template. The generated project includes:

- Standardized project structure
- Pre-configured `dockerfile` for containerized development
- Dependency management files (`requirements.txt`, `environment.yml`)
- Basic directory setup for `src`, `tests`, and more

## Getting Started

To generate a new project based on this template, you will need to have **Cookiecutter** installed. If you haven’t installed it yet, you can do so using `pip`:

```bash
pip install cookiecutter
```

Once installed, you can create a new project by running the following command and following the prompts:

```bash
cookiecutter /path/to/this/python-project-template
```

Replace /path/to/this/template with the path to this template directory or the Git repository URL if the template is hosted online.

## Project Structure
The generated project will include the following structure:

```bash
{{ cookiecutter.project_slug }}/
.
├── .created_from
├── .bumpversion.cfg
├── CodeOwner
├── README.md
├── datas
├── dockerfile
├── docs
├── envs
│   ├── environment.yml
│   └── requirements.txt
├── examples
├── src
│   ├── backend
│   │   ├── api.py
│   │   └── {{ cookiecutter.project_name }}
│   └── frontend
└── tests
    ├── integration
    └── unitary
        └── __init__.py
```

- .created_from: Metadata file indicating the origin of the generated project (e.g., link to the template or the version used).

- .bumpversion.cfg: Configuration file for bump2version, used to manage semantic versioning of your project.

- CodeOwner: Defines code owners for specific parts of the project. Useful for managing PR reviews and approvals.

- README.md: The main documentation file for the generated project.

- datas/: Directory for storing datasets or data files used by the project. This is useful for machine learning models, analysis, or any data-driven applications. You can organize this folder by using subfolders for raw, processed, and output data.

- Dockerfile: Configuration file for Docker to containerize the application. It defines the environment and dependencies required to run the project in a container.

- docs/: Contains documentation files for the project. This could include API documentation, design documents, user guides, etc.

- envs/: Environment configuration files to manage dependencies. The requirements.txt lists Python packages for a pip-based environment, while environment.yml is for Conda environments.

- examples/: This directory holds example scripts or Jupyter notebooks demonstrating how to use the project or its components.

- src/: Source code directory for application development. Typically divided into:

  - backend/: Contains server-side code, such as APIs.
  - frontend/: Placeholder for front-end assets (e.g., HTML, CSS, JavaScript) if applicable.
- tests/: Directory for unit and integration tests to ensure code quality and functionality.

  - integration/: Tests that validate how different parts of the system work together.
  - unitary/: Unit tests for individual components.

## Running the Generated Project
After generating the project, follow these steps to set up and run the project:

1. Set up the environment: Use the requirements.txt or environment.yml to create your Python environment.

2. Build and run the Docker container (if applicable):

    ```bash
    docker build -t your_project_name .
    docker run your_project_name
    ```

This template aims to help you start your Python projects quickly, maintain consistency, and follow best practices effortlessly.

## Versioning and Releases
To ensure stability and consistency across projects generated from this template, we use bump2version for version management. Whenever a stable update or improvement is made to the template, we recommend using bump2version to create a new version and tag it.

### Using bump2version for Versioning
We follow semantic versioning (MAJOR.MINOR.PATCH) to manage template versions:

MAJOR version: Increments for incompatible API changes or major updates.
MINOR version: Increments for new features that are backwards compatible.
PATCH version: Increments for backwards-compatible bug fixes or minor improvements.
Steps to Create a New Version and Tag
Update the version number and create a tag in one step:

For a major release:
```bash
bump2version major
```
For a minor release:
```bash
bump2version minor
```
For a patch release:
```bash
bump2version patch
```
Push the changes (including the new tag) to the remote repository:

```bash
git push origin main --tags
```

### Example Workflow
If you’ve made changes and want to release version 1.2.0, you only need to run:

```bash
bump2version minor
git push origin main --tags
```
This command will:

- Increment the version in the appropriate files.
- Commit the changes with a message like Bump version: X.Y.Z → X.Y+1.0.
- Create a Git tag corresponding to the new version (e.g., v1.2.0).