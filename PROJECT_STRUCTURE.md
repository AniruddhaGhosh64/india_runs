# Project Structure

This document details the organization of the repository and the purpose behind the intentional separation of logic across our primary notebooks.

## Repository Root

The root of the repository contains all the executable notebooks alongside essential configuration and documentation files. 

### Core Notebooks

The pipeline is split into three Google Colab notebooks. This separation exists to isolate data exploration from core logic development, and logic development from final production execution.

- **`INDIA_Runs_1.ipynb`**  
  **Data Understanding & Exploration**
  - Handles dataset loading and schema mapping.
  - Performs Exploratory Data Analysis (EDA) on the candidate pool.
  - Explores early feature signals to prepare for downstream processing.
  - *(Note: This notebook does not contain or execute any ranking logic.)*

- **`INDIA_Runs_2.ipynb`**  
  **Experimentation & Ranking Engine Development**
  - Serves as the core logic playground.
  - Parses Job Descriptions to establish a baseline for evaluation.
  - Implements the feature engineering, driving the extraction of Technical, Career, and Behavioral signals.
  - Tests various weighted ranking experiments to synthesize a final composite score.
  - Does NOT rely on machine learning or LLMs; everything is driven by explicit rules and structured queries.

- **`INDIA_Runs_3.ipynb`**  
  **Final Production Pipeline**
  - Applies the hardened ranking engine from Notebook 2 across the full dataset.
  - Runs validation checks and feature diagnostics to ensure deterministic logic holds up across edge cases.
  - Powers the explainability engine, generating deterministic recruiter reasoning for why a candidate received their score.
  - Produces the final submission outputs (e.g., CSV and Excel reports).

### Configuration & Documentation

- **`README.md`**: The main entry point describing the problem, methodology, and setup instructions.
- **`PROJECT_STRUCTURE.md`**: This file, outlining the repository's logical design.
- **`requirements.txt`**: The strictly necessary Python dependencies required to run the deterministic pipeline (Pandas, NumPy, Matplotlib, etc.).
- **`submission_metadata.yaml`**: The metadata template required for hackathon submission containing details about the team, constraints, and approach.

### Standards & Policies

- **`LICENSE`**: MIT License ensuring open-source usability.
- **`CONTRIBUTING.md`**: Guidelines for opening issues, requesting features, and submitting pull requests.
- **`CODE_OF_CONDUCT.md`**: Community standards to ensure a healthy and welcoming environment for contributors.
- **`SECURITY.md`**: Policy for reporting vulnerabilities privately.
- **`CHANGELOG.md`**: History of changes and milestones.
