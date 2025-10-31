<h1 align="center">NOSE: NOvel Species IdEntification </h1>

<p align="center">
   <a href="https://snakemake.readthedocs.io/"><img src="https://img.shields.io/badge/Snakemake-Workflow-green" alt="Snakemake"></a>
  <a href="https://www.python.org/"><img src="https://img.shields.io/badge/Python-3.10-blue" alt="Python"></a>
</p>




## Overview
**NOSE (Novel Species Identification Pipeline)** is a Snakemake-based workflow designed for identifying and classifying novel microbial species from genomic and metagenomic datasets. It is a collection of modular workflows that can be executed in sequence as per user requirements.  

The first module - **Genome Summary and Classification Workflow** - automates data preprocessing, taxonomic classification, and phylogenetic analysis using tools like **GTDB-Tk** and **CAT**. NOSE ensures **reproducibility, scalability, and efficiency** in analyzing large-scale metagenomic data and genome assemblies.

### Key Integrations
-  **Genome quality assessment** - CheckM2, QUAST  
- **Taxonomic classification** - GTDB-Tk, CAT  
- **Relatedness analysis** - ANI, AAI, POCP  
- **Phylogenetic tree construction** - GToTree  
   **Metagenomic abundance estimation** - Sourmash  

<h2>Features</h2>

- **Genome QC & Assembly Metrics** - Assess completeness, contamination, and N50 using <b>CheckM2</b> and <b>QUAST</b>  
- **Taxonomic Classification** - Assign taxonomy with <b>GTDB-Tk</b> (bacteria/archaea) and <b>CAT</b> (contigs)  
- **Relatedness Analysis** - Compute <b>ANI, AAI, POCP</b> to detect novel species  
- **Phylogenetic Analysis** - Build trees with <b>GToTree</b>  
- **Metagenomic Mapping** - Perform sketching and mapping with <b>Sourmash</b>  


## Installation
Ensure you have Snakemake and all required dependencies installed before running the pipeline.

### Prerequisites
- Snakemake  
- Conda (recommended for managing dependencies)

<h2>Step 1 - Clone the repository</h2>

```bash
git clone https://github.com/Prithvi-0805/NOSE.git
cd NOSE

```

<h2>Step 2 - Create Conda environments </h2>

```bash
conda create -y -n project python=3.10
conda activate project

```


<h2> Configuration</h2>

```bash
Modify `config.yaml` to specify:
- Input genome files  
- Output directories  
- Database paths (GTDB-Tk, CAT, etc.)

This ensures proper workflow execution before starting the pipeline.
```

<h2>Workflow</h2>

* **Raw Genomes**  → **Genome QC & Assembly Metrics** (CheckM2/QUAST)
* **Taxonomic Classification** (GTDB-Tk/CAT)
* **Relatedness Analysis** (ANI/AAI/POCP)
* **Phylogenetic Placement** (GToTree)
*  **Metagenomic Mapping** (Sourmash)
* **Identify Novel Species Candidates**

<h2>Usage</h2>

Run the full pipeline:

snakemake --cores 8 --use-conda



<h2>FAQ</h2> <details> <summary><b>Q1: What input formats are supported?</b></summary> FASTA, GenBank, and NCBI genome accessions </details> <details> <summary><b>Q2: Can I run NOSE on large datasets?</b></summary> Yes, Snakemake supports parallel processing efficiently. </details> <details> <summary><b>Q3: How do I update reference databases?</b></summary> Follow the instructions in <code>databases/README.md</code> </details> <details> <summary><b>Q4: How do I cite NOSE?</b></summary> See <code>docs/citations.txt</code> </details>
<h2>Troubleshooting</h2>

GTDB-Tk not found → Ensure GTDBTK_DATA_PATH is set

Pipeline stops on low-quality genome → Adjust config.yaml thresholds

Memory errors →  Reduce threads or increase RAM

<h2> Contributing</h2>

Contributions are welcome! Please follow the steps below to contribute:

1. **Fork** this repository  
2. **Create a new branch** for your feature or bug fix  
   ```bash
   git checkout -b feature-name
   ```
3. **Commit** your changes with a clear message  
   ```bash
   git commit -m "Add: short description of change"
   ```
4. **Push** to your branch  
   ```bash
   git push origin feature-name
   ```
5. **Submit a Pull Request (PR)** describing your updates

Your contributions help improve and expand the NOSE pipeline for the research community.

<h2> Citations</h2>

<a href="https://github.com/AstrobioMike/GToTree">GToTree</a>

<a href="https://github.com/Ecogenomics/GTDBTk">GTDB-Tk</a>

<a href="https://github.com/dib-lab/sourmash">Sourmash</a>

