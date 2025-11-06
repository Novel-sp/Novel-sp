
# NOSE (Novel Species Identification)

The exploration of microbial diversity has expanded dramatically with the advancement of high-throughput sequencing technologies. Despite these advances, a significant proportion of microbial life remains uncultured and uncharacterized, highlighting the need for efficient computational approaches to uncover novel species. Traditional methods relying on culture-based studies capture only a fraction of microbial diversity, often underrepresenting species inhabiting extreme or uncharacterized environments.

Genome-resolved metagenomics now enables direct recovery of microbial genomes from complex samples. However, analyzing such datasets demands a series of steps—quality assessment, taxonomic classification, and phylogenetic analysis—each involving specialized tools and manual coordination. This fragmented workflow can lead to inconsistencies, irreproducibility, and errors during data integration.

---

## About NOSE

To address these challenges, we developed **NOSE (Novel Species Identification)** — a Snakemake-based automated workflow that integrates multiple bioinformatics tools into a single reproducible framework.  
NOSE automates the identification of novel microbial species through quality filtering, classification, relatedness estimation, and functional annotation.  

The pipeline supports both local and high-performance computing (HPC) environments, making it adaptable to a range of computational infrastructures.  
It is particularly useful in large-scale biodiversity projects, clinical microbiome studies, and astrobiological investigations where consistency and reproducibility are essential.

---

## Methodology

### Pipeline Architecture

NOSE is organized as a modular workflow managed by Snakemake.  
Each module can be executed independently or sequentially, providing flexibility for various datasets and research objectives.  
The workflow tracks dependencies, manages environments, and records metadata to ensure reproducible outcomes.

---

## Module 1 — Genome Summary and Classification

### Description
**Module 1** integrates multiple quality assessment and classification tools to evaluate genome completeness, contamination, and taxonomy assignments.

### Tools Used
- **QUAST** – Assembly quality evaluation  
- **CheckM2 / EukCC** – Genome completeness and contamination checks  
- **GTDB-Tk** – Taxonomic classification  
- **Custom Python Script** – Aggregates outputs into a single report  

**Access the repository here:**  
[Genome Summary and Classification Workflow →](https://github.com/Novel-sp/Genome-summary-and-classification-workflow)

---

## Workflow Overview

A schematic representation of the NOSE workflow can be added below:

![NOSE Workflow](https://github.com/Novel-sp/Genome-summary-and-classification-workflow/blob/main/assets/nose_workflow.png)

Each module within the workflow is designed to operate independently and can be linked as part of the larger NOSE ecosystem.

---

## Future Work

Upcoming modules will extend NOSE to include:
- **Module 2:** Functional annotation  
- **Module 3:** Phylogenomic tree construction  
- **Module 4:** Novelty detection and visualization  

---

## Contact

For queries, suggestions, or contributions, please open an issue or submit a pull request in the relevant repository.
