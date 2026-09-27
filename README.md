# Cross-Cohort Single-Cell and Spatial Prioritization of Stromal-Vascular Programs Associated with Immune Exclusion in Microsatellite-Stable Colorectal Liver Metastasis

**Author**: Qiyuan Liu  
**Affiliation**: The First School of Clinical Medicine, Nanjing Medical University, Nanjing 211166, Jiangsu, China  
**Contact**: qiyuanliu@stu.njmu.edu.cn | chessyuan0404@gmail.com  
**ORCID**: 0009-0007-1265-0587  

---

## Overview

This repository provides open-source computational pipelines, statistical models, and reproducibility scripts for the study:
> **"Cross-Cohort Single-Cell and Spatial Prioritization of Stromal-Vascular Programs Associated with Immune Exclusion in Microsatellite-Stable Colorectal Liver Metastasis"**

The investigation integrates:
1. **Multi-Cohort Bulk Transcriptomics**: Random-effects meta-analysis across 3 clinical cohorts (528 participants, 601 biospecimens: GSE49355, GSE213402, GSE14297).
2. **Dual-Cohort Single-Cell Dissection**: Patient-level pseudobulk modeling across 85,319 QC-filtered cells from 16 patients (GSE164522 discovery, GSE178318 validation).
3. **Hierarchical Spatial Synthesis**: Multi-patient 10x Visium spatial transcriptomic analysis across 20,139 valid spots in 6 CRLM patients (GSE217414, GSE225857).
4. **Machine Learning & Negative Controls**: Supervised classification with patient-cluster bootstrap evaluated against an organ-of-origin negative control.
5. **Causal Genetics & Drug Prioritization**: Two-sample cis-eQTL Mendelian randomization (>450,000 GWAS individuals), Bayesian colocalization, and forensic clinical trial auditing.

---

## Repository Structure

```
PUBLIC_REPOSITORY_READY/
├── analysis_scripts/
�?  ├── 01_bulk_meta_analysis.py
�?  ├── 02_single_cell_pseudobulk.py
�?  ├── 03_spatial_hierarchical_synthesis.py
�?  ├── 04_machine_learning_benchmark.py
�?  ├── 05_causal_genetics_mr_coloc.py
�?  ├── 06_target_prioritization.py
�?  └── 07_generate_all_figures.py
├── metadata/
�?  ├── data_registry.tsv
�?  ├── candidate_ranking.tsv
�?  └── clinical_trial_registry.tsv
├── environment.yml
├── requirements.txt
├── .gitignore
└── README.md
```

---

## Installation & Setup

```bash
# Clone the repository
git clone https://github.com/chessyuan/CRLM-immune-exclusion.git
cd CRLM-immune-exclusion

# Create conda environment
conda env create -f environment.yml
conda activate mss_crlm_immune_exclusion

# Or install via pip
pip install -r requirements.txt
```

---

## Step-by-Step Reproduction

Execute the analysis scripts sequentially:
```bash
python analysis_scripts/01_bulk_meta_analysis.py
python analysis_scripts/02_single_cell_pseudobulk.py
python analysis_scripts/03_spatial_hierarchical_synthesis.py
python analysis_scripts/04_machine_learning_benchmark.py
python analysis_scripts/05_causal_genetics_mr_coloc.py
python analysis_scripts/06_target_prioritization.py
python analysis_scripts/07_generate_all_figures.py
```

---

## Data Availability
All analyzed datasets are available from public repositories under accession numbers detailed in `metadata/data_registry.tsv`:
- NCBI GEO: GSE49355, GSE213402, GSE14297, GSE164522, GSE178318, GSE217414, GSE225857
- GDC: TCGA-COAD and TCGA-READ
- GWAS: UK Biobank and FinnGen colorectal cancer summary statistics

---

## License
This project is licensed under the MIT License.
