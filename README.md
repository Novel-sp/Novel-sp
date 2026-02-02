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

## Anaconda & Snakemake Installation Guide (Linux)

This guide describes how to install **Anaconda Distribution** and set up a **dedicated Snakemake environment** using `conda-forge` and `bioconda`. These steps are suitable for Linux systems, including HPC servers.

---

## 1. Download Anaconda Distribution

Download the latest Anaconda installer based on your Linux architecture.

### For Linux x86_64

```bash
curl -O https://repo.anaconda.com/archive/Anaconda3-2025.12-2-Linux-x86_64.sh
```

### For Linux ARM64 (aarch64)

```bash
curl -O https://repo.anaconda.com/archive/Anaconda3-2025.12-2-Linux-aarch64.sh
```

## 2. (Recommended) Verify Installer Integrity

To ensure the installer was not corrupted or tampered with, verify its **SHA-256 hash**.

### Generate SHA-256 Hash

```bash
sha256sum <PATH_TO_INSTALLER_FILE>
```

Replace `<PATH_TO_INSTALLER_FILE>` with the path to the downloaded `.sh` file.

### Verify Hash

1. Note the generated SHA-256 hash from the output.
2. Visit `https://repo.anaconda.com/archive`
3. Locate the official SHA-256 hash for your installer.
4. Compare both values.

If the hashes match, the installer is safe to use.

## 3. Install Anaconda Distribution

Run the installer corresponding to your system architecture.

### For Linux x86_64

```bash
bash ~/Anaconda3-2025.12-2-Linux-x86_64.sh
```

### For Linux ARM64

```bash
bash ~/Anaconda3-2025.12-2-Linux-aarch64.sh
```
Follow the on-screen instructions to complete the installation. After installation, restart the terminal or source your shell configuration file if required.


## 4. Configure Conda Channels for Snakemake

Snakemake must be installed from **conda-forge** and **bioconda**.

Add and prioritize the required channels:

```bash
conda config --add channels conda-forge
conda config --add channels bioconda
conda config --set channel_priority strict
```

## 5. Create a Dedicated Snakemake Environment

Create a separate conda environment for Snakemake:

```bash
conda create -n snakemake snakemake -y
```

Activate the environment:

```bash
conda activate snakemake
```

## 6. Verify Snakemake Installation

Confirm that Snakemake is installed correctly:

```bash
snakemake --version
```

If the version is displayed, the installation is complete.

## Notes

* Using a dedicated environment avoids dependency conflicts.
* This setup is compatible with local machines and HPC environments.
* Always keep `conda-forge` and `bioconda` at higher priority for bioinformatics workflows.


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

Module 6 - Modeling
