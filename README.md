# Novel Species Identification

This novel species identification pipeline is designed to automate the discovery of new microbial species using genome-resolved metagenomics. Built on the Snakemake framework, it integrates multiple bioinformatics tools into a unified, reproducible workflow. The pipeline streamlines quality assessment, taxonomic classification, and functional analysis of metagenomic assemblies, ensuring consistency, scalability, and accuracy across large-scale microbial studies.


## Available Analysis Modules

### Genome Summary and Classification

This module focuses on evaluating genome assemblies for quality and taxonomic identity.  
It integrates **QUAST** for assembly quality metrics, **CheckM2** and **EukCC** for genome completeness and contamination assessment, and **GTDB-Tk** for taxonomic classification.  
A custom Python script compiles all outputs into a structured summary report, enabling streamlined downstream analysis.

Module 1 - **[ Genome Summary and Classification Workflow](https://github.com/Novel-sp/Genome-summary-and-classification-workflow)**
Module 2 - **[Novelty assessment through OGRI]**
