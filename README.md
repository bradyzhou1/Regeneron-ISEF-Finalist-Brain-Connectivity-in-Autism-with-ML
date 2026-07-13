<p align="center">
  <img src="pipeline.png" width="900">
</p>

<p align="center">
</p>

# Brain Connectivity in Autism Using Machine Learning
### Regeneron ISEF Finalist • Georgia Science & Engineering Fair Grand Award Winner

This repository contains the complete code, analysis workflow, and supporting materials for my research project investigating whether functional brain connectivity patterns measured by resting-state fMRI can distinguish individuals with Autism Spectrum Disorder (ASD) from neurotypical controls using machine learning.

The project was selected as a **Regeneron International Science and Engineering Fair (ISEF) Finalist** after qualifying through the Georgia Science and Engineering Fair (GSEF).

---

## Project Overview

Autism Spectrum Disorder is a complex neurodevelopmental condition with highly variable behavioral presentations. While diagnosis is currently based primarily on behavioral assessment, advances in neuroimaging have raised the question of whether patterns of functional brain connectivity can provide additional biological insights.

This project investigates whether resting-state functional MRI (rs-fMRI) connectivity features can be used to identify autism-related brain network patterns while carefully evaluating one of the largest challenges in multi-site neuroimaging studies: **site effects**.

Rather than simply maximizing prediction accuracy, this research focuses on understanding:

- Can functional connectivity distinguish ASD from neurotypical controls?
- How much do acquisition site differences influence machine learning performance?
- Which brain networks contribute most consistently across independent validation folds?

---

# Dataset

This study uses publicly available data from the **ABIDE I and ABIDE II** consortium.

Dataset characteristics:

- 679 participants
- 319 Autism Spectrum Disorder
- 360 Neurotypical controls
- Male participants
- Ages 5–30 years
- 24 imaging sites
- CC200 functional atlas
- Preprocessed using the C-PAC pipeline

Because the original MRI data are publicly available through ABIDE, this repository does **not** redistribute the imaging dataset.

---

# Methodology

The analysis pipeline consists of:

1. Download and preprocess ABIDE data
2. Extract ROI time series
3. Compute functional connectivity matrices
4. Fisher z-transformation
5. Feature extraction (19,900 connectivity edges)
6. Dimensionality reduction
7. Machine learning classification
8. Leave-One-Site-Out (LOSO) validation
9. Random train/test validation
10. Permutation testing
11. Network interpretation

---

# Machine Learning Models

The primary model is Logistic Regression with L2 regularization.

Additional analyses include:

- PCA dimensionality reduction
- UMAP visualization
- Permutation significance testing
- Site-balanced validation
- Brain network interpretation using the Yeo 7-network atlas

---

# Key Results

### Leave-One-Site-Out Validation

| Metric | Value |
|---------|-------|
| Accuracy | 0.700 |
| Balanced Accuracy | 0.674 |
| AUC | 0.738 |
| Sensitivity | 0.665 |
| Specificity | 0.683 |

### Random Train/Test Validation

Average Accuracy:

**0.685 ± 0.035**

Permutation testing demonstrated performance significantly above chance (p < 0.001).

---

# Major Findings

This project demonstrates that:

- Functional connectivity contains reproducible autism-related information.
- Site effects remain substantially larger than diagnostic effects in multi-site MRI studies.
- Certain interactions involving Limbic, Default Mode, and Attention networks consistently contribute across validation folds.
- Careful validation is essential to avoid overestimating machine learning performance.

---

# Repository Contents

```
2026 Cobb Paulding Regional Fair.ipynb
    Initial regional science fair analysis

2026 GSEF Science Fair.ipynb
    Improved pipeline submitted to GSEF

2026 Regeneron ISEF.ipynb
    Final analysis used for ISEF

download_abide_preproc.py
    Script for downloading ABIDE preprocessed data

MRI_ROI200_example.csv
    Example ROI time series from one participant

scorr05_2level_all.nii.gz
    MNI template used for connectivity visualization
```

---

# Reproducibility

The repository includes:

- Complete analysis notebooks
- Data preprocessing workflow
- Machine learning pipeline
- Statistical evaluation
- Example input data

Due to the size of the ABIDE dataset, users should download the original data directly from the ABIDE repository before reproducing the analyses.

---

# Awards

🏅 Regeneron International Science and Engineering Fair (ISEF) Finalist

🏅 Georgia Science & Engineering Fair (GSEF) REGENERON ISEF AWARD (TOP 4)

🏅 GSEF TOP TEN GRAND AWARD 

🏅 GSEF Best in Category - COMPUTATIONAL BIOLOGY & BIOINFORMATICS

🏅 Citadel Securities Innovation Prize for exceptional data analysis techniques

🏅 Cobb-Paulding Regional Science Fair First Place Winner

---

# Motivation

This research was inspired by my younger brother, who is autistic.

While the project focuses on computational neuroscience and machine learning rather than clinical diagnosis, it represents my effort to better understand autism through data science and to explore how machine learning can contribute to neuroscience research.

---

# Future Work

Potential future directions include:

- Graph Neural Networks
- Domain adaptation to reduce site effects
- Harmonization techniques (e.g., ComBat)
- Explainable AI for brain connectivity
- Larger multi-cohort validation studies

---

# Citation

If you use this repository, please cite:

Brady Zhou.
**Brain Connectivity in Autism Using Machine Learning.**
Regeneron International Science and Engineering Fair (ISEF), 2026.

---

# Disclaimer

This repository is intended for research and educational purposes only.

The models presented here are **not designed for clinical diagnosis** and should not be used for medical decision making.
