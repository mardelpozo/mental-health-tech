# Mental Health in the Tech Workplace: A Data Science Case Study

![Python](https://img.shields.io/badge/Python-3.11-blue) ![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange) ![Status](https://img.shields.io/badge/Status-Completed-green)

A quantitative analysis of the 2016 OSMI Mental Health in Tech Survey, utilizing unsupervised machine learning to identify employee risk profiles and propose targeted HR interventions.

**Repository:** [https://github.com/mardelpozo/mental-health-tech](https://github.com/mardelpozo/mental-health-tech)

## 📌 Project Overview

Mental health in the technology sector is a critical challenge, characterized by high burnout rates and varying levels of workplace support. This case study applies advanced data science techniques to survey data from over 1,400 technology professionals.

**The Goal:** To categorize employees into distinct "Personas" based on their mental health status, workplace sentiment, and demographic traits, enabling Human Resources to move from generic support models to targeted, data-driven interventions.

## 🛠️ Key Technologies & Methodology

This project focuses on **Mixed-Type Data Analysis** (handling both numerical and categorical survey responses).

* **Data Cleaning:** Handling structural missingness (skip-logic in survey design) and statistical imputation.
* **Feature Selection:** Mutual Information scores and Cramer's V for categorical redundancy analysis.
* **Dimensionality Reduction:** * **FAMD** (Factor Analysis of Mixed Data) to visualize variance structure.
    * **t-SNE** (using Gower Distance) to visualize the respondent manifold.
* **Clustering:** **K-Prototypes** algorithm (an extension of K-Means for mixed data) to partition the workforce.
* **Profiling:** Radar charts and statistical mode analysis to generate business personas.

## 📂 Project Structure

```text
├── data/
│   ├── raw/                 # Original OSMI 2016 dataset
│   └── processed/           # Cleaned, encoded, and clustered dataframes
├── notebooks/
│   ├── mental-health-tech.ipynb  # Main analysis (EDA, Preprocessing, Modeling)
│   └── figures.ipynb             # Generation of publication-ready visualizations
├── reports/
│   ├── figures/             # Exported PNGs for the Case Study document
│   └── Task_CaseStudy.pdf   # Final Case Study Report
├── README.md                # Project documentation
└── environment.yml         # Python dependencies
```

## 📊 Key Findings (The Personas)

The analysis identified three distinct clusters of employees (**k=3**), validated via Stability Analysis (ARI = 0.90).

| Cluster | Persona Name | Characteristics | HR Recommendation |
| :--- | :--- | :--- | :--- |
| **0** | **The Healthy Unaware** | No current disorders, but **low awareness** of benefits. High "Unknown" responses. | **Preventative Literacy:** Focus on education before crisis occurs. |
| **1** | **The Vulnerable Uncertain** | "Maybe" responses to clinical questions. High uncertainty about safety/anonymity. | **De-stigmatization:** Campaigns explicitly clarifying anonymity protocols. |
| **2** | **The Critically Affected** | Diagnosed, high benefit awareness, but **high difficulty** taking leave. | **Structural Reform:** Simplify leave processes and reduce administrative friction. |

## 🚀 Getting Started

### Prerequisites
* Python 3.8+
* Jupyter Notebook or JupyterLab

### Installation
1.  Clone the repo:
    ```bash
    git clone [https://github.com/mardelpozo/mental-health-tech.git](https://github.com/mardelpozo/mental-health-tech.git)
    cd mental-health-tech
    ```

2.  Create the environment:
    ```bash
    conda env create -f environment.yml
    conda activate mental-health-tech
    ```

3.  Run the analysis:
    * Open `notebooks/mental-health-tech.ipynb` to see the full modeling pipeline.
    * Open `notebooks/figures.ipynb` to generate the report visualizations.

## 📈 Visualizations

*See `reports/figures/` for the complete gallery.*

* **Manifold Structure:** t-SNE projection showing the continuous spectrum of mental health.
* **Cluster DNA:** Radar charts highlighting the gap between benefit awareness and structural friction for affected employees.

## 📜 License

This project utilizes data from the Open Sourcing Mental Illness (OSMI) research institute. Code is provided for educational and portfolio purposes.

---
*Author: [Mariana Del Pozo Patron](https://github.com/mardelpozo)*