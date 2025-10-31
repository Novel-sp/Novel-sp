```markdown
<h1 align="center">NOSE — NOvel Species IdEntification</h1>

<p align="center">
  <a href="https://snakemake.readthedocs.io/"><img src="https://img.shields.io/badge/Snakemake-Workflow-green" alt="Snakemake"></a>
  <a href="https://www.python.org/"><img src="https://img.shields.io/badge/Python-3.10-blue" alt="Python"></a>
</p>

## Overview
NOSE is a modular Snakemake workflow to identify and classify novel microbial species from genome and metagenome assemblies.  
Modules are independent and can be run separately; the first module produces per-sample QC, taxonomic assignment and a merged summary for downstream filtering.

Core goals:
- reproducible, scalable pipeline orchestration with Snakemake
- clear, minimal user steps for non-experts
- modular rules so real tools or placeholders can be swapped easily

---

## What Module 1 does (short)
Module 1: automated assembly QC and taxonomy summary. It runs per-assembly analyses to generate completeness/contamination and taxonomy, then aggregates everything into a single results table for easy review.

---

## Quick install (copy-paste)
# 1. Clone repo
git clone https://github.com/Prithvi-0805/NOSE.git
cd NOSE

# 2. Create conda environment and install Snakemake + minimal deps
conda create -n nose_env python=3.10 -y
conda activate nose_env
conda install -c conda-forge -c bioconda snakemake -y
pip install pandas

# 3. Prepare folders and add assemblies
mkdir -p data/assemblies results/{quast,eukcc,cat,checkm2,gtdbtk,compiled}
# Copy your one-FASTA-per-sample files to data/assemblies/
# Filenames should look like: SAMPLE1.fasta SAMPLE2.fasta

---

## Module 1 — Steps (very short & clear)
1. Place FASTA assemblies into data/assemblies/ (one sample per file).  
2. Ensure the conda env is activated:
   conda activate nose_env
3. Run Snakemake with chosen cores (example uses 4):
   snakemake --cores 4 --use-conda
4. Find outputs:
   - Per-sample outputs: results/<tool>/<SAMPLE>/ (placeholder or real tool outputs)
   - Merged summary: results/compiled/module1_summary.tsv
5. Quick inspect:
   head -n 10 results/compiled/module1_summary.tsv

---

## Configuration (what to edit before running)
Open config.yaml and update:
- assemblies_dir: path to your FASTA files (default: data/assemblies)
- results_dir: output root (default: results)
- (Optional) paths to any tool databases if you replace placeholders with real tools

---

## Notes for non-expert users
- You do not need to install all downstream bioinformatics tools to test the workflow — the provided Snakefile includes a placeholder rule that generates demo outputs so you can run end-to-end and see the final table. Replace placeholders with real tool commands when ready.
- Use --cores <N> to control parallelism; higher N speeds up runs but uses more CPU.
- If you want us to wire real commands for particular tools (and provide conda env YAMLs for them), tell us which tools you want enabled and whether your dataset is prokaryotic, eukaryotic, or mixed.

---

## Outputs (expected)
- results/compiled/module1_summary.tsv — merged table of per-sample QC and taxonomy
- results/<tool>/<sample>/ — per-sample reports (one folder per tool)

---

## Minimal troubleshooting
- "No assemblies found": ensure FASTA extension is .fasta or .fa and placed in data/assemblies/
- "Snakemake not found": ensure the conda env is activated and snakemake is installed
- Permissions / disk space: ensure write permissions for results/ and enough disk for databases if you run real tools

---

## License & Contact
Maintain the repo LICENSE as appropriate. For questions or additions, open an issue in the repository.

```
