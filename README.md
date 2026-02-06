# Novel Species Identification (NOSE)

A Modular Snakemake Toolkit for Genome-Resolved Discovery
NOSE is a scalable bioinformatics pipeline designed to identify and characterize novel microbial species. By integrating quality assessment, phylogenetics, and functional mapping into a unified Snakemake workflow, NOSE ensures your research is reproducible, automated, and ready for HPC environments.

## The Engine: Why Snakemake?
NOSE operates on the logic of a DAG (Directed Acyclic Graph). Here is why that matters for your data:

• Directed: Logic flows sequentially; downstream analytical modules (e.g., Metabolic Mapping) are automatically triggered upon the successful generation of upstream dependencies.

• Acyclic: The pipeline architecture prevents circular dependencies, ensuring a deterministic path from input (FASTA) to output (CSV/TSV).

• Graph-Based: Every rule represents a discrete computational node, allowing for granular error tracking and partial workflow resumption.

## Prerequisites
### Computational Prerequisites
• Access to a Unix-like system (Linux workstation or HPC server)<br>
• Internet connectivity (required for environment setup and database downloads)<br>
• Sufficient compute resources (CPU and memory requirements vary by module)<br>

### Software Prerequisites
• Conda (Miniconda or Anaconda) must be installed<br>
• Ability to execute bash scripts (.sh files)<br>
• All workflow execution is handled through Snakemake; no direct code modification is required.<br>


## For Conda Installation and Setup 

Getting Started: Follow the provided guide to install the Anaconda distribution and configure a dedicated Snakemake environment. This setup ensures a stable, reproducible workspace with all necessary bioinformatics channels pre-configured for the pipeline.<br>
**[Anaconda and Snakemake Setup & Installation](https://github.com/Novel-sp/Conda-snakemake-setup)**<br>

----
## NOSE Modules

Each module is independent and documented in its own repository.<br>
Click on a module to view detailed usage instructions.

Module 1 - **[ Genome Summary and Classification Workflow](https://github.com/Novel-sp/Genome-summary-and-classification-workflow)** <br>
Genome quality assessment and taxonomic classification for prokaryotic and eukaryotic genomes.</br>

Module 2 - **[Novelty assessment through OGRI](https://github.com/Novel-sp/Genome-related-indices)**<br>
Genome-related indices–based novelty assessment (ANI, dDDH, AAI).</br>

Module 3 - **[Phylogenetic Tree](https://github.com/Novel-sp/Phylogenetic-tree)**<br>
Phylogenetic reconstruction for candidate novel species.</br>

Module 4 - **[Metabolic Mapping](https://github.com/Novel-sp/Metabolic-Mapping)**<br>
Pathway reconstruction and metabolic profiling.</br>

Module 5 - **[Functional Characterization](https://github.com/Novel-sp/Functional-Characterization)**<br>
Biosynthetic gene clusters, resistance genes, and functional annotation.</br>

Module 6 - **[Metabolic Modeling](https://github.com/Novel-sp/Metabolic-model)**<br>
Genome-scale metabolic model reconstruction and evaluation using CarveMe.


