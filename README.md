# AD_transcriptomics (Archival Repository)

> ⚠️ **NOTICE: THIS IS A COMPONENT REPOSITORY** ⚠️
> This repository contains *only* the Phase I transcriptomic meta-analysis scripts referenced in Chapter 2 of the manuscript titled "Targeting Pathogenic Phospho-Tau Epitopes and Associated Pathways: A Novel RNA Aptamer and Repurposed Drugs for Alzheimer's Disease". 
> 
> **For the complete computational pipeline — including RNA aptamer design, hierarchical virtual screening, and molecular dynamics validation — please visit the master repository:** 
> 👉 **[AD_Thesis](https://github.com/RabiaSultan8/AD_Thesis)**

---

## Overview
This repository archives the R scripts used to validate primary molecular targets (MAPT and GSK3B) for Alzheimer's disease through a cross-dataset weighted meta-analysis of two independent transcriptomic datasets:
* **GSE138260**: Microarray study of post-mortem temporal cortex (n = 36).
* **GSE118553**: RNA-seq study of iPSC-derived neurons with familial AD mutations (n = 207).

## Repository Contents (Analysis Pipeline)
The analysis is structured into 11 modular R scripts designed for sequential execution:

* **`00_install_packages.r`**: Environment setup and dependency installation.
* **`01_download_data.r`**: Programmatic retrieval of raw expression matrices and phenotype data from NCBI GEO.
* **`02_preprocess_GSE138260.r`**: Quality control, probe filtering, and limma-based differential expression analysis for the post-mortem cohort.
* **`03_preprocess_GSE118553.r`**: VST-normalization and DESeq2 differential expression analysis for the iPSC-derived neuronal cohort.
* **`04_meta_analysis.r`**: Weighted fixed-effects meta-analysis combining both datasets using Stouffer's z-score method.
* **`05_volcano_v4.r`**: Generation of bilateral volcano plots highlighting the 554 high-confidence DEGs.
* **`06_scatter_v3.r`**: Cross-dataset consistency scatter plot comparing log₂ fold changes.
* **`07a_go_dotplot.r`**: Functional enrichment visualization for GO Biological Processes.
* **`07b_kegg_dotplot.r`**: Functional enrichment visualization for KEGG Pathways.
* **`08_lollipop_v3.r`**: Curated expression profile plotting for the 15-gene AD target panel.
* **`09_heatmap_v2.r`**: Z-scored expression heatmap for the top 40 reproducible DEGs.

## Usage
To reproduce the transcriptomic analysis:
1. Clone this repository.
2. Execute `00_install_packages.r` to ensure all required CRAN and Bioconductor packages are present.
3. Run scripts `01` through `04` sequentially to download data and generate the meta-analysis data objects.
4. Run scripts `05` through `09` to generate the publication-ready figures.

## Full Project Framework
The targets validated by this transcriptomic pipeline serve as the foundation for downstream precision probe discovery (RNA aptamers and repurposed FDA-approved drugs). 

Please direct all issues, pull requests, and inquiries to the **[AD_Thesis](https://github.com/RabiaSultan8/AD_Thesis)** repository.
