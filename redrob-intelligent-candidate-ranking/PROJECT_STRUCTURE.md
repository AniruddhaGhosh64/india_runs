# Project Structure

This document outlines the purpose of every folder and notebook in the repository.

## Directory Layout

### `/notebooks/`
Contains the core logical pipeline of the project, split across three Google Colab notebooks.
- **`01_data_exploration.ipynb`**: Responsible for ingesting raw candidate data, performing exploratory data analysis (EDA), handling missing values, and preparing a clean dataset.
- **`02_candidate_ranking.ipynb`**: The core logic engine. It handles deterministic feature engineering and applies the weighted scoring system to rank candidates based on their suitability.
- **`03_validation_submission.ipynb`**: The final stage. It validates the output distributions, generates transparent explainability metrics for the scores, and produces the final submission files (CSV/Excel).

### `/docs/`
Holds project documentation and architecture visuals.
- **`images/`**: Contains architecture, workflow, and pipeline diagrams (e.g., `architecture.png`, `workflow.png`, `ranking_pipeline.png`).
- **`sample_outputs/`**: Contains screenshots or visual examples of the final outputs for documentation purposes.
- **`presentation.pdf`**: (Placeholder) The final pitch or presentation deck for the hackathon.

### `/sample_data/`
Contains small-scale sample datasets to run the notebooks without needing the full production database.
- **`sample_candidates.jsonl`**: A JSON-lines file containing mock candidate profiles for testing the pipeline.

### `/outputs/`
The destination folder for generated results.
- **`sample_submission.csv`**: The tabular output of ranked candidates.
- **`sample_submission.xlsx`**: The spreadsheet version of the ranked candidates, potentially with formatting and explainability tabs.

### `/assets/`
Resources for UI, README, or presentations.
- **`images/`**: General project images or logos.
- **`icons/`**: Badges or custom icons used in documentation.

## Root Files
- **`README.md`**: The main entry point describing the project, setup, and usage.
- **`PROJECT_STRUCTURE.md`**: This file, explaining the layout.
- **`requirements.txt`**: Python dependencies required to run the notebooks.
- **`submission_metadata.yaml`**: The metadata template required for hackathon submission.
- **`.gitignore`**: Defines files and folders that should not be tracked by Git (e.g., outputs, Colab checkpoints).
- **`LICENSE`**: MIT License details.
- **`CONTRIBUTING.md`**: Guidelines for contributing to the repository.
- **`CODE_OF_CONDUCT.md`**: Community standards for contributors.
- **`SECURITY.md`**: Information on reporting security vulnerabilities.
- **`CHANGELOG.md`**: History of changes and releases.
