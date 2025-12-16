# RNASeq–Pasilla Analysis

## Overview

**Author:** Daniel Scheuermann
**Date:** 2024-01-31

This repository contains an R Markdown–based RNA-seq analysis that reproduces, in part, the workflow and findings of a 2010 study investigating the effects of *Pasilla* gene depletion on gene expression. In the original experiment, *Pasilla* was depleted prior to RNA extraction, and both single-end and paired-end sequencing libraries were prepared for treated and untreated samples. The resulting RNA-seq data were analyzed to identify transcriptional changes associated with *Pasilla* knockdown.

This analysis compares treated versus untreated samples while accounting for sequencing strategy as a technical covariate. The workflow emphasizes reproducibility, transparent data filtering, and standard differential expression and visualization practices using DESeq2 and related tools.

## Dependencies

Before running the analysis, ensure the following R packages are installed:

* **DESeq2** – differential expression analysis
* **pheatmap** – heatmap visualization
* **dplyr** – data manipulation
* **RColorBrewer** – color palettes
* **ggplot2** – general plotting
* **ggrepel** – non-overlapping plot labels
* **clusterProfiler** – functional enrichment analysis
* **goseq** – GO enrichment for RNA-seq data

## R Markdown Structure

The file `RNASeq-Pasilla.rmd` contains the full analysis and is organized into the following sections, each corresponding to a logical step in the RNA-seq workflow:

### 1. Introduction

Provides background on the original study, outlines the biological motivation, and describes the goals of the current analysis.

### 2. Data Setup

Imports the raw count matrix and sample metadata, and defines experimental factors including treatment status and sequencing strategy.

### 3. DESeq2 Setup

Constructs the DESeq2 dataset object and specifies the statistical design formula, incorporating sequencing type as a covariate and defining untreated samples as the reference level.

### 4. Data Filtering and Differential Expression Analysis

Applies expression-based filtering to remove low-count genes, followed by DESeq2 modeling to identify differentially expressed genes between treated and untreated samples.

### 5. Examination of Specific Genes

Inspects individual genes of interest, with particular focus on *Pasilla*, to confirm expected expression changes and validate model results.

### 6. Identification of Differentially Expressed Genes

Applies statistical significance and effect-size thresholds to generate a refined set of differentially expressed genes suitable for downstream analysis.

### 7. Storing Results

Exports key outputs—including full DESeq2 results, filtered gene lists, and normalized counts—to CSV files to support reproducibility and further analysis.

### 8. Visualization: Dispersion and PCA

Generates dispersion estimates and principal component analysis (PCA) plots to assess model fit and visualize global patterns in the data.

### 9. Visualization: Heatmaps, MA Plots, and Volcano Plots

Produces multiple visual summaries of differential expression results, including sample distance heatmaps, gene-level heatmaps, MA plots with log-fold-change shrinkage, and volcano plots.

### 10. Gene Ontology (GO) Analysis

Summarizes the results of Gene Ontology enrichment analysis performed externally using the Galaxy platform, highlighting over- and under-represented functional categories.

### 11. KEGG Pathway Analysis

Describes enriched KEGG pathways associated with differentially expressed genes and interprets their potential biological relevance.

### 12. Future Directions

Reflects on methodological insights gained from the project and outlines potential extensions, including deeper biological interpretation and implementation of similar workflows using alternative tools such as UNIX-based pipelines or Python.

## Sources

* [Original Pasilla RNA-seq Study](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3032923/)
* [Galaxy GO Enrichment Tutorial](https://training.galaxyproject.org/training-material/topics/transcriptomics/tutorials/goenrichment/tutorial.html)
* [Galaxy Reference-Based RNA-seq Tutorial](https://training.galaxyproject.org/training-material/topics/transcriptomics/tutorials/ref-based/tutorial.html#conclusion)
* [KEGG Pathway Database](https://www.genome.jp/kegg/)
