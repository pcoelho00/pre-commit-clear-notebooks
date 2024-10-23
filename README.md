# Jupyter Notebook Output Clearer

A pre-commit hook that automatically clears output cells from Jupyter notebooks before committing. This helps maintain clean version control history by preventing unnecessary diffs from notebook outputs and execution counts.

## Features

- 🧹 Automatically clears all output cells from Jupyter notebooks
- 🎯 Only processes staged `.ipynb` files
- 🚫 Skips `.ipynb_checkpoints` directories
- ♻️ Re-stages modified notebooks automatically
- ⚡ Fast processing using `jq` for JSON manipulation

## Prerequisites

- Python 3.9 or higher
- `pre-commit` package installed (`pip install pre-commit`)
- `jq` command-line JSON processor:
  ```bash
  # Ubuntu/Debian
  sudo apt-get install jq
  ```

## Installation

### Option 1: Using pre-commit config

1. Add this to your `.pre-commit-config.yaml`:
  ```yaml
  repos:
    - repo: https://github.com/pcoelho00/pre-commit-clear-notebooks
      rev: v1.0.0
      hooks:
        - id: clear-notebooks
  ```

2. Install the pre-commit hook:
  ```bash
  pre-commit install
  ```

### Option 2: Pulling from github

1. Clone the repository:
  ```bash
   git clone https://github.com/pcoelho00/pre-commit-clear-notebooks
  ```

## Usage

Once installed, the hook runs automatically when you try to commit files:

```bash
git add notebook.ipynb
git commit -m "Update notebook"
```

To skip the hook for a particular commit:
```bash
git commit --no-verify -m "Keep notebook outputs"
```

## Manual Usage

You can also use the script directly to clear notebook outputs:

```bash
# Clear a single notebook
./scripts/clear-notebooks notebook.ipynb

# Clear all notebooks in a directory
./scripts/clear-notebooks /path/to/notebooks/
```

## License

MIT License - feel free to use and modify as needed.
