# GDC_and_TCGAbiolinks
Workflows and scripts to retrieve cancer omics data from NCI's Genomics Data Commons Portal and TCGAbiolinks


This automated workflow will guide you through analyzing cancer genomics data from TCGA (The Cancer Genome Atlas) using R. By the end, you’ll be able to:

-   Download gene expression, clinical and mutation data for any TCGA cancer type
-   Analyze expression of your genes of interest
-   Visualize differences between tumor and normal samples
-   Perform differential expression analysis, mutation oncoplots and correlation plots
-   Create publication-quality plots

**Key Features:** Most of the workflow runs automatically! You only need to specify your genes of interest and cancer type at the beginning.

# Learning Objectives - Checklist
By completing this workshop, you should be able to:

-   [ ] Download TCGA data using TCGAbiolinks
-   [ ] Process and normalize RNA-seq count data
-   [ ] Perform differential expression analysis
-   [ ] Create publication-quality visualizations
-   [ ] Interpret survival analysis results
-   [ ] Understand gene co-expression patterns
-   [ ] Analyze mutation data and create oncoplots
-   [ ] Explore clinical variables and their impact
-   [ ] Modify the workflow for your own research questions



# Setup & Configuration

## Install Required Packages (ONE-TIME ONLY)

**Run this section only ONCE when setting up R for the first time**

```{r install-packages, eval=FALSE}
# Install BiocManager if not already installed
if (!requireNamespace("BiocManager", quietly = TRUE)) {
  install.packages("BiocManager")
}

# Install Bioconductor packages
BiocManager::install(c(
  "TCGAbiolinks",
  "SummarizedExperiment", 
  "edgeR",
  "DESeq2",
  "org.Hs.eg.db",
  "maftools"
), ask = FALSE, update = FALSE)

# Install CRAN packages
install.packages(c(
  "dplyr", "ggplot2", "pheatmap", "RColorBrewer",
  "survival", "survminer", "ggpubr", "tibble", 
  "Hmisc", "patchwork", "gridExtra", "reactable"
))
