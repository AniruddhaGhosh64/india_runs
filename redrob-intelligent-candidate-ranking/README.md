# Redrob Intelligent Candidate Discovery & Ranking Challenge

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Status](https://img.shields.io/badge/Status-Hackathon_Ready-success)

## Problem Statement
The recruitment industry faces challenges in efficiently discovering and ranking the right candidates from large applicant pools. Manual screening is time-consuming and prone to human bias, while simplistic keyword matching often overlooks a candidate's true potential and fit for a role.

## Solution Overview
Our solution provides an intelligent, deterministic candidate discovery and ranking system. By leveraging structured feature engineering and a transparent weighted scoring methodology, it accurately evaluates candidates against job requirements without the unpredictability of generative models.

## Key Features
- **Deterministic Feature Engineering:** Extract meaningful signals from candidate profiles.
- **Weighted Scoring System:** Transparent ranking based on multiple configurable dimensions.
- **Explainable Results:** Clear breakdown of why a candidate received a specific score.
- **Scalable Pipeline:** Efficient processing of large candidate datasets.

## Repository Structure
```
redrob-intelligent-candidate-ranking/
│
├── notebooks/                     # Core logic and pipeline steps
├── docs/                          # Documentation and architecture diagrams
├── sample_data/                   # Sample inputs for testing
├── outputs/                       # Generated rankings and reports
├── assets/                        # Icons and imagery
├── requirements.txt               # Dependencies
├── submission_metadata.yaml       # Hackathon submission details
└── README.md                      # Project overview
```

## Pipeline Overview
The pipeline consists of three main stages, executed sequentially via Google Colab notebooks:
1. **Data Exploration & Preprocessing:** Cleaning and structuring raw candidate data.
2. **Feature Engineering & Ranking:** Applying scoring algorithms based on predefined weights.
3. **Validation & Submission:** Verifying results, generating explanations, and formatting outputs.

## Architecture Overview
![Architecture Overview](docs/images/architecture.png)
*(Placeholder for Architecture Diagram)*

![Workflow Overview](docs/images/workflow.png)
*(Placeholder for Workflow Diagram)*

![Ranking Pipeline](docs/images/ranking_pipeline.png)
*(Placeholder for Ranking Pipeline Diagram)*

## Notebook Descriptions

### Notebook 1: `01_data_exploration.ipynb`
- **Purpose:** Analyze and clean the raw candidate dataset.
- **What it does:** Performs exploratory data analysis (EDA), handles missing values, and normalizes fields to prepare the data for downstream processing.
- **Outputs:** Cleaned structured data ready for feature extraction.

### Notebook 2: `02_candidate_ranking.ipynb`
- **Purpose:** Execute feature engineering and rank candidates.
- **Feature Engineering:** Extracts key attributes such as experience, skills alignment, and education level.
- **Ranking:** Applies a deterministic weighted scoring model to compute a final suitability score for each candidate.
- **Outputs:** Scored and ranked list of candidates.

### Notebook 3: `03_validation_submission.ipynb`
- **Purpose:** Validate rankings, generate explainability metrics, and format final deliverables.
- **Validation:** Checks for logical consistency and handles edge cases.
- **Explainability:** Generates a clear breakdown of individual scores to ensure transparency.
- **Submission:** Formats the final ranked lists into CSV and Excel files.
- **Outputs:** `sample_submission.csv` and `sample_submission.xlsx`.

## Technologies Used
- **Language:** Python
- **Data Processing:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Utilities:** tqdm, scikit-learn
- **Document Handling:** python-docx, openpyxl, pyyaml
- **Environment:** Google Colab / Jupyter

## Feature Engineering Summary
We derive features from candidate profiles by quantifying aspects such as years of experience, skill match percentage, and educational relevance. These features form the foundation of our deterministic model.

## Candidate Ranking Methodology
The ranking is based on a transparent weighted scoring equation. Each extracted feature is assigned a specific weight depending on its importance to the role, and the total sum dictates the candidate's final rank. No generative AI or black-box LLMs are used, ensuring 100% deterministic and reproducible results.

## Explainability Engine
Every ranked candidate comes with a detailed score breakdown, showing exactly how many points were awarded for experience, skills, and other criteria. This ensures recruiters can trust and verify the system's recommendations.

## Validation Strategy
The output is validated through statistical checks on score distributions and manual spot-checking of edge cases to ensure the scoring logic applies fairly across all candidate profiles.

## Runtime & Compute Constraints
- Optimized to run efficiently on standard Google Colab instances (CPU/Standard RAM).
- No GPU acceleration is required.
- Memory usage is minimized through chunked processing where necessary.

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/AniruddhaGhosh64/india_runs.git
   cd india_runs
   ```
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Running the Project
1. Open the notebooks in Google Colab or a local Jupyter environment.
2. Execute them in order:
   - `01_data_exploration.ipynb`
   - `02_candidate_ranking.ipynb`
   - `03_validation_submission.ipynb`

## Sample Outputs
*Screenshots of the outputs will be added below.*
![Sample Output](docs/sample_outputs/sample_output.png)
*(Placeholder for sample outputs)*

## Future Improvements
- Dynamic weight adjustment via a simple UI.
- Support for processing PDF resumes natively.
- Integration with standard ATS (Applicant Tracking Systems) APIs.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
