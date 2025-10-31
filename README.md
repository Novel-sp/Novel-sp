# Gene Catalog

![Version](https://img.shields.io/badge/version-0.6.0-brightgreen)

<!-- [![Documentation Status](https://img.shields.io/readthedocs/camp-gene_catalog)](https://camp-documentation.readthedocs.io/en/latest/gene_catalog.html) -->
<!-- [![Documentation Status](https://img.shields.io/badge/docs-unknown-yellow.svg)]()-->

## Overview

This module is designed to function as both a standalone gene catalog pipeline as well as a component of the larger CAMP metagenome analysis pipeline. As such, it is both self-contained (ex. instructions included for the setup of a versioned environment, etc.), and seamlessly compatible with other CAMP modules (ex. ingests and spawns standardized input/output config files, etc.). 

This module generates and functionally annotates a gene catalog from assembled contigs. It is both self-contained (ex. instructions included for the setup of a versioned environment, etc.), and compatible with other CAMP modules (ex. ingests and spawns standardized input/output config files, etc.). 

## Installation

> [!TIP]
> All databases used in CAMP modules will also be available for download on Zenodo (link TBD).

### Install `conda`

If you don't already have `conda` handy, we recommend installing `miniforge`, which is a minimal conda installer that, by default, installs packages from open-source community-driven channels such as `conda-forge`.
```Bash
# If you don't already have conda on your system...
wget https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Linux-x86_64.sh
```

Run the following command to initialize Conda for your shell. This will configure your shell to recognize conda activate. 
```Bash
conda init
```

Restart your terminal or run:
```Bash
source ~/.bashrc  # For bash users
source ~/.zshrc   # For zsh users
```
### Setting up the Gene Cataloguing Module

1. Clone repo from [Github](<https://github.com/Meta-CAMP/camp_gene-catalog>).
```Bash
git clone https://github.com/Meta-CAMP/camp_gene-catalog
```

2. Set up the rest of the module interactively by running `setup.sh`. This will install the necessary conda environments (if they have not been installed already) and generate `parameters.yaml` as well as set up the paths in `test_data/samples.csv` for testing. 
```Bash
cd camp_gene-catalog/
source setup.sh

# If you encounter issues where conda activate is not recognized, follow these steps to properly initialize Conda
conda init
source ~/.bashrc # or source ~/.zshrc
```

3. Make sure the installed pipeline works correctly. With 10 threads and a maximum of 40 GB allocated, the test dataset should finish in approximately 80 minutes.
```Bash
# Run tests on the included sample dataset
conda activate camp
python /path/to/camp_gene-catalog/workflow/gene-catalog.py test
```

## Using the Module

**Input**: `/path/to/samples.csv` provided by the user.

**Output**: TODO

### Module Structure
```
└── workflow
    ├── Snakefile
    ├── gene-catalog.py
    ├── utils.py
    ├── __init__.py
    └── ext/
        └── scripts/
```
- `workflow/gene-catalog.py`: Click-based CLI that wraps the `snakemake` and other commands for clean management of parameters, resources, and environment variables.
- `workflow/Snakefile`: The `snakemake` pipeline. 
- `workflow/utils.py`: Sample ingestion and work directory setup functions, and other utility functions used in the pipeline and the CLI.
- `ext/`: External programs, scripts, and small auxiliary files that are not conda-compatible but used in the workflow.

### Running the Workflow

1. Make your own `samples.csv` based on the template in `configs/samples.csv`. Sample test data can be found in `test_data/`. 
    - `samples.csv` requires either absolute paths or paths relative to the directory that the module is being run in

2. Update the relevant parameters in `configs/parameters.yaml`.

3. Update the computational resources available to the pipeline in `configs/resources.yaml`. 

#### Command Line Deployment

To run CAMP on the command line, use the following, where `/path/to/work/dir` is replaced with the absolute path of your chosen working directory, and `/path/to/samples.csv` is replaced with your copy of `samples.csv`. 
    - The default number of cores available to Snakemake is 1 which is enough for test data, but should probably be adjusted to 10+ for a real dataset.
    - Relative or absolute paths to the Snakefile and/or the working directory (if you're running elsewhere) are accepted!
    - The parameters and resource config YAMLs can also be customized.
```Bash
conda activate camp
python /path/to/camp_gene-catalog/workflow/gene-catalog.py \
    (-c number_of_cores_allocated) \
    (-p /path/to/parameters.yaml) \
    (-r /path/to/resources.yaml) \
    -d /path/to/work/dir \
    -s /path/to/samples.csv
```

#### Slurm Cluster Deployment

To run CAMP on a job submission cluster (for now, only Slurm is supported), use the following.
    - `--slurm` is an optional flag that submits all rules in the Snakemake pipeline as `sbatch` jobs. 
    - In Slurm mode, the `-c` flag refers to the maximum number of `sbatch` jobs submitted in parallel, **not** the pool of cores available to run the jobs. Each job will request the number of cores specified by threads in `configs/resources/slurm.yaml`.
```Bash
conda activate camp
sbatch -J jobname -o jobname.log << "EOF"
#!/bin/bash
python /path/to/camp_gene-catalog/workflow/gene-catalog.py --slurm \
    (-c max_number_of_parallel_jobs_submitted) \
    (-p /path/to/parameters.yaml) \
    (-r /path/to/resources.yaml) \
    -d /path/to/work/dir \
    -s /path/to/samples.csv
EOF
```

## Credits

- This package was created with [Cookiecutter](https://github.com/cookiecutter/cookiecutter>) as a simplified version of the [project template](https://github.com/audreyr/cookiecutter-pypackage>).
- Free software: MIT

