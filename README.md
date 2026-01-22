# Mental Health in Technology: An Unsupervised Learning Case Study


A quantitative analysis of the OSMI 2016 Survey, utilizing unsupervised machine learning to identify mental health profile clusters of employees and propose targeted HR interventions to implement the appropriate management strategies by analyzing survey data from over 1,400 technology professionals.

---

## Table of Contents
* [Project Overview](#project-overview)
* [Key Findings](#key-findings)
* [Methodology](#methodology)
* [Repository Structure](#repository-structure)
* [Getting Started](#setup)
* [References](#references)

---

## Project Overview

**Problem Context:**
The intersection of corporate technology environments and mental health has become a focal point for organizational development. This case study moves beyond reactive crisis management to a pre-emptive mitigation program supported by quantitative analysis.

**Proposed Solution:** To categorize employees into distinct personas based on their mental health status, workplace sentiment, and demographic traits, enabling Human Resources to tailor support programs rather than applying a generic approach.

**[Link to the full Case Study report](https://docs.google.com/document/d/13YLSrwZEpFJfEOVDi6Xh5uo-uaAa3xYomTThBuegRhc/edit?usp=sharing)**

---

## Key Findings

The analysis identified three distinct clusters (`k=3`), validated via Stability Analysis (ARI = 0.90) and Hierarchical Clustering. The results suggest that mental health is a spectrum, and management practices, as opposed to medical severity itself, dictate the employee experience.

| Cluster | Persona | Profile Summary                                                                                                                                 | Intervention                                                                                                         |
| :--- | :--- |:------------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------|
| **0** | **Healthy Baseline** | **Low Risk / Disengaged.** (~36% of workforce). Predominantly without disorders, but scores highest for unawareness of benefits.                | **Preventative education:** Shift from crisis response to proactive benefit education during onboarding.             |
| **1** | **Supported Risk** | **High Risk / Positive Experience.** (~32%). High prevalence of disorders, yet reports positive workplace support and mental health management. | **Reinforce safety:** Maintain trust via strict anonymity protocols to prevent regression.                           |
| **2** | **Unsupported Risk** | **High Risk / Negative Experience.** (~32%). High prevalence of disordes, and reports high structural barriers and poor workplace support.      | **Mitigate structural barriers:** Audit administrative workflows to ensure seamless access to support and resources. |

---

## Methodology

This project utilizes a pipeline designed for high-dimensional mixed data:

1.  **Data Preprocessing:**
     * Handling structural missingness (Skip-Logic) via explicit categorization (encoded as `-1`).
     * Exclusion of self-employed respondents to focus on corporate HR strategy.
2.  **Dimensionality Reduction:**
    * **FAMD (Factor Analysis of Mixed Data):** Used to diagnose variance domination caused by employment history features.
    * **t-SNE (Gower Distance):** Used to visualize the local manifold, confirming the continuous spectrum of mental health.
3.  **Clustering:**
    * **K-Prototypes:** The primary algorithm, extending K-Means to handle both numerical and categorical features.
    * **Hierarchical Clustering:** Used for structural validation of the `k=3` solution.

**Tech Stack:** `Python 3.11`, `pandas`, `scikit-learn`, `kmodes`, `prince` (FAMD), `gower`, `seaborn`, `missingno`.

---

## Repository Structure

```text
├── data/
│   ├── raw/                 # Original OSMI 2016 dataset (Not included in repo, see Setup)
│   └── processed/           # Cleaned and encoded dataframes and cluster profiles (Run mental-health-tech.ipynb)
├── notebooks/
│   ├── mental-health-tech.ipynb  # Primary analysis (ETL, Preprocessing, and Clustering pipeline)
│   └── figures.ipynb             # Generation of interpretable visualizations for the report
├── reports/
│   └── figures/             # Exported PNGs used in the report (Run figures.ipynb)
├── environment.yml          # Conda environment configuration
├── README.md 
└── .gitignore
```

## Setup

### 1. Prerequisites
This project requires **Conda** (Anaconda) to manage mixed dependencies (pip + conda).

### 2. Clone Repository
```bash
git clone [https://github.com/mardelpozo/mental-health-tech.git](https://github.com/mardelpozo/mental-health-tech.git)
cd mental-health-tech
```

### 3. Environment
```bash
conda env create -f environment.yml
conda activate mental-health-tech
```

### 4. Dataset Download
Due to licensing and file size, the raw dataset is not hosted directly in this repository.

1.  Navigate to the [OSMI Mental Health in Tech Survey 2016 on Kaggle](https://www.kaggle.com/datasets/osmi/mental-health-in-tech-2016).
2.  Download the file `mental-heath-in-tech-2016_20161114.csv`.
3.  Place the downloaded file in the `data/raw/` directory.

*Note: The notebooks are configured to look for the data in this specific relative path.*

### 5. Running the Analysis
```bash
jupyter lab
```
- Pipeline (`notebooks/mental-health-tech.ipynb`): Contains the complete end-to-end workflow, including data cleaning, feature engineering, clustering, and validation metrics.
- Visualizations (`notebooks/figures.ipynb`): Generates the interpretable visualizations (FAMD projections, t-SNE plots, radar Charts) used in the final report.

## References

For a complete list of references, please consult the **Bibliography** section of the corresponding case study report.

This project was conducted as part of the **Machine Learning: Unsupervised Learning and Feature Engineering** course at IU International University of Applied Sciences.

---
*Author: [Mariana Del Pozo Patrón](https://github.com/mardelpozo)*