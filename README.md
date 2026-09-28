# Replication Package: On the Use of Machine Learning for Code Review Automation: A Systematic Literature Review

This repository contains the full replication package and supplementary material for the systematic literature review (SLR) titled:

> **"On the Use of Machine Learning for Code Review Automation: A Systematic Literature Review"**

This package provides the complete dataset of **166 primary studies** spanning over a decade (2014–2025), comprehensive screening and quality assessment logs, interactive visual artifacts, the paper appendix, and computational Jupyter notebooks used to derive the taxonomies, statistical distributions, and empirical findings reported in the manuscript.

---

## 📂 Repository Structure

The repository is organized into four main directories alongside the supplementary appendix:

```text
replication_package/
├── paper_appendix.pdf                  # Supplementary Appendix (Primary Studies Table & QA Details)
├── data/                               # Raw and processed datasets, screening logs, QA scores, queries
│   ├── data_extraction.xlsx            # Full data extraction spreadsheet for all 166 primary studies
│   ├── parsed_extracted_data.jsonl     # Structured, machine-readable dataset in JSON Lines format
│   ├── queries.docx                    # Search strings and boolean queries executed across digital libraries
│   ├── Full_text_screening_excluded_papers.xlsx # Full-text screening exclusions with detailed rationales
│   ├── quality assessment.xlsx         # Quality assessment scoring sheet across all evaluated studies
│   └── quality_assessment_rejected_papers.csv   # Papers excluded during the quality assessment phase (< 80%)
├── notebooks/                          # Jupyter notebooks for data parsing and research question analyses
│   ├── parse_data.ipynb                # Pipeline converting raw extraction sheets to JSONL format
│   ├── data_overview.ipynb             # Macroscopic trends, venue, publication, and demographic distributions
│   ├── RQ1.ipynb                       # RQ1: Addressed Code Review Tasks & Taxonomy Analysis
│   ├── RQ2.ipynb                       # RQ2: Data Characteristics, Input Modalities & Availability
│   ├── RQ3.ipynb                       # RQ3: Machine Learning Techniques & Adaptation Paradigms
│   └── RQ4.ipynb                       # RQ4: Evaluation Rigor, Validation Designs & Metrics
└── figures/                            # Interactive HTML visualizations and demographic charts
    ├── sankey_inputs_tasks.html        # Interactive Sankey diagram: Input Modalities -> Review Tasks
    ├── sankey_task_category_training.html # Interactive Sankey diagram: Task Categories -> ML Paradigms
    ├── Sankey_metrics.html             # Interactive Sankey diagram: Tasks -> Evaluation Paradigms -> Metrics
    ├── top_affiliations.png            # Author affiliation distribution
    └── top_countries.png               # Geographical distribution of primary studies
```

---

## 📄 Supplementary Appendix (`paper_appendix.pdf`)

The accompanying document **`paper_appendix.pdf`** provides extended supplementary material to complement the main manuscript:

*   **Primary Studies Catalogue (Table A.1):** A comprehensive reference table detailing all 166 primary studies included in the review, listing their publication year, publication venue and type, target code review task category (RQ1), input artifact types (RQ2), machine learning family and adaptation strategy (RQ3), evaluation paradigms and metrics (RQ4), and artifact/dataset availability links.
*   **Quality Assessment Framework (Table A.2):** Detailed description of the 8 formal quality assessment questions, scoring rubric (Yes = 1, Partially = 0.5, No = 0), and individual quality assessment scores for all candidate studies.

---

## 📊 Data Artifacts (`data/`)

*   **`data_extraction.xlsx`**: The primary extraction spreadsheet containing all qualitative and quantitative data extracted across all dimensions (tasks, input modalities, ML models, evaluation methods, replication packages, baseline usage, data splits, and reported challenges).
*   **`parsed_extracted_data.jsonl`**: The cleaned, normalized, and machine-readable JSON Lines version of the extraction dataset used directly as the input source for all computational analysis notebooks.
*   **`queries.docx`**: The exact search strings, boolean search clauses, and field constraints tailored for each electronic digital library (ACM Digital Library, IEEE Xplore, Scopus, SpringerLink, and arXiv).
*   **`Full_text_screening_excluded_papers.xlsx`**: Log of candidate papers excluded during the full-text screening phase, including paper metadata and specific exclusion criteria applied.
*   **`quality assessment.xlsx`**: Detailed scores for each paper across all 8 quality criteria items, showing category totals and final percentage scores.
*   **`quality_assessment_rejected_papers.csv`**: List of candidate papers that scored below the 80% quality assessment threshold and were subsequently excluded from the primary study corpus.

---

## 📓 Analysis Notebooks (`notebooks/`)

All analytical computations and figures are reproducible via the Jupyter notebooks located in `notebooks/`:

| Notebook | Focus / Research Question | Description & Key Analyses |
| :--- | :--- | :--- |
| `parse_data.ipynb` | **Data Pipeline** | Ingests `data_extraction.xlsx`, normalizes multi-value fields, validates schema integrity, and exports `parsed_extracted_data.jsonl`. |
| `data_overview.ipynb` | **Corpus Overview** | Computes publication timelines (2014–2025), venue distributions (conferences vs. journals vs. preprints), and demographic distributions. |
| `RQ1.ipynb` | **RQ1: CR Tasks** | Analyzes the 4-phase code review task taxonomy (pre-review, review assistance, generative, post-review), task frequencies, and temporal evolution. |
| `RQ2.ipynb` | **RQ2: Data Characteristics** | Analyzes input artifact modalities (diffs, ASTs, metadata, dialogue), dataset availability trends, public benchmark dominance, and programming language distributions. |
| `RQ3.ipynb` | **RQ3: ML Techniques** | Maps machine learning paradigms (Classical ML, DL, PLMs, Decoder-only LLMs), model architectures, training vs. prompting strategies, and task-model pairings. |
| `RQ4.ipynb` | **RQ4: Evaluation Rigor** | Analyzes validation designs (cross-project, temporal, random splits), baseline configurations, metric categories (lexical, semantic, ranking, classification), and statistical testing practices. |

---

## 🌐 Interactive Visualizations (`figures/`)

The `figures/` folder contains interactive Plotly/Sankey HTML visualizations that allow users to dynamically explore multi-dimensional relationships in the corpus:

*   **`sankey_inputs_tasks.html`**: Explore flows from input artifact modalities to specific code review tasks.
*   **`sankey_task_category_training.html`**: Explore mappings between task categories and ML training/adaptation paradigms (supervised, fine-tuning, prompting, zero-shot).
*   **`Sankey_metrics.html`**: Explore connections across code review tasks, evaluative paradigms (offline, human study, LLM-as-a-judge), and metric categories.

---

## 🚀 Reproduction Guidelines

All figures, statistical counts, and tables presented in the paper can be inspected directly within the pre-executed notebook outputs or recomputed from scratch.

### 1. Environment Setup

Ensure you have Python 3.9+ installed. Install the required dependencies:

```bash
pip install pandas numpy matplotlib seaborn plotly jupyter openpyxl
```

### 2. Execution Order

1. Clone or extract this replication package.
2. Open a terminal and navigate to the `notebooks/` directory:
   ```bash
   cd notebooks
   jupyter notebook
   ```
3. To regenerate the structured data from raw extraction sheets, execute `parse_data.ipynb`.
4. Run any of the analytical notebooks (`data_overview.ipynb`, `RQ1.ipynb`, `RQ2.ipynb`, `RQ3.ipynb`, `RQ4.ipynb`) to reproduce figures, tables, and statistics.

---

## 📜 License & Citation

This replication package is released under the **MIT License**.

If you find this replication package, dataset, or the SLR findings useful in your research, please cite our paper:

```bibtex
TODO
```


