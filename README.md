# Project Overview
The Redrob Intelligent Candidate Discovery & Ranking Challenge submission. This project provides a transparent, scalable pipeline to process applicant data, extract meaningful signals, and rank candidates deterministically against job requirements.

# Problem Statement
The recruitment industry faces challenges in efficiently discovering and ranking the right candidates from large applicant pools. Manual screening is time-consuming and prone to human bias, while simplistic keyword matching often overlooks a candidate's true potential and fit for a role. This project aims to address these issues through a structured, unbiased evaluation methodology.

# Solution Overview
Our solution provides an intelligent, deterministic candidate discovery and ranking system. By leveraging structured feature engineering and a transparent weighted scoring methodology, it accurately evaluates candidates without the unpredictability of generative models. The pipeline is designed to be fully reproducible, explainable, and scalable.

# Key Features
- **Deterministic Feature Engineering:** Extract meaningful technical, career, and behavioral signals from candidate profiles using strict rule-based logic.
- **Weighted Scoring System:** Transparent ranking based on multiple configurable dimensions tailored to the job description.
- **Explainable Results:** Clear breakdown of why a candidate received a specific score, ensuring trust and verifiability.
- **Scalable Pipeline:** Efficient processing of large candidate datasets through a logically separated execution environment.

# Repository Structure
```text
india_runs/
├── INDIA_Runs_1.ipynb             # Data understanding and EDA
├── INDIA_Runs_2.ipynb             # Experimentation and ranking engine
├── INDIA_Runs_3.ipynb             # Production pipeline and submission
├── README.md                      # Project overview
├── PROJECT_STRUCTURE.md           # Detailed file and logic breakdown
├── submission_metadata.yaml       # Hackathon submission details
├── requirements.txt               # Dependencies
├── CONTRIBUTING.md                # Contribution guidelines
├── SECURITY.md                    # Security policy
├── CHANGELOG.md                   # Version history
└── LICENSE                        # MIT License
```

# Notebook Overview

The complete pipeline is intentionally separated into three logical stages to allow clear inspection, testing, and sequential execution.

### Notebook 1: `INDIA_Runs_1.ipynb`
- **Purpose:** Data understanding, schema exploration, and initial Exploratory Data Analysis (EDA). This notebook *does not* perform ranking.
- **Inputs:** Raw candidate profile datasets.
- **Outputs:** Cleaned datasets, schema maps, and a foundational understanding of the available features and candidate signals.

### Notebook 2: `INDIA_Runs_2.ipynb`
- **Purpose:** Experimentation and ranking engine development. This is where the core logic is designed and iteratively tested.
- **Inputs:** Cleaned datasets and parsed Job Descriptions.
- **Outputs:** Engineered features, technical/career/behavioral scores, and draft composite ranking scores for candidates.

### Notebook 3: `INDIA_Runs_3.ipynb`
- **Purpose:** Final production pipeline. This notebook applies the tested ranking logic, runs the explainability engine, and generates the final deliverables.
- **Inputs:** Validated ranking engine parameters and the full candidate dataset.
- **Outputs:** The final submission files, diagnostic reports, and deterministic recruiter reasoning.

# Pipeline Overview
1. **Data Understanding (Notebook 1):** Ingest raw data, map schemas, and explore available features.
2. **Engine Development (Notebook 2):** Parse job descriptions and design a deterministic scoring system that extracts hard technical skills, career progression, and behavioral traits.
3. **Validation & Submission (Notebook 3):** Run the complete pipeline over the candidate pool, validate the results against expected outcomes, generate explainable breakdowns, and output the final reports.

# Candidate Evaluation Methodology
The evaluation methodology relies purely on deterministic rules and structured feature engineering. Candidates are scored based on:
- **Technical Scoring:** Exact or partial matches for required tools, languages, and frameworks.
- **Career Scoring:** Evaluation of experience depth, role relevance, and career progression.
- **Behavioral Scoring:** Identification of leadership or collaborative signals explicitly stated in the candidate's background.
These dimensions are combined using a configurable weighted ranking experiment to produce a single composite score.

# Explainability
A core tenant of this project is absolute transparency. The explainability engine provides deterministic recruiter reasoning—a clear, logical breakdown detailing precisely which features contributed to a candidate's final score, avoiding any "black box" decisions.

# Validation
The pipeline includes rigorous validation checks in Notebook 3. These diagnostics ensure that the feature engineering logic performs consistently across edge cases and that the final ranking distribution aligns with deterministic expectations.

# Runtime Constraints
- The solution is optimized to run natively within standard Google Colab environments.
- No GPUs are required, as the deterministic pipeline relies heavily on CPU-bound data processing (Pandas, NumPy).
- It scales efficiently without external API dependencies or rate limits.

# Technologies Used
- **Language:** Python
- **Data Manipulation:** Pandas, NumPy
- **Analysis & Modeling:** scikit-learn (for deterministic utilities, *not* ML ranking)
- **Visualization:** Matplotlib, Seaborn
- **Utilities:** tqdm, pyyaml, openpyxl, python-docx

*(Note: Large Language Models, GPT, Claude, Gemini, or Hosted AI APIs are strictly **NOT** used in this project.)*

# Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/AniruddhaGhosh64/india_runs.git
   cd india_runs
   ```
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

# Running the Project
1. Open the repository in a Jupyter environment or Google Colab.
2. Execute the notebooks in sequential order:
   - Run `INDIA_Runs_1.ipynb` to understand the data.
   - Run `INDIA_Runs_2.ipynb` to observe the feature engineering and ranking engine development.
   - Run `INDIA_Runs_3.ipynb` to execute the production pipeline and generate the final outputs.

# Future Improvements
- Parameterized weighting via a unified configuration file to allow easy adjustments without modifying notebook code.
- Extended unit testing for individual deterministic rules.
- Integration with standard Applicant Tracking Systems (ATS) through exportable API endpoints.

# License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
