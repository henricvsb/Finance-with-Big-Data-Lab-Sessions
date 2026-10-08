# Repository Guidelines

## Project Structure & Module Organization

This repository contains Finance with Big Data coursework organized into `#1/` through `#4/`. Each directory holds a `PCLAB#<number> - Group 2 - <authors>.ipynb` notebook and contents supporting PDFs. These PDS's usually contain information about the assignment or additional papers to read for the assignment. Assignment CSVs are stored alongside notebooks in `#1/` and `#4/`. There is no separate source package or test suite.

Keep additions within the relevant lab directory and preserve the existing notebook naming pattern. Quote paths containing `#` or spaces in shell commands.

## Build, Test, and Development Commands

There is no build step or dependency manifest. Use a Python 3 environment with Jupyter and the packages imported by the target notebook.

- `python3 -m venv .venv` creates a local environment.
- `source .venv/bin/activate` activates it on macOS/Linux.
- `python -m pip install jupyterlab pandas numpy matplotlib seaborn scipy plotly statsmodels scikit-learn yfinance` installs common notebook dependencies; Lab 3 needs additional NLP and PyTorch packages.
- `cd "#4"` followed by `jupyter lab` starts Jupyter from a lab directory so relative CSV paths resolve.

Select the intended Python kernel and use **Restart Kernel and Run All Cells** to validate execution.

## Coding Style & Naming Conventions

Use four-space indentation, `snake_case` for functions and variables, and `UPPER_SNAKE_CASE` for configuration constants. Keep imports and configuration near the beginning. Explain task objectives and financial assumptions in Markdown cells. Preserve chronological ordering, explicit return units, and fixed random seeds where sampling is used. No formatter or linter is configured.

**MOST IMPORTANTLY:**. 
Keep your code as simple as possible and follow the Pareto principle. First implement an easy to understand version and then propose some additions to the user. You should follow a "Minimum Viable Product" - first approach.

## Testing Guidelines

No automated test framework or coverage threshold is configured. Run changed notebooks from a fresh kernel and inspect tables, plots, missing values, and existing assertions. Add focused assertions for data invariants when appropriate. Preserve chronological train/test separation to avoid look-ahead bias. Report unavailable datasets, network failures, or skipped expensive cells when full execution is impractical.

## Commit & Pull Request Guidelines

History uses short, informal English and German messages without an enforced convention. Prefer descriptive imperative messages such as `Fix Lab 4 return alignment`. Keep changes focused on one lab or task. In general, always ask before running git add / commit / push. The user can also do this themselves. 

No PR's needed, everything pushed to main directly.

## Data & Configuration

Keep assignment CSVs tracked. Respect `.gitignore`: Lab 3 datasets and caches, virtual environments, notebook checkpoints, and secrets are excluded. Document required external inputs and avoid committing credentials or unrelated generated files.
