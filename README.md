# RNASeq-Pasilla Analysis

## Overview

**Author:** Daniel Scheuermann  
**Date:** 2024-01-31

This repository contains a comprehensive R script and analysis to replicate a study conducted in 2010, which focused on the Pasilla gene using RNA-seq data. The Pasilla gene was depleted, and RNA was isolated to prepare single-end and paired-end libraries for treated vs untreated samples. The resulting libraries were sequenced to obtain RNA-seq data, and this script compares the gene expression in treated vs untreated samples.

## Dependencies

Ensure you have the following R packages installed before running the script:

- DESeq2
- pheatmap
- dplyr
- RColorBrewer
- ggplot2
- ggrepel
- clusterProfiler
- goseq

## RMD Sections
Please for RNASeq-Pasilla.rmd for a breakdown of the code and the exploration of the data resulting from each section.

### 1. Intro

Provides an overview of the study and its inspiration.

### 2. Data Setup

Reads and sets up the count data and sample information.

### 3. DESeq2 Setup

Creates the DESeq2 object and specifies treatment factors.

### 4. Data Manipulation

Filters genes and performs DESeq2 analysis.

### 5. Looking at Specific Genes

Examines specific genes, focusing on the Pasilla gene.

### 6. Data Manipulation 2

Filters differentially expressed genes.

### 7. Storing Results

Saves manipulated data and normalized counts to CSV files.

### 8. Visualization (Dispersion and PCA)

Generates dispersion and PCA plots for visualizing sample relationships.

### 9. Visualization (HeatMaps and Volcano)

Produces heatmaps, MA plots, and volcano plots for differential gene expression visualization.

### 10. GO-Analysis

Describes the results of Gene Ontology (GO) analysis.

### 11. Kegg Pathway Analysis

Summarizes the findings of Kegg pathway analysis.

### 12. Future Goals

Outlines the author's reflections and future goals for the project.

## Sources

- [Original Study](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3032923/)
- [DESeq2 Tutorial](https://www.youtube.com/playlist?list=PLe1-kjuYBZ05N8tWd2XVW67C4SJOJIdXD)
- [GO Enrichment Tutorial](https://training.galaxyproject.org/training-material/topics/transcriptomics/tutorials/goenrichment/tutorial.html)
- [Kegg Pathway Analysis Tutorial](https://training.galaxyproject.org/training-material/topics/transcriptomics/tutorials/ref-based/tutorial.html#conclusion)
- [Kegg Pathway Database](https://www.genome.jp/kegg/)
