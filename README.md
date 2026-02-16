<h1 align="center"><span style="color:#0056b3">Novel Species Identification (NOSE)</span></h1>

<p align="center"><strong>A Modular Snakemake Toolkit for Genome-Resolved Discovery</strong></p>

<div align="justify" style="color:#000000; font-family: sans-serif; line-height: 1.6;">
NOSE is a scalable bioinformatics pipeline designed to identify and characterize novel microbial species. By integrating quality assessment, phylogenetics, and functional mapping into a unified Snakemake workflow, NOSE ensures your research is reproducible, automated, and ready for HPC environments.
</div>

---

## <span style="color:#0056b3">Conda Installation and Setup</span>

<table>
  <tr>
    <td bgcolor="#f8f9fa" style="padding:20px; border-left: 5px solid #0056b3;">
      <p style="color:#000000; margin:0;">
        <strong>Getting Started:</strong> Follow the provided guide to install the Anaconda distribution and configure a dedicated Snakemake environment. This setup ensures a stable, reproducible workspace with all necessary bioinformatics channels pre-configured for the pipeline.
      </p>
      <br>
      <a href="https://github.com/Novel-sp/Conda-snakemake-setup"><strong>🔗 Anaconda and Snakemake Setup & Installation</strong></a>
    </td>
  </tr>
</table>

---

## <span style="color:#0056b3">NOSE Modules</span>

<table border="0">
  <tr>
    <td width="50%" valign="top" style="border: 1px solid #e1e4e8; border-radius: 10px; padding: 20px;">
      <h3><span style="color:#0056b3">Module 1</span></h3>
      <p><strong><a href="https://github.com/Novel-sp/Genome-summary-and-classification-workflow">Genome Summary & Classification</a></strong></p>
      <p align="justify" style="color:#000000; font-size: 0.85em;">
        Automated pipeline for assembly metrics and taxonomic lineages. Features <strong>QUAST</strong>, <strong>EukCC</strong>, and <strong>CAT</strong> for eukaryotic data, and <strong>CheckM2</strong> with <strong>GTDB-Tk</strong> for prokaryotic isolates. Includes a standardized HQ filter (≥90% completeness, ≤5% contamination).
      </p>
    </td>
    <td width="50%" valign="top" style="border: 1px solid #e1e4e8; border-radius: 10px; padding: 20px;">
      <h3><span style="color:#0056b3">Module 2</span></h3>
      <p><strong><a href="https://github.com/Novel-sp/Genome-related-indices">Overall Genome-Relatedness (OGRI)</a></strong></p>
      <p align="justify" style="color:#000000; font-size: 0.85em;">
        Comprehensive assessment of genomic distance using 16S rRNA and WGS-based pipelines. Calculates <strong>FastANI</strong>, <strong>AAI</strong>, and <strong>POCP</strong> to define taxonomic positions. Automatically flags potential novel species (ANI < 95%) for downstream validation.
      </p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top" style="border: 1px solid #e1e4e8; border-radius: 10px; padding: 20px;">
      <h3><span style="color:#0056b3">Module 3</span></h3>
      <p><strong><a href="https://github.com/Novel-sp/Phylogenetic-tree">Phylogenetic Tree Workflow</a></strong></p>
      <p align="justify" style="color:#000000; font-size: 0.85em;">
        Validates novelty via genus-specific clusters and conserved Single-Copy Genes (SCGs) using <strong>GToTree</strong>. Infers high-resolution Maximum Likelihood trees via <strong>IQ-TREE</strong> with 1000 ultrafast bootstraps and automated <strong>iTOL</strong> annotation.
      </p>
    </td>
    <td width="50%" valign="top" style="border: 1px solid #e1e4e8; border-radius: 10px; padding: 20px;">
      <h3><span style="color:#0056b3">Module 4</span></h3>
      <p><strong><a href="https://github.com/Novel-sp/Metagenome-mapping-workflow">Metagenome Mapping Workflow</a></strong></p>
      <p align="justify" style="color:#000000; font-size: 0.85em;">
        Quantifies isolate prevalence using <strong>sylph</strong>. Employs k-mer-based containment estimation for rapid profiling across datasets with optimized thresholds to ensure species-level resolution and mitigate false positives.
      </p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top" style="border: 1px solid #e1e4e8; border-radius: 10px; padding: 20px;">
      <h3><span style="color:#0056b3">Module 5</span></h3>
      <p><strong><a href="https://github.com/Novel-sp/Functional-Characterization">Functional Characterization</a></strong></p>
      <p align="justify" style="color:#000000; font-size: 0.85em;">
        Multi-modal screening including <strong>Prokka</strong> (annotation), <strong>antiSMASH</strong> (BGC detection), <strong>geNomad</strong> (phages/plasmids), and <strong>ABRICATE</strong> (resistance/virulence factors) to profile metabolic potential.
      </p>
    </td>
    <td width="50%" valign="top" style="border: 1px solid #e1e4e8; border-radius: 10px; padding: 20px;">
      <h3><span style="color:#0056b3">Module 6</span></h3>
      <p><strong><a href="https://github.com/Novel-sp/Metabolic-model">Metabolic Modeling Workflow</a></strong></p>
      <p align="justify" style="color:#000000; font-size: 0.85em;">
        Genome-scale reconstruction using <strong>CarveMe</strong>. GEMs are exported in SBML format, validated via <strong>COBRApy</strong> growth tests, and benchmarked using the <strong>MEMOTE</strong> suite for stoichiometric consistency and performance.
      </p>
    </td>
  </tr>
</table>

<br>

<p align="center" style="color: #666666; font-size: 0.8em;">
  &copy; 2026 NOSE Project Team • Built for Genome-Resolved Discovery
</p>
