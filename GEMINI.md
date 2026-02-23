# Gemini CLI - Visualization Curriculum

This project is a data visualization curriculum based on **Altair** and **Vega-Lite**, structured as a series of interactive Jupyter notebooks. It is designed to be rendered as a **Jupyter Book**.

## Project Overview
- **Domain:** Data Science / Visualization Education.
- **Key Technologies:**
  - **Python 3.11+**: Primary programming language.
  - **Altair & Vega-Lite**: Core visualization libraries.
  - **Pandas**: Data manipulation.
  - **Jupyter Lab/Notebook**: Development environment for curriculum content.
  - **Jupyter Book / MyST**: Documentation and book generation framework.
  - **uv**: Python package and environment management.

## Project Structure
- `*.ipynb`: Individual chapters of the curriculum (Introduction, Marks & Encoding, Transformations, etc.).
- `intro.md`: The landing page and introduction for the book.
- `myst.yml`: Configuration for MyST and the book's Table of Contents (TOC).
- `pyproject.toml` & `uv.lock`: Python dependency definitions.
- `_build/`: Directory where the generated book is stored (Git ignored).
- `.github/workflows/deploy-book.yml`: CI/CD pipeline for building and deploying the book to GitHub Pages.

## Building and Running

### Development Environment
To set up the local development environment:
```bash
# Install dependencies
uv sync

# Launch Jupyter Lab to edit notebooks
uv run jupyter lab
```

### Building the Book
To generate the static HTML version of the curriculum:
```bash
# Build the HTML site
uv run jupyter-book build --html
```
The output will be located in `_build/html/`.

## Development Conventions
- **Notebook-First:** All curriculum content resides in Jupyter notebooks (`.ipynb`).
- **MyST Configuration:** The structure and metadata of the book are managed via `myst.yml`. If adding a new chapter, ensure it is registered in the `toc` section of `myst.yml`.
- **Dependency Management:** Use `uv` for adding or updating dependencies to ensure reproducible environments.
- **Clean Builds:** Before a final build, it is often useful to clear the cache: `uv run jupyter-book clean .`.
