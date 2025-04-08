# README
# Acute Myeloid Leukemia (AML) RNA-seq Analysis

This repository contains an R-based analysis pipeline for visualizing gene expression patterns in Acute Myeloid Leukemia (AML) samples using RNA sequencing data. The analysis focuses on identifying and visualizing differentially expressed genes across various AML mutations and treatments.

## Overview

This analysis uses RNA-seq data from 19 AML model mice samples 
, examining gene expression patterns across different mutations and treatment conditions. The pipeline processes quantile-normalized data from [refine.bio](https://www.refine.bio/) and generates an annotated heatmap to visualize gene expression patterns.

## Key Features

- Analysis of 19 AML model mice samples
- Comparison of different mutations (IDH2, TET2, WT)
- Treatment condition analysis (vehicle, AG-221, 5-Azacytidine)
- Gene expression visualization using hierarchical clustering
- Identification of highly variable genes

## Requirements

- R programming environment
- Required packages:
  * pheatmap
  * magrittr
  * readr
  * dplyr
  * tibble
  * sessioninfo

## Directory Structure

```markdown
project/
├── data/
│   └── SRP070849/
│       ├── SRP070849.tsv      # Gene expression data
│       └── metadata_SRP070849.tsv  # Sample metadata
├── plots/
│   └── aml_heatmap.png       # Generated heatmap
└── results/
    └── top_90_var_genes.tsv   # Highly variable genes
```

## Analysis Pipeline

1. **Data Preparation**
   - Downloads and organizes RNA-seq data from refine.bio
   - Processes metadata for sample information
   - Ensures consistent sample ordering

2. **Gene Selection**
   - Calculates gene variance across samples
   - Selects top 25% most variable genes
   - Saves selected genes for further analysis

3. **Heatmap Generation**
   - Creates annotated heatmap using pheatmap
   - Includes sample clustering
   - Adds mutation and treatment annotations
   - Uses custom color scheme for better visualization

## Usage

1. Clone the repository
2. Install required R packages
3. Download data from refine.bio
4. Run the analysis pipeline
5. Generate heatmap visualization

## Output Files

- `aml_heatmap.png`: Final heatmap visualization
- `top_90_var_genes.tsv`: List of highly variable genes
- Session information for reproducibility

## Citation

This analysis uses data from Shih et al., 2017 
, which investigated AML mutations and treatment responses in mouse models.
