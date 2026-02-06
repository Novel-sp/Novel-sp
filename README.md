# Novel Species Identification (NOSE)

NOSE is a modular, Snakemake-based bioinformatics toolkit designed to support the identification and characterization of novel microbial species from genome-resolved datasets.
The toolkit integrates multiple analysis stages-including genome quality assessment, taxonomic classification, novelty assessment, phylogenetics, metabolic mapping, and functional characterization-within a reproducible and scalable workflow.

NOSE is optimized for execution on Linux servers and HPC environments and is designed to be usable by researchers without prior programming experience, relying on configuration-driven execution rather than manual scripting.


## Prerequisites
### Computational Prerequisites
• Access to a Unix-like system (Linux workstation or HPC server)<br>
• Internet connectivity (required for environment setup and database downloads)<br>
• Sufficient compute resources (CPU and memory requirements vary by module)<br>

### Software Prerequisites
• Conda (Miniconda or Anaconda) must be installed<br>
• Ability to execute bash scripts (.sh files)<br>
• All workflow execution is handled through Snakemake; no direct code modification is required.<br>

----
## For Conda Installation and Setup 

Getting Started: Follow the provided guide to install the Anaconda distribution and configure a dedicated Snakemake environment. This setup ensures a stable, reproducible workspace with all necessary bioinformatics channels pre-configured for the pipeline. - **[Anaconda and Snakemake Setup & Installation](https://github.com/Novel-sp/Conda-snakemake-setup)**<br>

----
## NOSE Modules

Each module is independent and documented in its own repository.<br>
Click on a module to view detailed usage instructions.

Module 1 - **[ Genome Summary and Classification Workflow](https://github.com/Novel-sp/Genome-summary-and-classification-workflow)** <br>
Genome quality assessment and taxonomic classification for prokaryotic and eukaryotic genomes.</br>

Module 2 - **[Novelty assessment through OGRI](https://github.com/Novel-sp/Genome-related-indices)**<br>
Genome-related indices–based novelty assessment (ANI, dDDH, AAI).</br>

Module 3 - **[Phylogenetic tree](https://github.com/Novel-sp/Phylogenetic-tree)**<br>
Phylogenetic reconstruction for candidate novel species.</br>

Module 4 - **[Metabolic Mapping](https://github.com/Novel-sp/Metabolic-Mapping)**<br>
Pathway reconstruction and metabolic profiling.</br>

Module 5 - **[Functional Characterization](https://github.com/Novel-sp/Functional-Characterization)**<br>
Biosynthetic gene clusters, resistance genes, and functional annotation.</br>

Module 6 - **[Modeling](https://github.com/Novel-sp/Metabolic-model)**<br>
Genome-scale metabolic model reconstruction and evaluation using CarveMe.


