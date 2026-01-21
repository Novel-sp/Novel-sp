# Novel Species Identification (NOSE)

NOSE is a modular, Snakemake-based bioinformatics toolkit designed to support the identification and characterization of novel microbial species from genome-resolved datasets.
The toolkit integrates multiple analysis stages—including genome quality assessment, taxonomic classification, novelty assessment, phylogenetics, metabolic mapping, and functional characterization—within a reproducible and scalable workflow.

NOSE is optimized for execution on Linux servers and HPC environments and is designed to be usable by researchers without prior programming experience, relying on configuration-driven execution rather than manual scripting.


## Prerequisites
### Computational Prerequisites
Access to a Unix-like system (Linux workstation or HPC login node)

Internet connectivity (required for environment setup and database downloads)

Sufficient compute resources (CPU and memory requirements vary by module)
### Software Prerequisites
Conda (Miniconda or Anaconda) must be installed

Ability to execute bash scripts (.sh files)

All workflow execution is handled through Snakemake; no direct code modification is required.

  ## Create a Snakemake environment and installation

These instructions assume a Unix-like system with internet access.
Only one environment setup method is required.
Two common routes are shown: using conda (Miniconda/Anaconda) or micromamba. Use one method only.

1. Install Miniconda (if not already installed)
   - Download and install from https://docs.conda.io/en/latest/miniconda.html
   - Restart your shell or run `source ~/.bashrc` (or equivalent).

2. (Recommended) Install mamba for faster environment creation
   ```bash
       conda install -n base -c conda-forge mamba
   ```
4. Create and activate a Snakemake environment
   - If an environment YAML for Snakemake is provided in `env/` (for example `env/snakemake.yaml`), create it:
    Using conda:
    ```bash
       - conda env create -f env/snakemake.yaml
       - conda activate snakemake
    ```
    (or)
    Using mamba (faster):
   ```bash
       - mamba env create -f env/snakemake.yaml
       - conda activate snakemake
   ```
6. Verify Snakemake is available:
    ```bash
       - snakemake --version
    ```
Notes:
- All NOSE modules are executed using this single Snakemake environment

- The workflows rely on Snakemake’s --use-conda feature to automatically create rule-specific environments

- Ensure conda or mamba is available within the active Snakemake environment

----
## NOSE Modules

Each module is independent and documented in its own repository.
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

Module 6 - Modeling
