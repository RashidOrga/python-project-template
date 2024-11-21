
# Python Project Template

Welcome to **python-project-template**! This repository is a standardized starting point for new Python projects in our organization.

This template uses **Cookiecutter** to generate a project structure aligned with best practices and standardized configurations.


## Project Purpose

This template serves as a foundation for quickly initiating Python projects, whether for application development, data science, or other Python-related tasks. It ensures consistency and quality across projects within the organization.


## How It Works

### Generate a Project

1. **Install Cookiecutter** if you haven't already:
   ```bash
   pip install cookiecutter
   ```

2. **Create a project** from the template:
   ```bash
   cookiecutter /path/to/this/python-project-template
   ```
   Replace `/path/to/this/python-project-template` with the local path or the repository URL containing this template.

### Generated Structure

Here’s an overview of the generated structure:

```bash
{{ cookiecutter.project_slug }}/
├── .created_from
├── .bumpversion.cfg
├── CodeOwner
├── README.md
├── datas/
├── dockerfile
├── docs/
├── envs/
│   ├── environment.yml
│   └── requirements.txt
├── examples/
├── src/
│   ├── backend/
│   └── frontend/
└── tests/
    ├── integration/
    └── unitary/
```

### Key Points

- **`.created_from`**: Metadata file indicating the origin of the generated project.
- **`.bumpversion.cfg`**: Configuration for managing project versioning, initializing to 0.0.0.
- **`datas/`**: Folder for storing datasets or related files.
- **`envs/`**: Dependencies listed in `requirements.txt` (pip) or `environment.yml` (Conda).
- **`src/`**: Source code, organized into submodules like `backend` and `frontend`.
- **`tests/`**: Unit and integration tests to ensure code quality.

## Template Version Management

We use **bump2version** to manage the versioning of this template, following semantic versioning (**MAJOR.MINOR.PATCH**):

- **MAJOR**: Increment for major or breaking changes.
- **MINOR**: Increment for new features that are backward compatible.
- **PATCH**: Increment for bug fixes or minor improvements.

### Steps to Update and Tag a New Version

1. **Make your changes** (e.g., add files, folders, or new features to the template).
2. **Increment the version**:
   - For a major release:
     ```bash
     bump2version major
     ```
   - For a minor release:
     ```bash
     bump2version minor
     ```
   - For a patch release:
     ```bash
     bump2version patch
     ```
3. **Push the changes and the new tag**:
   ```bash
   git push origin main --tags
   ```

This workflow ensures that every change to the template is versioned and tracked consistently.
