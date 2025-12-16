# Car Recall Clustering: Severity-Based Analysis of U.S. Vehicle Recalls

This project analyzes nearly six decades of U.S. vehicle recall data and applies unsupervised learning to cluster recalls by severity.  
Rather than focusing on recall frequency alone, the analysis groups recalls based on the **number of potentially affected vehicles**, temporal patterns, and manufacturer characteristics to uncover structural differences in recall severity.

This repository contains the **clustering pipeline, which I led as part of a team project.


## Abstract
Vehicle recalls are a critical indicator of automotive safety risk, yet severity is often discussed only in aggregate counts.  
This project uses K-Means clustering to identify **low-, medium-, and high-severity recall groups** based on recall scale, year, and manufacturer. By clustering recalls rather than pre-labeling severity, the analysis reveals meaningful patterns across manufacturers, defect categories, and time that are not visible through descriptive statistics alone.


## Problem
- Recall datasets are large, noisy, and highly skewed, making severity difficult to assess directly.
- Raw recall counts obscure structural risk patterns, especially across manufacturers with different production scales.
- Existing analyses rarely apply unsupervised learning to understand recall severity at scale.


## Approach
The analysis follows a structured clustering pipeline:

- Cleaned and filtered recall records to vehicle-related recalls.
- Selected severity-driven features, including log-transformed recall size, recall year, and manufacturer.
- Standardized numeric variables and one-hot encoded categorical features.
- Applied K-Means clustering, selecting the number of clusters using Elbow and Silhouette criteria on fixed random samples.
- Ranked clusters by median recall size and mapped them to ordered severity levels (low, medium, high).
- Evaluated clustering quality using Silhouette, Calinski–Harabasz, and Davies–Bouldin metrics.
- Analyzed severity patterns across time, manufacturers, and defect components.


## Key Findings
- A **three-cluster solution (k = 3)** consistently emerged as optimal, representing low, medium, and high recall severity.
- High-severity recalls disproportionately involve safety-critical components such as **electrical systems, fuel systems, and airbags**.
- Large manufacturers (e.g., GM, Ford, Chrysler) dominate absolute recall counts, but **smaller manufacturers exhibit higher proportional rates of severe recalls**.
- Temporal analysis shows a rise in high-severity recalls beginning in the 1990s, aligning with increasing vehicle complexity and regulatory changes.

---

## Code
The analysis is organized into three notebooks to emphasize clarity and reproducibility:

- `01_eda.ipynb`: Data loading, cleaning, exploratory analysis, and preparation of clustering inputs.
- `02_clustering.ipynb`: Feature engineering, K selection, K-Means clustering, and severity labeling.  
  *(Clustering design and implementation led by me.)*
- `03_evaluation.ipynb`: Internal validation metrics and interpretation of cluster structure.

Intermediate artifacts are generated automatically to support reproducibility.



## Tools and Libraries
- Python
- pandas, numpy
- scikit-learn (K-Means, clustering validation metrics)
- matplotlib, seaborn


## Contribution
- Led the **clustering design and implementation**, including feature selection, normalization strategy, K selection, and severity mapping.
- Implemented the full K-Means pipeline and internal evaluation metrics.
- Contributed to the interpretation of manufacturer- and component-level severity patterns.
- Collaborated on overall analysis design and final report preparation.


## Report
📄 [View full project report](reports/final_report.pdf)
