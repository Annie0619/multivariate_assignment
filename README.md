# Multivariate Techniques for Leaf Species Classification

### Author: Andomei Smit

### Date: April 2025

---

## Overview

This project explores the application of multivariate dimension reduction techniques combined with clustering and classification algorithms for the task of leaf species identification. The primary aim is to evaluate whether dimension reduction improves classification performance compared to prior methods, specifically those introduced by Mallah et al. (2013). The techniques examined include Principal Component Analysis (PCA), Isometric Mapping (Isomap), and Locally Linear Embedding (LLE), followed by clustering using the K-Means algorithm. The Hungarian algorithm is used to align cluster assignments to true species labels for accuracy evaluation.

---

## Repository Structure

| File/Folder                              | Description                                                   |
| ---------------------------------------- | ------------------------------------------------------------- |
| `Initial Data Cleaning.rmd` | R Markdown script to remove species with incomplete features |
| `PCA and ISOMAP Dimension Reduction.rmd` | R Markdown script for PCA and Isomap preprocessing and tuning |
| `LLE_Dimension_Deduction.ipynb`          | Python notebook for LLE dimension reduction [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Annie0619/multivariate_assignment/blob/main/LLE_Dimension_Reduction.ipynb) |                                                
| `Applying K-means.rmd`                                         | R Markdown script applying K-means clustering and evaluating performance                 |
| `Final Report.pdf`                   | Final academic write-up summarizing methods and findings                                 |
| `created_data/`                                                | Folder containing intermediate and final datasets (e.g., reduced-dimensional embeddings) |
| `plots/`                                                       | Folder containing figures generated during analysis                                      |
| `data/`                                                       | Folder containing original extracted features from Mallah et al. (2013)                                      |
| `results/`                                                       | Folder containing the results after applying K-Means to the various reduced dimension data sets.                                     |
| `presentation/`                                                       | Folder containing the slides used for the presentation of the progress of the project                                 |
| `previous_work/`                                                       | Folder containing a brief proposal of three initial topics that were considered for this project                                    |

---

## How to Run the Code
To created the Analysis Ready Dataset (`ard1.csv`), run the `Initial Data Cleaning.Rmd` file. This will remove the two species with incomplete feature sets and write a `.csv` file to the `created_data` folder.

### R Scripts:

To reproduce the PCA, Isomap, and K-means clustering steps:

1. Open the `.Rmd` files in RStudio
2. Click `Knit` or run the code chunks sequentially

Required scripts (in order):

- `PCA and Isomap dimension reduction.rmd`
- `Applying K-means.rmd`

### Python Script (Google Colab):

To run the LLE dimension reduction in Python:

1. Open the notebook
[`lle_dimension_reduction.ipynb`](https://colab.research.google.com/github/Annie0619/multivariate_assignment/blob/main/LLE_Dimension_Reduction.ipynb)
2. Click `Runtime > Run all` to execute all cells

This will generate reduced embeddings using LLE and export them for use in clustering.

---

## Methods Used

- **Principal Component Analysis (PCA)** using the correlation matrix
- **Isometric Mapping (Isomap)** with geodesic distance and MDS
- **Locally Linear Embedding (LLE)** using neighborhood reconstruction and low-dimensional mapping
- **K-Means Clustering** to group reduced embeddings into species clusters
- **Hungarian Algorithm** to optimally align cluster labels to species labels
- **Evaluation** using accuracy, per-species accuracy, silhouette scores, and runtime

---

## Dataset

- Original dataset: 1600 binary and grayscale images of leaves
- Source: Royal Botanic Gardens, Kew (UK), as used in Mallah et al. (2013)
- After cleaning: 1568 images across 98 species (each with 16 samples)
- Features: 192 continuous values per sample (64 each from shape, margin, and texture)

---

## R Package Dependencies

```r
library(dplyr)
library(tidyr)
library(xtable)
library(splitstackshape)
library(FactoMineR)
library(ggplot2)
library(factoextra)
library(lattice)
library(permute)
library(vegan)
library(cluster)
library(RDRToolbox)
library(FNN)
library(e1071)
library(patchwork)
library(clue)
library(kernlab)
library(parallel)
```

Note: `Sys.setenv(RGL_USE_NULL = TRUE)` is required to install `RDRToolbox`.

Python dependencies for Colab are handled within the notebook.

---

## References

- Mallah, C., Coquin, D., & Tougne, L. (2013). *Plant Leaf Classification Using Probabilistic Integration of Shape, Texture and Margin Features*.
- Beck, H. E. et al. (2020), Malik et al. (2022), Tariku et al. (2023), Christenhusz et al. (2016) — see final write-up for full citations.

For full details on methodology and results, see the final report: [`View Final Report.pdf`](https://github.com/Annie0619/multivariate_assignment/blob/main/Final%20Report.pdf)

---




